---
description: Create a new Svelte component with proper structure and TypeScript support
---

# Create Svelte Component

Create a new Svelte component following best practices with proper structure, TypeScript, and accessibility.

## Usage

`/svelte-dev:create-component <component-name>`

## What it creates

When creating a component named "$ARGUMENTS", scaffold the following:

```
src/lib/components/${ARGUMENTS}/
├── ${ARGUMENTS}.svelte
└── ${ARGUMENTS}.test.ts
```

## Component structure

Create a Svelte component with:

```svelte
<script lang="ts">
  // Component props
  interface Props {
    // Define props here
  }

  let { prop }: Props = $props();
</script>

<!-- Component markup -->
<div class="${ARGUMENTS}">
  <!-- Component content -->
</div>

<style>
  .${ARGUMENTS} {
    /* Component styles */
  }
</style>
```

## Implementation steps

1. Create the component directory structure
2. Generate the component file with proper TypeScript types
3. Add proper accessibility attributes (aria-labels, roles, etc.)
4. Include JSDoc documentation
5. Create a test file using Vitest or your test framework
6. Ensure component follows Svelte 5 runes pattern if using Svelte 5

## Best practices

- Use Svelte 5 runes (`$state`, `$derived`, `$effect`) if using Svelte 5
- Ensure accessibility (A11y) standards
- Add proper TypeScript types
- Include JSDoc comments
- Use scoped styles
- Follow Svelte component naming conventions
- Export component from index if part of a library
