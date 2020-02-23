# Rocket Space
The RocketSpace static website is built with [Hugo](https://gohugo.io/) and the
CSS framework [Bulma](https://bulma.io). It also uses components from the theme
[After Dark](https://after-dark.habd.as/).

Hugo gives us a clear separation of content, layout, and styling.

The basic structure is similar to:

```
├── assets
│   └── style.scss         # main styles (and overrides for theme styles)
├── config.yaml            # site-wide configuration (like navbar and footer)
├── content
│   ├── _index.md          # content for the main landing page
│   ├── about
│   │   └── _index.md      # content for the about page
│   ├── privacy.md         # content for the privacy page
├── data
│   ├── about.toml         # data for the about page
├── layouts
│   ├── _default
│   │   ├── baseof.html    # base layout
│   │   └── single.html    # layout for single pages (like /privacy)
│   ├── about
│   │   └── about.html     # layout for the about page
│   ├── index.html         # layout for the main landing page
│   ├── partials
│   │   ├── css.html       # CSS is generated from assets/style.scss
│   │   ├── navbar.html    # partial for the shared navbar
├── static
│   └── images
└── themes
    └── after-dark
```

To update content, simply edit the Markdown files in `content`. Changes to master will trigger an automatic deployment of the site via CircleCI.


## Development

[Install hugo](https://gohugo.io/getting-started/installing):

``` sh
brew install hugo
```

Then launch the server:

``` sh
hugo server -w -D
```

This runs a lightweight webserver that live-updates as changes are made.

See [hugo documentation](https://gohugo.io/documentation/) for more info.

## Build

`hugo`

This generates the static site in `public/`.

## Deploy

The site is deployed to Github Pages automatically by CI. Just push to master.
