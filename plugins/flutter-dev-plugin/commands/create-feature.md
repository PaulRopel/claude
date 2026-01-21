---
description: Create a new Flutter feature scaffold with bloc, screen, and repository pattern
---

# Create Flutter Feature

Create a new Flutter feature following best practices with proper structure.

## Usage

`/flutter-dev:create-feature <feature-name>`

## What it creates

When creating a feature named "$ARGUMENTS", scaffold the following structure:

```
lib/features/$ARGUMENTS/
├── data/
│   ├── models/
│   │   └── ${ARGUMENTS}_model.dart
│   └── repositories/
│       └── ${ARGUMENTS}_repository.dart
├── domain/
│   ├── entities/
│   │   └── ${ARGUMENTS}_entity.dart
│   └── usecases/
│       └── get_${ARGUMENTS}.dart
└── presentation/
    ├── bloc/
    │   └── ${ARGUMENTS}_bloc.dart
    ├── screens/
    │   └── ${ARGUMENTS}_screen.dart
    └── widgets/
        └── ${ARGUMENTS}_widget.dart
```

## Implementation steps

1. Create the directory structure using `fvm flutter create --template=package` if needed
2. Generate bloc files using `fvm flutter pub run build_runner build` if using code generation
3. Create the feature files with proper imports and structure
4. Ensure all files follow Flutter best practices and use FVM commands
5. Add proper error handling and state management
6. Include basic tests structure

## Best practices

- Use clean architecture (data/domain/presentation layers)
- Implement proper state management with BLoC
- Add proper error handling
- Include widget tests for presentation layer
- Use FVM for all Flutter/Dart commands
