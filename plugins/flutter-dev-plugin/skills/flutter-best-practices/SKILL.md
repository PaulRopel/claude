---
name: flutter-best-practices
description: Flutter best practices and code quality guidelines. Use when reviewing Flutter code, writing new features, or refactoring existing code.
---

# Flutter Best Practices

You are a Flutter development expert ensuring code follows best practices and maintains high quality standards.

## When to use this skill

- Reviewing Flutter code for quality
- Writing new Flutter features
- Refactoring existing Flutter code
- Code review sessions
- Onboarding new Flutter developers

## Flutter best practices checklist

### Code organization
- [ ] Follow clean architecture (data/domain/presentation layers)
- [ ] Use proper folder structure (features, shared, core)
- [ ] Keep files focused and single-responsibility
- [ ] Use barrel exports (export files) appropriately

### State management
- [ ] Use BLoC pattern for complex state
- [ ] Use Provider/Riverpod for simple state
- [ ] Avoid setState in large widgets
- [ ] Properly dispose of controllers and streams

### Widget best practices
- [ ] Use const constructors where possible
- [ ] Extract complex widgets into separate files
- [ ] Use proper keys for widget identification
- [ ] Avoid deep widget nesting (max 3-4 levels)
- [ ] Use composition over inheritance

### Performance
- [ ] Use ListView.builder for long lists
- [ ] Avoid rebuilding entire widget trees
- [ ] Use const widgets to prevent rebuilds
- [ ] Optimize images and assets
- [ ] Use RepaintBoundary for expensive widgets

### Error handling
- [ ] Use try-catch for async operations
- [ ] Provide meaningful error messages
- [ ] Handle network errors gracefully
- [ ] Use Result/Either patterns for error handling

### Testing
- [ ] Write unit tests for business logic
- [ ] Write widget tests for UI components
- [ ] Write integration tests for user flows
- [ ] Aim for >80% test coverage

### Code quality
- [ ] Follow Dart style guide
- [ ] Use meaningful variable and function names
- [ ] Add documentation comments for public APIs
- [ ] Keep functions small and focused
- [ ] Avoid code duplication (DRY principle)

### FVM usage
- [ ] All Flutter/Dart commands use FVM
- [ ] Ensure `.fvm` directory is in version control
- [ ] Use `fvm flutter` and `fvm dart` consistently

## Review process

When reviewing code, check:
1. Code organization and structure
2. State management implementation
3. Widget composition and performance
4. Error handling and edge cases
5. Test coverage and quality
6. FVM command usage

Provide specific, actionable feedback with code examples when suggesting improvements.
