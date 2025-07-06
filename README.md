# AI rules

Use our AI rules to get the most out of Nuxt UI when using AI tools like Cursor, Windsurf, Claude Code, and others.

## Installation

You can download the latest version of Hugo's AI rules from the [rules folder](https://github.com/hugorcd/nuxt-ui-rules/blob/main/rules/nuxt-ui.md?plain=1). Copy and paste these into your prompts as needed, or set them up in your AI tool of choice.

## Using with Cursor

To add these rules to Cursor, create a new file at `.cursor/rules/nuxt-ui.mdc`, and add this header to the new file (adjusting the file extensions if necessary):

```md
---
name: nuxt-ui
description: Best practices for using and upgrading Nuxt UI
globs: ["**/*.{js,ts,jsx,tsx,mdx,css,html,vue,svelte,astro}"]
tags:
  - nuxt-ui
  - nuxt
  - library
  - ui
---
```

Finally copy and paste the [rules](https://github.com/hugorcd/nuxt-ui-rules/blob/main/rules/nuxt-ui.md?plain=1) into the end of the file.

## Using with Claude Code

### Adding the rules as needed

If you want fine-grained control, store the [rules](https://github.com/hugorcd/nuxt-ui-rules/blob/main/rules/nuxt-ui.md?plain=1) in a dedicated rules folder like `rules/nuxt-ui.md`. Then, whenever you want to make your current Claude Code session an expert in Nuxt UI, `@`-mention the rules to make Claude read it:

```
╭──────────────────────────────────────────────────────────────────────────────╮
│ > read @rules/nuxt-ui.md and create a custom accordion                       │
╰──────────────────────────────────────────────────────────────────────────────╯
```

### Referencing in your CLAUDE.md file

Copy and paste the [rules](https://github.com/hugorcd/nuxt-ui-rules/blob/main/rules/nuxt-ui.md?plain=1) directly into your `CLAUDE.md` file. Claude Code will now read them for every new session.
