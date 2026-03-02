+++
title = 'Step 4: Add Content'
weight = 4
+++

## Create your first post

Hugo provides a command to scaffold new content files:

```bash
hugo new content content/posts/hello-world.md
```

This creates a file using the archetype template in `archetypes/default.md`. The resulting file looks like:

```markdown
+++
title = 'Hello World'
date = 2026-03-02T12:00:00+01:00
draft = true
+++
```

## Write some content

Open the file and add Markdown content below the front matter:

```markdown
+++
title = 'Hello World'
date = 2026-03-02T12:00:00+01:00
draft = true
+++

This is my first Hugo post. Hugo makes it easy to write
content in Markdown and have it rendered into a fast,
static website.
```

## Preview your site

Start the development server with draft content enabled:

```bash
hugo server -D
```

Open `http://localhost:1313` in your browser. The site live-reloads as you edit files.

## Publish a post

When you are happy with a post, set `draft = false` in the front matter (or remove the line entirely). Only non-draft content is included when you build the production site.

{{< guide-nav >}}
