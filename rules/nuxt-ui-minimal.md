---
name: nuxt-ui
description: Essential rules for Nuxt UI v3 migration and best practices
globs: ["**/*.{js,ts,jsx,tsx,vue,mdx}"]
tags:
  - nuxt-ui
  - nuxt
  - vue
  - ui
---

## Core Principles

- **Always use Nuxt UI v3.0+** - Never use v2 components or patterns
- **Always wrap your app with UApp** - Required for modals, toasts, and overlays
- **Use semantic color aliases** - `primary`, `secondary`, `success`, `info`, `warning`, `error`, `neutral` instead of Tailwind colors
- **Prefer built-in integrations** - Don't install `@nuxt/fonts`, `@nuxt/icon` separately

## Breaking Changes (v2 → v3)

### Renamed Components (NEVER use v2 names)

| ❌ v2 | ✅ v3 |
|-------|-------|
| `UDivider` | `USeparator` |
| `UDropdown` | `UDropdownMenu` |
| `UFormGroup` | `UFormField` |
| `URange` | `USlider` |
| `UToggle` | `USwitch` |
| `UNotification` | `UToast` |
| `UVerticalNavigation` | `UNavigationMenu` with `orientation="vertical"` |

### Removed Components (NEVER use these)

| ❌ v2 | ✅ v3 Replacement |
|-------|-------------------|
| `UModals` | Wrap app with `UApp` |
| `USlideovers` | Wrap app with `UApp` |
| `UNotifications` | Wrap app with `UApp` |

### Props Changes

```vue
<!-- ❌ v2 -->
<USelect :options="items" />
<UModal v-model="isOpen" />

<!-- ✅ v3 -->
<USelect :items="items" />
<UModal v-model:open="isOpen" />
```

## New Overlay Pattern

All overlay components (`UModal`, `UPopover`, `USlideover`) now use trigger-based approach:

```vue
<!-- ✅ Trigger in default slot, content in #content -->
<UModal>
  <UButton>Open</UButton>
  <template #content>
    <UCard>Content here</UCard>
  </template>
</UModal>

<!-- ✅ Or use #body for automatic structure -->
<UModal title="Title">
  <UButton>Open</UButton>
  <template #body>Content</template>
  <template #footer>Actions</template>
</UModal>
```

## Event Handlers

```vue
<!-- ❌ v2 -->
const items = [{ label: 'Edit', click: () => {} }]

<!-- ✅ v3 -->
const items = [{ label: 'Edit', onClick: () => {} }]
```

## Color System

```vue
<!-- ❌ Don't use Tailwind colors -->
<UButton color="red" />
<UButton color="blue" />

<!-- ✅ Use semantic aliases -->
<UButton color="error" />
<UButton color="primary" />
```

## Design Tokens

Use design tokens instead of manual dark mode classes:

```vue
<!-- ❌ Manual dark mode -->
<div class="bg-white dark:bg-gray-900 text-gray-900 dark:text-white border-gray-200 dark:border-gray-700">
  <p class="text-gray-600 dark:text-gray-300">Description</p>
</div>

<!-- ✅ Use design tokens -->
<div class="bg-default text-highlighted border-default">
  <p class="text-muted">Description</p>
</div>
```

**Available token categories**:
- **Text**: `text-dimmed`, `text-muted`, `text-toned`, `text-default`, `text-highlighted`, `text-inverted`
- **Background**: `bg-default`, `bg-muted`, `bg-elevated`, `bg-accented`, `bg-inverted`
- **Border**: `border-default`, `border-muted`, `border-accented`, `border-inverted`
- **Ring**: `ring-default`, `ring-muted`, `ring-accented`, `ring-inverted`
- **Divide**: `divide-default`, `divide-muted`, `divide-accented`, `divide-inverted`

## Composables

```vue
<!-- ❌ v2 -->
const modal = useModal()
const toast = useToast()
toast.add({ timeout: 5000 })

<!-- ✅ v3 -->
const overlay = useOverlay()
const toast = useToast()
toast.add({ duration: 5000 })
```

## Common Pitfalls

1. **Using v2 component names** - Always use v3 names
2. **Forgetting UApp wrapper** - Required for overlays
3. **Installing included dependencies** - Don't install `@nuxt/fonts`, `@nuxt/icon`
4. **Using Tailwind colors over semantic aliases**
5. **Wrong event handlers** - Use `onClick` not `click`
6. **Missing .npmrc for pnpm** - Add `shamefully-hoist=true`

## Setup

```bash
# .npmrc (for pnpm users)
shamefully-hoist=true
```

```ts
// nuxt.config.ts - Don't install these separately
export default defineNuxtConfig({
  modules: ['@nuxt/ui'] // Includes fonts, icons, color-mode
})
```

```vue
<!-- app.vue - Required wrapper -->
<template>
  <UApp>
    <NuxtPage />
  </UApp>
</template>
``` 