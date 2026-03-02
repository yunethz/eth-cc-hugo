+++
title = 'Step 3: Add a Theme'
weight = 3
+++

Hugo supports themes to control the look and layout of your site. The recommended way to add a theme in modern Hugo is via **Hugo Modules** (powered by Go modules).

## Initialize your project as a Go module

```bash
hugo mod init github.com/youruser/mysite
```

This creates a `go.mod` file in your project root.

## Import a theme

Open `hugo.toml` and add a module import. We will use the popular [Ananke](https://github.com/theNewDynamic/gohugo-theme-ananke) theme:

```toml
baseURL = 'https://example.org/'
languageCode = 'en-us'
title = 'My Site'

[module]
  [[module.imports]]
    path = 'github.com/theNewDynamic/gohugo-theme-ananke/v2'
```

## Download the theme module

```bash
hugo mod get -u
```

This fetches the theme and creates a `go.sum` file. Both `go.mod` and `go.sum` should be committed to version control.

## Why Hugo Modules instead of Git submodules?

Hugo Modules offer several advantages:

- **Version pinning** — `go.mod` records the exact version
- **No nested Git repos** — cleaner repository structure
- **Easy updates** — `hugo mod get -u` updates to the latest version
- **Composable** — you can import multiple modules and mount specific directories

You can browse more themes at [themes.gohugo.io](https://themes.gohugo.io/).

{{< guide-nav >}}
