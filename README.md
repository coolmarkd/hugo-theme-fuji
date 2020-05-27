# Fuji

Fuji is a minimal Hugo theme inspired by Hexo theme [Murasaki](https://github.com/printempw/hexo-theme-murasaki/), with responsive grid system and GitHub Primer markdown style.

![RELEASE](https://img.shields.io/github/v/release/amzrk2/hugo-theme-fuji?style=flat-square) ![BUILD STATUS](https://img.shields.io/github/workflow/status/amzrk2/hugo-theme-fuji/Build%20Test?style=flat-square) ![REPO SIZE](https://img.shields.io/github/repo-size/amzrk2/hugo-theme-fuji?style=flat-square) ![LICENSE](https://img.shields.io/github/license/amzrk2/hugo-theme-fuji?style=flat-square)

## Table of contents

- [Live demos](#live-demos)
- [Notice](#notice)
- [Getting started](#getting-started)
- [Update the theme](#update-the-theme)
- [Configration](#configration)
  - [In-post license & comments](#in-post-license--comments)
  - [APlayer](#aplayer)
  - [Image zoom and lazyload settings](#image-zoom-and-lazyload-settings)
  - [Markdown render hook](#markdown-render-hook)
  - [Custom fonts](#custom-fonts)
- [Contributing](#contributing)
- [License](#license)
- [Annotations](#annotations)

## Live demos

[**Demo on gohugo.io (en)**](https://themes.gohugo.io/theme/hugo-theme-fuji/) | [My Blog (zh-Hans)](https://blog.amzrk2.cc/)

<!--more-->

![Screenshot of Fuji](https://raw.githubusercontent.com/amzrk2/hugo-theme-fuji/master/images/screenshot.png)

## Notice

Remember to add [summary divider](https://gohugo.io/content-management/summaries/#manual-summary-splitting) to your post `.md` files to show blockquotes, links and codes with proper style in list pages' summary part.

## Getting started

Inside the folder of your Hugo site run:

```bash
$ git submodule add https://github.com/amzrk2/hugo-theme-fuji.git themes/fuji
```

For more information read the official [setup guide](https://gohugo.io/overview/installing/) of Hugo.

Then copy the `config.toml` in the `exampleSite`to the root of your Hugo site. Change strings as you like.

Run Hugo's built-in local server:

```bash
$ hugo server
```

If you want to generate your site, just run `hugo` or `hugo --minify`.

## Update the theme

Inside the folder of your Hugo site run:

```bash
$ git submodule update --remote --merge
```

## Configration

### In-post license & comments

You can set variables below in post's front matter to disable them:

```toml
noLicense = true # Do not show license in this post
noComments = true # Do not show comments in this post
```

### APlayer

In-post APlayer supported, you can set these variables in post's front matter:

```toml
playerName = "..." # Audio title or name
playerArtist = "..." # Audio artist
playerURL = "..." # Audio URL, support aac, mp3, wav and ogg
playerCover = "..." # Audio cover
```

### Image zoom and lazyload settings

Zoomable, not lazyloaded:

```markdown
![Alt text](test/example.png)
```

Zoomable, lazyloaded:

```html
{{< img-lazy "Alt text" "test/example.png" >}}
{{< img-lazy "row" "Alt text" "test/example.png" >}}
{{< img-lazy "col" "Alt text" "test/example.png" >}}
```

Not zoomable, not lazyloaded, optional ext link:

```html
{{< img-nz "Alt text" "test/example.png" ["https://example.com"] >}}
```

Not zoomable, lazyloaded, optional ext link:

```html
{{< img-nz-lazy "Alt text" "test/example.png" ["https://example.com"] >}}
{{< img-nz-lazy "row" "Alt text" "test/example.png" ["https://example.com"] >}}
{{< img-nz-lazy "col" "Alt text" "test/example.png" ["https://example.com"] >}}
```

`img-lazy` will show a 16x9 placeholder before image is loaded, so `img-lazy-row` will show a 32x9 placeholder and `img-lazy-col` will show a 8x9 placeholder. You can choose different aspect ratios you want for different images. The placeholder image can be set in site's `config.toml`.

### Markdown render hook

You can create the files below in your site to adjust the markdown render hook, see [Hugo's Official Docs](https://gohugo.io/getting-started/configuration-markup#markdown-render-hooks).

You can use `[SITEROOT]/layouts/_default/_markup/render-link.html` to decide whether or not links in the markdown content will open in new tab:

```html
<a href="{{ .Destination | safeURL }}"{{ with .Title }} title="{{ . }}"{{ end }}{{ if strings.HasPrefix .Destination "http" }} target="_blank"{{ end }}>{{ .Text | safeHTML }}</a>
```

### Custom fonts

**Hugo Extended version needed.**

You can create `[SITEROOT]/assets/_custom.sass` to cover sass variables of the theme. Just copy the variable which you need into it, check available variables below:

```scss
$font-size-0: 2rem; // 16px->32px
$font-size-1: 1.75rem; // 16px->28px #
$font-size-2: 1.5rem; // 16px->24px ##
$font-size-3: 1.25rem; // 16px->20px ###
$font-size-4: 1rem; // 16px->16px ####

$body-font: -apple-system, BlinkMacSystemFont, 'SF Pro Text', 'Helvetica Neue', 'Helvetica', 'Arial', 'PingFang SC',
    'Hiragino Sans GB', 'Source Han Sans CN', 'Source Han Sans SC', 'Microsoft YaHei', 'WenQuanYi Micro Hei', sans-serif;
$mono-font: 'Cascadia Code', 'SF Mono', 'Fira Code', 'Consolas', $body-font;
$body-font-size: 16px;
```

## Contributing

Did you found a bug or got an idea for a new feature? Feel free to use the [issue tracker](https://github.com/amzrk2/hugo-theme-fuji/issues) to let me know.

## License

The theme is released under the ```Apache License 2.0```, for more information read the [License](https://github.com/amzrk2/hugo-theme-fuji/blob/master/LICENSE).

## Annotations

Thanks to [community contributors](https://github.com/amzrk2/hugo-theme-fuji/graphs/contributors) for great help.

- [Hugo](https://gohugo.io/)
- [Primer CSS](https://primer.style/css/)
- [APlayer](https://github.com/MoePlayer/APlayer)
- [lazysizes](https://github.com/aFarkas/lazysizes)
- [medium-zoom](https://github.com/francoischalifour/medium-zoom)
