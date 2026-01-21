# Claude Plugins

Local development plugins for Claude Code.

## Plugins

- **flutter-dev-plugin**: Flutter/Dart development tools with FVM support
- **svelte-dev-plugin**: Svelte development tools with TypeScript support

## Installation as Local Marketplace

This repository is configured as a local marketplace in Claude Code. The plugins will be automatically discovered and can be installed via the plugin system.

### Setup

The repository is already registered in `~/.claude/plugins/known_marketplaces.json` as `claude-plugins-local`. Claude Code will automatically discover plugins in this marketplace.

### Installing Plugins

Install plugins from this marketplace using Claude Code's plugin commands:

```bash
# Install Flutter plugin
/plugin install flutter-dev-plugin@claude-plugins-local

# Install Svelte plugin  
/plugin install svelte-dev-plugin@claude-plugins-local
```

Or use the plugin UI in Claude Code to browse and install from the local marketplace.

### Manual Installation (Alternative)

If you prefer to load plugins directly without installing:

```bash
# Flutter plugin
claude --plugin-dir ~/dev/claude/plugins/flutter-dev-plugin

# Svelte plugin
claude --plugin-dir ~/dev/claude/plugins/svelte-dev-plugin
```

## Plugin Details

### Flutter Dev Plugin

See [flutter-dev-plugin/README.md](./flutter-dev-plugin/README.md) for details.

**Features:**
- Auto-formatting and linting
- Test automation
- Build runner integration
- Code review hooks
- Dart LSP with FVM support
- Custom commands: `/flutter-dev:create-feature`, `/flutter-dev:generate-widget`, `/flutter-dev:run-tests`

### Svelte Dev Plugin

See [svelte-dev-plugin/README.md](./svelte-dev-plugin/README.md) for details.

**Features:**
- Auto-formatting and linting
- Type checking with svelte-check
- Test automation
- Code review hooks
- Svelte LSP support
- Custom commands: `/svelte-dev:create-component`, `/svelte-dev:generate-store`, `/svelte-dev:run-checks`

## Development

This repository contains local plugins for development. Each plugin follows the standard Claude Code plugin structure:

```
plugin-name/
├── .claude-plugin/
│   └── plugin.json
├── hooks/
│   └── hooks.json
├── commands/
├── skills/
└── README.md
```

## Verification

After setting up aliases, restart Claude Code and verify:

1. Plugin commands appear (e.g., `/flutter-dev:*` and `/svelte-dev:*`)
2. Hooks trigger on file edits
3. LSP works correctly

If plugins don't load, check `~/.claude/debug/*.txt` for plugin load messages.

## Notes

- These plugins are for local development use
- They are separate from marketplace plugins (stored in `~/.claude/plugins/marketplaces/`)
- Installed plugins are tracked in `~/.claude/plugins/installed_plugins.json`
- Local plugins loaded via `--plugin-dir` don't appear in the installed plugins list
