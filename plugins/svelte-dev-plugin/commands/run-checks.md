---
description: Run Svelte type checking, linting, and tests
---

# Run Svelte Checks

Run Svelte type checking, linting, and tests.

## Usage

`/svelte-dev:run-checks [type]`

## Check types

- **all**: Run all checks (default)
- **type**: Run svelte-check only
- **lint**: Run linting only
- **test**: Run tests only
- **format**: Check formatting only

## Commands

Run checks based on "$ARGUMENTS":

- **all** or empty: `npm run check` or `npm run svelte-check && npm run lint && npm test`
- **type**: `npm run svelte-check` or `npx svelte-check --workspace .`
- **lint**: `npm run lint` or `npx eslint .`
- **test**: `npm run test` or `npm test`
- **format**: `npm run format:check` or `npx prettier --check .`

## Check execution

1. **Type checking**: Validates TypeScript and Svelte component types
2. **Linting**: Checks code style and potential issues
3. **Testing**: Runs unit and integration tests
4. **Formatting**: Verifies code formatting consistency

## Best practices

- Run checks before committing code
- Fix type errors before proceeding
- Address linting warnings
- Ensure tests pass
- Use consistent formatting
- Run checks in CI/CD pipeline

## Common issues

- **Type errors**: Fix TypeScript type issues
- **Lint warnings**: Address code style issues
- **Test failures**: Fix broken tests
- **Formatting**: Run formatter to fix formatting
