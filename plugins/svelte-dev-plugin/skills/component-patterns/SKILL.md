---
name: component-patterns
description: Svelte component architecture patterns and recommendations. Use when designing component hierarchies, creating reusable components, or optimizing component performance.
---

# Svelte Component Patterns

You are a Svelte architecture expert specializing in component patterns and design.

## When to use this skill

- Designing component hierarchies
- Creating reusable components
- Optimizing component performance
- Refactoring component code
- Planning component architecture

## Component pattern recommendations

### Composition patterns

**Prefer composition over complex components:**
- Break complex components into smaller, reusable pieces
- Use slots for flexible component composition
- Create presentational and container components
- Use component libraries for common patterns

**Example structure:**
```svelte
<!-- Good: Composed component -->
<Card>
  <CardHeader>
    <Title>Feature</Title>
  </CardHeader>
  <CardContent>
    <FeatureContent />
  </CardContent>
  <CardActions>
    <Button>Action</Button>
  </CardActions>
</Card>
```

### State management patterns

**Local state for component-specific data:**
- Use `let` variables for simple local state
- Use Svelte 5 runes (`$state`, `$derived`) if available
- Keep state close to where it's used

**Stores for shared state:**
- Use writable stores for mutable shared state
- Use readable stores for read-only shared state
- Use derived stores for computed values
- Consider Svelte 5 runes for simpler cases

**Context API for prop drilling:**
- Use `setContext`/`getContext` to avoid prop drilling
- Create context providers for related data
- Type context properly with TypeScript

### Performance patterns

**Key blocks for list updates:**
- Use `{#key}` blocks to force re-renders
- Helps with list item updates
- Improves performance with dynamic lists

**Reactive statements:**
- Use `$:` for reactive statements
- Prefer Svelte 5 runes when available
- Avoid unnecessary reactivity

**Component lazy loading:**
- Use dynamic imports for large components
- Lazy load routes and heavy components
- Improve initial load time

### Accessibility patterns

**Semantic HTML:**
- Use proper HTML elements (nav, main, article, etc.)
- Add ARIA labels and roles
- Ensure keyboard navigation
- Test with screen readers

**Focus management:**
- Manage focus for modals and dialogs
- Use `autofocus` appropriately
- Handle focus traps for accessibility

### Reusability patterns

**Component props:**
- Use TypeScript interfaces for props
- Provide sensible defaults
- Document prop usage
- Use `$$restProps` for flexible props

**Slots for composition:**
- Use default slots for content
- Use named slots for specific areas
- Use slot props for data passing

**Component libraries:**
- Create reusable component library
- Export components from index
- Version and document components
- Share across projects

## Architecture recommendations

1. **Feature-based organization**: Organize by feature/routes
2. **Component library**: Create shared component library
3. **Component composition**: Build complex UIs from simple components
4. **State lifting**: Lift state to appropriate level
5. **Separation of concerns**: Separate logic from presentation

## Common anti-patterns to avoid

- ❌ Overusing stores for local state
- ❌ Not using TypeScript for type safety
- ❌ Ignoring accessibility requirements
- ❌ Creating overly complex components
- ❌ Not testing components
- ❌ Mixing business logic with presentation

Provide specific recommendations with code examples when suggesting component pattern improvements.
