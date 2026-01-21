---
description: Generate Flutter widget boilerplate with proper structure
---

# Generate Widget

Generate a new Flutter widget with proper structure and best practices.

## Usage

`/flutter-dev:generate-widget <widget-name>`

## What it creates

When generating a widget named "$ARGUMENTS", create:

```dart
import 'package:flutter/material.dart';

class ${ARGUMENTS}Widget extends StatelessWidget {
  const ${ARGUMENTS}Widget({
    super.key,
  });

  @override
  Widget build(BuildContext context) {
    return Container(
      // Widget implementation
    );
  }
}
```

## Implementation steps

1. Create the widget file in the appropriate location
2. Use proper Flutter widget structure (StatelessWidget or StatefulWidget)
3. Add proper key parameter for widget tree optimization
4. Include proper documentation comments
5. Follow Flutter naming conventions
6. Use const constructors where possible
7. Format the code using `fvm dart format`

## Widget types

- **StatelessWidget**: For widgets that don't need state
- **StatefulWidget**: For widgets that need to manage state
- Consider using composition over inheritance

## Best practices

- Use const constructors for performance
- Extract complex widgets into separate files
- Use proper keys for widget identification
- Follow Flutter's widget composition patterns
- Ensure accessibility (semantics, etc.)
