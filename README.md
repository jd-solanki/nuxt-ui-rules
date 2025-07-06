# Guidelines for AI Assistants

Leverage the full power of Nuxt UI in your AI-powered workflow. These guidelines are designed to help AI coding assistants like Cursor, Windsurf, Claude Code, and others understand the best practices for working with the Nuxt UI component library.

## Getting Started

You can grab the latest version of the guidelines from the [rules folder](https://github.com/hugorcd/nuxt-ui-rules/blob/main/rules/nuxt-ui.md?plain=1). From there, you can either copy and paste them into your prompts on a case-by-case basis or integrate them directly into your preferred AI assistant's configuration for persistent access.

## Using with Cursor

To integrate these guidelines with Cursor, follow these steps:

1.  Start by creating a new file named `nuxt-ui.mdc` inside the `.cursor/rules/` directory of your project.

2.  Populate the new file with the following header. Be sure to adjust the `globs` property to match the file types you are working with.

    ```md
    ---
    name: nuxt-ui
    description: Best practices for using and upgrading Nuxt UI
    globs: ["**/*.{js,ts,css,html,vue}"]
    tags:
      - nuxt-ui
      - nuxt
      - library
      - ui
    ---
    ```

3.  To complete the setup, append the full content of the [guidelines file](https://github.com/hugorcd/nuxt-ui-rules/blob/main/rules/nuxt-ui.md?plain=1) to the end of your newly created `nuxt-ui.mdc`.

## Using with Claude Code

You have two main options for using these guidelines with Claude Code.

### On-Demand Context

For more granular control, place the [guidelines file](https://github.com/hugorcd/nuxt-ui-rules/blob/main/rules/nuxt-ui.md?plain=1) in a designated project directory, for instance, `rules/nuxt-ui.md`. Then, anytime you need Claude to be aware of Nuxt UI best practices for a specific task, simply `@`-mention the file path in your prompt to load it into the current session's context.
