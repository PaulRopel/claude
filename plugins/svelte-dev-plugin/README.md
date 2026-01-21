# Svelte Development Plugin for Claude Code

A comprehensive Claude Code plugin for Svelte development with hooks, LSP configuration, and feature development tools.

## Features

- **Automatic formatting and linting**: Auto-format and fix linting issues on Svelte files
- **Type checking**: Automatically run svelte-check on file changes
- **Test automation**: Automatically run tests when test files are modified
- **Code review**: Automatic code review before git commits
- **Svelte LSP**: Full code intelligence using Svelte Language Server
- **Custom commands**: Component scaffolding, store generation, and check running
- **Agent skills**: Svelte best practices and component pattern recommendations

## Installation

### Local Development

```bash
claude --plugin-dir ./svelte-dev-plugin
```

### From Marketplace

```bash
/plugin install svelte-dev
```

## Prerequisites

- Claude Code installed and authenticated
- Node.js and npm/pnpm/yarn installed
- Svelte project with proper dependencies

## Configuration

### Required Dependencies

Ensure your Svelte project has:

```json
{
  "devDependencies": {
    "@sveltejs/vite-plugin-svelte": "^latest",
    "svelte": "^latest",
    "svelte-check": "^latest",
    "typescript": "^latest",
    "@typescript-eslint/eslint-plugin": "^latest",
    "eslint-plugin-svelte": "^latest",
    "prettier": "^latest",
    "prettier-plugin-svelte": "^latest"
  }
}
```

## Usage

### Custom Commands

- **`/svelte-dev:create-component <name>`**: Create a new Svelte component
  - Creates component with TypeScript, styles, and tests
  - Example: `/svelte-dev:create-component UserCard`

- **`/svelte-dev:generate-store <name> [type]`**: Generate Svelte store
  - Creates writable, readable, or derived store
  - Example: `/svelte-dev:generate-store userStore writable`

- **`/svelte-dev:run-checks [type]`**: Run Svelte checks
  - Runs type checking, linting, tests, or all
  - Example: `/svelte-dev:run-checks all`

### Agent Skills

The plugin includes automatic skills that Claude uses based on context:

- **svelte-best-practices**: Automatically invoked when reviewing Svelte code
- **component-patterns**: Automatically invoked when designing component hierarchies
- **code-review**: Triggered before git commit operations

## Hooks

### PostToolUse Hooks

Automatically triggered after Write/Edit operations:

- **Auto-format**: Formats `.svelte` files using Prettier
- **Lint fixes**: Applies linting fixes using ESLint
- **Type checking**: Runs `svelte-check` on `.svelte`, `.ts`, `.js` files
- **Run tests**: Runs tests when test files are modified

### PreCommand Hooks

- **Code review**: Triggers code review skill before `git commit` operations

## LSP Configuration

The plugin configures Svelte Language Server:

- Uses `svelte-language-server` for code intelligence
- Provides real-time code analysis and autocomplete
- Supports TypeScript and Svelte syntax

## Plugin Structure

```
svelte-dev-plugin/
├── .claude-plugin/
│   └── plugin.json              # Plugin manifest
├── hooks/
│   └── hooks.json               # Hooks configuration
├── .lsp.json                   # Svelte LSP configuration
├── commands/                    # Custom commands
│   ├── create-component.md
│   ├── generate-store.md
│   └── run-checks.md
├── skills/                      # Agent skills
│   ├── svelte-best-practices/
│   ├── component-patterns/
│   └── code-review/
└── README.md                    # This file
```

## Development

### Testing Locally

```bash
# Test the plugin
claude --plugin-dir ./svelte-dev-plugin

# Test hooks by editing a Svelte file
# Test commands with /svelte-dev:*

# Test code review hook by staging changes and running git commit
```

### Debugging

If hooks aren't triggering:
1. Check that file patterns match your files
2. Verify npm scripts are configured in package.json
3. Check Claude Code logs for hook execution

If LSP isn't working:
1. Verify `svelte-language-server` is installed
2. Check that node_modules/.bin is in PATH
3. Ensure Svelte project is properly configured

## Best Practices

- Always use TypeScript for type safety
- Run checks before committing code
- Let hooks handle formatting and linting automatically
- Use code review hook to catch issues before committing
- Follow Svelte best practices recommended by the skills
- Use Svelte 5 runes when available

## Contributing

This plugin is designed for personal use but can be extended:
- Add more custom commands in `commands/`
- Add more skills in `skills/`
- Customize hooks in `hooks/hooks.json`
- Adjust LSP configuration in `.lsp.json`

## License

MIT
