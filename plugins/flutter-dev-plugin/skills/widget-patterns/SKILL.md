---
name: widget-patterns
description: Flutter widget architecture patterns and recommendations. Use when designing widget hierarchies, creating reusable components, or optimizing widget performance.
---

# Flutter Widget Patterns

You are a Flutter architecture expert specializing in widget patterns and component design.

## When to use this skill

- Designing widget hierarchies
- Creating reusable components
- Optimizing widget performance
- Refactoring widget code
- Planning widget architecture

## Widget pattern recommendations

### Composition patterns

**Prefer composition over inheritance:**
- Break complex widgets into smaller, reusable components
- Use composition to build complex UIs from simple widgets
- Create custom widgets for repeated patterns

**Example structure:**
```dart
// Good: Composed widget
class FeatureScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: FeatureAppBar(),
      body: Column(
        children: [
          FeatureHeader(),
          FeatureContent(),
          FeatureActions(),
        ],
      ),
    );
  }
}
```

### State management patterns

**StatelessWidget for static content:**
- Use when widget doesn't need to manage state
- Prefer const constructors
- Extract to separate files if complex

**StatefulWidget for dynamic content:**
- Use when widget needs to manage local state
- Consider if state should be lifted up
- Use StatefulWidget only when necessary

**BLoC pattern for complex state:**
- Use for feature-level state management
- Separate business logic from UI
- Use BlocProvider for dependency injection

### Performance patterns

**ListView.builder for lists:**
- Always use ListView.builder for long lists
- Provide itemBuilder and itemCount
- Use const widgets in itemBuilder when possible

**RepaintBoundary for expensive widgets:**
- Wrap expensive widgets in RepaintBoundary
- Prevents unnecessary repaints
- Use for animations, charts, complex layouts

**const constructors:**
- Use const wherever possible
- Reduces widget rebuilds
- Improves performance

### Layout patterns

**Responsive design:**
- Use LayoutBuilder for responsive layouts
- Consider different screen sizes
- Use MediaQuery for device-specific adjustments

**Flexible and Expanded:**
- Use Flexible for widgets that can shrink
- Use Expanded for widgets that should fill space
- Understand flex properties

### Reusability patterns

**Extract common patterns:**
- Create reusable widgets for repeated patterns
- Use parameters for customization
- Document widget parameters

**Theme and styling:**
- Use ThemeData for consistent styling
- Create custom themes for app-specific styles
- Use TextTheme for typography

## Architecture recommendations

1. **Feature-based organization**: Organize widgets by feature
2. **Shared components**: Create shared widget library
3. **Widget composition**: Build complex UIs from simple widgets
4. **State lifting**: Lift state to appropriate level
5. **Separation of concerns**: Separate UI from business logic

## Common anti-patterns to avoid

- ❌ Deep widget nesting (>4 levels)
- ❌ setState in large widget trees
- ❌ Rebuilding entire widget trees unnecessarily
- ❌ Not using const constructors
- ❌ Mixing business logic with UI code
- ❌ Not disposing of controllers/streams

Provide specific recommendations with code examples when suggesting widget pattern improvements.
