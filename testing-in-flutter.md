# Testing in Flutter

Welcome to the Testing in Flutter guide! In this section, we'll explore unit testing with the `test` package, widget testing, integration testing, mocking, and test-driven development (TDD) in Flutter.

## Unit Testing with Test Package

The `test` package is used for writing and running tests in Dart.

```dart
void main() {
  test('Sample Test', () {
    expect(2 + 2, equals(4));
  });
}
```

### Widget Testing and Integration Testing
Flutter supports both widget testing for individual widgets and integration testing for testing the entire app.

```dart
testWidgets('Widget Test Example', (WidgetTester tester) async {
  await tester.pumpWidget(MyWidget());

  expect(find.text('Hello, Flutter!'), findsOneWidget);
});
```

### Mocking and Test-Driven Development (TDD)
Mocking is used to simulate dependencies during testing. Test-driven development involves writing tests before writing the actual code.

```dart
// Example of TDD
test('Counter increments correctly', () {
  final counter = Counter();

  counter.increment();

  expect(counter.value, 1);
});
```
