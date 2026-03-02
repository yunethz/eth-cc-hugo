+++
title = 'Step 2: Create a New Hugo Project'
weight = 2
+++

## Scaffold the project

Create a new Hugo project and enter its directory:

```bash
hugo new project mysite
cd mysite
```

This creates the standard Hugo directory structure:

```
mysite/
├── archetypes/    # Templates for new content
├── assets/        # CSS, JS, images processed by Hugo Pipes
├── content/       # Your Markdown content
├── data/          # Data files (JSON, TOML, YAML)
├── i18n/          # Translation files
├── layouts/       # HTML templates
├── static/        # Files copied as-is to the output
├── themes/        # Theme directory (if using submodules)
└── hugo.toml      # Site configuration
```

## Initialize Git

```bash
git init
```

## Set up mise

Create a `mise.toml` file in the project root to pin your tool versions:

```toml
[tools]
"aqua:gohugoio/hugo/hugo-extended" = "0.157.0"
"aqua:sass/dart-sass" = "1.97.3"
go = "1.26.0"
```

Now run `mise install` (or simply `cd` back into the directory — mise activates automatically):

```bash
mise install
```

Verify everything is in place:

```bash
hugo version
go version
sass --version
```

You should see Hugo report the **extended** edition.

{{< guide-nav >}}
