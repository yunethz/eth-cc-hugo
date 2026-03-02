# Hugo Getting Started Guide

A minimal template site that teaches how to set up [Hugo](https://gohugo.io) with GitHub Pages.

**[View the live site](https://oetiker.github.io/eth-cc-hugo/)**

## What's included

- Hugo extended via [mise](https://mise.jdx.dev) for reproducible local development
- [Ananke](https://github.com/theNewDynamic/gohugo-theme-ananke) theme via Hugo Modules
- Custom SCSS overrides compiled with Dart Sass
- Step-by-step guide content covering install, setup, theming, and deployment
- GitHub Actions workflow for automatic deployment to GitHub Pages

## Quick start

Click **"Use this template"** above to create your own repository, then:

```bash
git clone https://github.com/YOUR_USER/YOUR_REPO.git
cd YOUR_REPO
mise install        # installs Hugo, Go, and Dart Sass
hugo server -D      # start the dev server
```

Open http://localhost:1313 to view the site.

## Prerequisites

- [Git](https://git-scm.com)
- [mise](https://mise.jdx.dev) — installs all other tools automatically

## Deploy

Push to `main` and GitHub Actions builds and deploys to GitHub Pages. Make sure to enable **Settings > Pages > Source: GitHub Actions** in your repository.

## License

MIT
