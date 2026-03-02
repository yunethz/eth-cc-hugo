+++
title = 'Step 1: Prerequisites'
weight = 1
+++

Before we begin, make sure you have the following tools installed on your system.

## Git

Hugo uses Git for module management. Install it via your system package manager:

- **macOS:** `brew install git`
- **Debian/Ubuntu:** `sudo apt install git`
- **Fedora:** `sudo dnf install git`

Verify with:

```bash
git --version
```

## mise — Dev Tool Manager

[mise](https://mise.jdx.dev) is a polyglot tool version manager that lets you pin exact tool versions per project. We use it to install Hugo, Go, and Dart Sass without polluting your global system.

Install mise by following the [official instructions](https://mise.jdx.dev/getting-started.html), for example:

```bash
curl https://mise.run | sh
```

Then activate it in your shell (add to your `~/.bashrc` or `~/.zshrc`):

```bash
eval "$(mise activate bash)"   # or zsh, fish
```

Verify with:

```bash
mise --version
```

## What mise will handle for you

In the next step we will set up a `mise.toml` file in the project. Once that is in place, `mise` will automatically install the correct versions of:

- **Hugo** (extended edition) — the static site generator
- **Go** — required for Hugo Modules
- **Dart Sass** — for SCSS/Sass processing

No manual installation of these tools is needed.

{{< guide-nav >}}
