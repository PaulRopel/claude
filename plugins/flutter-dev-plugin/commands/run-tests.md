---
description: Run Flutter tests with coverage using FVM
---

# Run Flutter Tests

Run Flutter tests with coverage reporting.

## Usage

`/flutter-dev:run-tests [test-path]`

## Command

Run tests using FVM:

```bash
fvm flutter test --coverage
```

If a specific test path is provided in "$ARGUMENTS", run:

```bash
fvm flutter test --coverage $ARGUMENTS
```

## Test execution

1. Run all tests: `fvm flutter test --coverage`
2. Run specific test file: `fvm flutter test --coverage test/path/to/test.dart`
3. Run tests matching pattern: `fvm flutter test --coverage --name pattern`

## Coverage

After running tests, generate coverage report:

```bash
genhtml coverage/lcov.info -o coverage/html
```

## Best practices

- Run tests before committing code
- Aim for high test coverage (>80%)
- Write unit tests for business logic
- Write widget tests for UI components
- Write integration tests for user flows
- Use FVM to ensure consistent Flutter version across team

## Test types

- **Unit tests**: Test individual functions and classes
- **Widget tests**: Test individual widgets in isolation
- **Integration tests**: Test complete user flows
