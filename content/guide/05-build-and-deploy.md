+++
title = 'Step 5: Build and Deploy'
weight = 5
+++

## Build the production site

Run Hugo without flags to generate the final output:

```bash
hugo --minify
```

The rendered site is written to the `public/` directory. This is a fully self-contained static site you can host anywhere.

## Deploy to GitHub Pages

The easiest way to deploy is with GitHub Actions. Create the workflow file:

```
.github/workflows/hugo.yaml
```

with the following content:

```yaml
name: Deploy Hugo site to GitHub Pages

on:
  push:
    branches: [main]
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: pages
  cancel-in-progress: false

defaults:
  run:
    shell: bash

jobs:
  build:
    runs-on: ubuntu-latest
    env:
      DART_SASS_VERSION: 1.97.3
    steps:
      - name: Checkout
        uses: actions/checkout@v4
        with:
          fetch-depth: 0

      - name: Install tools with mise
        uses: jdx/mise-action@v3
        with:
          cache: true

      - name: Install Dart Sass
        run: |
          curl -sLJO "https://github.com/sass/dart-sass/releases/download/${DART_SASS_VERSION}/dart-sass-${DART_SASS_VERSION}-linux-x64.tar.gz"
          tar -C "${HOME}" -xf "dart-sass-${DART_SASS_VERSION}-linux-x64.tar.gz"
          rm "dart-sass-${DART_SASS_VERSION}-linux-x64.tar.gz"
          echo "${HOME}/dart-sass" >> "${GITHUB_PATH}"

      - name: Setup Pages
        id: pages
        uses: actions/configure-pages@v5

      - name: Initialize Hugo modules
        run: hugo mod get -u

      - name: Build
        run: |
          hugo --minify \
            --baseURL "${{ steps.pages.outputs.base_url }}/"

      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: ./public

  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

## Enable GitHub Pages

1. Push your repository to GitHub
2. Go to **Settings > Pages**
3. Set **Source** to **GitHub Actions**

Every push to `main` will now automatically build and deploy your site.

{{< guide-nav >}}
