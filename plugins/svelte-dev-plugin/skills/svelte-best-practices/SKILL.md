---
name: svelte-best-practices
description: Svelte best practices and code quality guidelines. Use when reviewing Svelte code, writing new components, or refactoring existing Svelte code.
---

# Svelte Best Practices

You are a Svelte development expert ensuring code follows best practices and maintains high quality standards.

## When to use this skill

- Reviewing Svelte code for quality
- Writing new Svelte components
- Refactoring existing Svelte code
- Code review sessions
- Onboarding new Svelte developers

## Svelte best practices checklist

### Component structure
- [ ] Use proper component organization (lib/components, lib/routes)
- [ ] Keep components focused and single-responsibility
- [ ] Use TypeScript for type safety
- [ ] Proper file naming conventions (PascalCase for components)

### Svelte 5 Runes (if using Svelte 5)
- [ ] Use `$state()` for reactive state
- [ ] Use `$derived()` for computed values
- [ ] Use `$effect()` for side effects
- [ ] Prefer runes over stores when appropriate
- [ ] Use `$props()` for component props

### Accessibility (A11y)
- [ ] Proper ARIA labels and roles
- [ ] Keyboard navigation support
- [ ] Focus management
- [ ] Screen reader compatibility
- [ ] Semantic HTML elements

### Performance
- [ ] Use `{#key}` blocks for list updates
- [ ] Avoid unnecessary reactivity
- [ ] Use `bind:this` appropriately
- [ ] Optimize component re-renders
- [ ] Lazy load components when possible

### State management
- [ ] Use stores for global state
- [ ] Prefer local state when possible
- [ ] Use context API for prop drilling
- [ ] Keep state close to where it's used
- [ ] Use Svelte 5 runes for local state if available

### TypeScript
- [ ] Proper type definitions for props
- [ ] Type store interfaces
- [ ] Use strict TypeScript settings
- [ ] Avoid `any` types
- [ ] Type event handlers

### Styling
- [ ] Use scoped styles
- [ ] Follow CSS naming conventions
- [ ] Use CSS variables for theming
- [ ] Avoid inline styles when possible
- [ ] Use CSS modules or preprocessors if needed

### Testing
- [ ] Write component tests
- [ ] Test user interactions
- [ ] Test accessibility
- [ ] Use Vitest or your test framework
- [ ] Aim for good test coverage

### Code quality
- [ ] Follow Svelte style guide
- [ ] Use meaningful variable and function names
- [ ] Add JSDoc comments for public APIs
- [ ] Keep functions small and focused
- [ ] Avoid code duplication (DRY principle)

### Build and tooling
- [ ] Use Vite for build tooling
- [ ] Run svelte-check for type checking
- [ ] Use ESLint with Svelte plugin
- [ ] Format code with Prettier
- [ ] Use proper import/export patterns

## Review process

When reviewing code, check:
1. Component structure and organization
2. TypeScript usage and type safety
3. Accessibility implementation
4. Performance considerations
5. State management approach
6. Test coverage and quality
7. Code style and consistency

Provide specific, actionable feedback with code examples when suggesting improvements.
