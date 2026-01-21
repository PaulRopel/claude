# Flutter Development Plugin for Claude Code

A comprehensive Claude Code plugin for Flutter development with hooks, LSP configuration, and feature development tools. All Flutter/Dart commands use FVM (Flutter Version Management) for consistent version control.

## Features

- **Automatic formatting and linting**: Auto-format and fix linting issues on Dart files
- **Test automation**: Automatically run tests when test files are modified
- **Build runner**: Automatically run build_runner when generated code imports are detected
- **Code review**: Automatic code review before git commits
- **Dart LSP**: Full code intelligence using FVM-managed Dart SDK
- **Custom commands**: Feature scaffolding, widget generation, and test running
- **Agent skills**: Flutter best practices and widget pattern recommendations

## Installation

### Local Development

```bash
claude --plugin-dir ./flutter-dev-plugin
```

### From Marketplace

```bash
/plugin install flutter-dev
```

## Prerequisites

- Claude Code installed and authenticated
- Flutter installed via FVM
- FVM configured in your project (`.fvm` directory present)

## Configuration

### FVM Setup

Ensure your Flutter project uses FVM:

```bash
# Install FVM if not already installed
dart pub global activate fvm

# Install Flutter version
fvm install <version>

# Use Flutter version in project
fvm use <version>
```

The plugin automatically uses `fvm flutter` and `fvm dart` commands.

## Usage

### Custom Commands

- **`/flutter-dev:create-feature <name>`**: Create a new Flutter feature scaffold
  - Creates clean architecture structure (data/domain/presentation)
  - Includes BLoC, repository, and screen files
  - Example: `/flutter-dev:create-feature user-profile`

- **`/flutter-dev:generate-widget <name>`**: Generate widget boilerplate
  - Creates properly structured Flutter widget
  - Includes const constructor and proper documentation
  - Example: `/flutter-dev:generate-widget user-card`

- **`/flutter-dev:run-tests [path]`**: Run Flutter tests with coverage
  - Runs all tests or specific test file
  - Generates coverage report
  - Example: `/flutter-dev:run-tests test/features/auth`

### Agent Skills

The plugin includes automatic skills that Claude uses based on context:

- **flutter-best-practices**: Automatically invoked when reviewing Flutter code
- **widget-patterns**: Automatically invoked when designing widget hierarchies
- **code-review**: Triggered before git commit operations

## Hooks

### PostToolUse Hooks

Automatically triggered after Write/Edit operations:

- **Auto-format**: Formats `.dart` files using `fvm dart format`
- **Lint fixes**: Applies lint fixes using `fvm dart fix --apply`
- **Run tests**: Runs `fvm flutter test` when test files are modified
- **Build runner**: Runs `fvm dart run build_runner build` when generated code imports detected

### PreCommand Hooks

- **Code review**: Triggers code review skill before `git commit` operations

## LSP Configuration

The plugin configures Dart LSP server using FVM:

- Uses `fvm dart language-server` for code intelligence
- Respects project-specific Flutter version via FVM
- Provides real-time code analysis and autocomplete

## Plugin Structure

```
flutter-dev-plugin/
├── .claude-plugin/
│   └── plugin.json              # Plugin manifest
├── hooks/
│   └── hooks.json               # Hooks configuration
├── .lsp.json                   # Dart LSP configuration
├── commands/                    # Custom commands
│   ├── create-feature.md
│   ├── generate-widget.md
│   └── run-tests.md
├── skills/                      # Agent skills
│   ├── flutter-best-practices/
│   ├── widget-patterns/
│   └── code-review/
└── README.md                    # This file
```

## Development

### Testing Locally

```bash
# Test the plugin
claude --plugin-dir ./flutter-dev-plugin

# Test hooks by editing a Dart file
# Test commands with /flutter-dev:*

# Test code review hook by staging changes and running git commit
```

### Debugging

If hooks aren't triggering:
1. Check that file patterns match your files
2. Verify FVM is installed and configured
3. Check Claude Code logs for hook execution

If LSP isn't working:
1. Verify `fvm dart` command works in your terminal
2. Check that `.fvm` directory exists in your project
3. Ensure Flutter version is installed via FVM

## Best Practices

- Always use FVM for Flutter version management
- Run tests before committing code
- Let hooks handle formatting and linting automatically
- Use code review hook to catch issues before committing
- Follow Flutter best practices recommended by the skills

## Contributing

This plugin is designed for personal use but can be extended:
- Add more custom commands in `commands/`
- Add more skills in `skills/`
- Customize hooks in `hooks/hooks.json`
- Adjust LSP configuration in `.lsp.json`

## License

MIT
