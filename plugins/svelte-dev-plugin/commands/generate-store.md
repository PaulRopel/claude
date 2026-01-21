---
description: Generate a Svelte store with proper TypeScript types
---

# Generate Svelte Store

Generate a new Svelte store (writable, readable, or derived) with proper TypeScript types.

## Usage

`/svelte-dev:generate-store <store-name> [type]`

## Store types

- **writable**: Mutable store (default)
- **readable**: Read-only store
- **derived**: Computed store based on other stores

## What it creates

When generating a store named "$ARGUMENTS" of type "${2|writable,readable,derived|}", create:

```typescript
import { writable } from 'svelte/store';

export interface ${ARGUMENTS}Store {
  // Define store shape
}

const create${ARGUMENTS}Store = () => {
  const { subscribe, set, update } = writable<${ARGUMENTS}Store>({
    // Initial state
  });

  return {
    subscribe,
    // Custom methods
  };
};

export const ${ARGUMENTS}Store = create${ARGUMENTS}Store();
```

## Implementation steps

1. Create the store file in `src/lib/stores/`
2. Define TypeScript interface for store state
3. Implement store with proper typing
4. Export store for use in components
5. Add JSDoc documentation
6. Include example usage in comments

## Best practices

- Use TypeScript for type safety
- Keep stores focused and single-purpose
- Provide clear API methods
- Document store purpose and usage
- Handle errors gracefully
- Consider using Svelte 5 runes instead if appropriate
