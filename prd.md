## Best-practice context (what those repos in ~/.claude are)

- Claude Code uses `~/.claude/plugins/marketplaces/` to store *marketplace repositories* it clones/updates automatically (see `~/.claude/plugins/known_marketplaces.json`). Those are for discovery/installation.
- Installed plugins are then materialized under `~/.claude/plugins/cache/...` and tracked in `~/.claude/plugins/installed_plugins.json`.
- For **your own local plugins**, the recommended dev flow is to keep them in a normal workspace repo (e.g. `~/dev/claude-plugins`) and run Claude Code with `--plugin-dir /path/to/plugin` (documented in your plugin READMEs).

## Target structure

- New repo: `~/dev/claude-plugins/`
- Inside it, one folder per plugin:
- `~/dev/claude-plugins/flutter-dev-plugin/`
- `~/dev/claude-plugins/svelte-dev-plugin/`
- Each plugin already matches the expected layout (has `.claude-plugin/plugin.json`, plus `commands/`, `hooks/`, `skills/`, etc.).

## Move plan (from ~/.dotfiles)

- Move these directories into the new repo:
- `~/.dotfiles/claude/.claude/plugins/flutter-dev-plugin` → `~/dev/claude-plugins/flutter-dev-plugin`
- `~/.dotfiles/claude/.claude/plugins/svelte-dev-plugin` → `~/dev/claude-plugins/svelte-dev-plugin`
- Optionally also move `~/.dotfiles/flutter-dev-plugin/` if it’s a duplicate of the same plugin (we’ll verify which one is canonical before deleting/moving).

## Git repo setup

- Initialize `~/dev/claude-plugins` as its own git repo.
- Add a README that documents:
- how to run: `claude --plugin-dir ~/dev/claude-plugins/svelte-dev-plugin` (and same for flutter)
- how to keep both loaded conveniently (see wrapper below)

## Make it easy to run (no remembering flags)

Choose one of these (we’ll implement the simplest that fits your dotfiles):

- **Shell alias** in your zsh config:
- `alias claude-svelte='claude --plugin-dir ~/dev/claude-plugins/svelte-dev-plugin'`
- `alias claude-flutter='claude --plugin-dir ~/dev/claude-plugins/flutter-dev-plugin'`
- **Wrapper script** (better if you want one command that loads multiple plugins):
- script runs `claude` with multiple `--plugin-dir` flags (if supported) or one combined entry-point if you prefer.

## Verification

- Restart Claude Code sessions launched via the alias/wrapper.
- Confirm plugin commands appear (e.g. `/svelte-dev:...` and `/flutter-dev:...`).
- If anything doesn’t load, check `~/.claude/debug/*.txt` for plugin load messages.