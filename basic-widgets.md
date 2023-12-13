# Basic Widgets

Welcome to the Basic Widgets guide! In this section, we'll explore the fundamental widgets in Flutter.

## Introduction to Widgets

In Flutter, everything is a widget. Widgets are the basic building blocks of a Flutter app. They define the structure and appearance of the user interface.

## Examples of Basic Widgets

Here are some examples of commonly used widgets:

### Container

The `Container` widget is a box model that can contain other widgets. It allows you to customize the dimensions, padding, margin, and decoration of a widget.

```dart
Container(
  width: 200,
  height: 100,
  color: Colors.blue,
  child: Text('Hello, Container!'),
)
```
### Text
The Text widget displays a short piece of text. You can customize its style, such as font size, color, and alignment.

```dart
Text(
  'Hello, Flutter!',
  style: TextStyle(fontSize: 20, color: Colors.green),
)
```
### Row and Column
Row and Column widgets allow you to arrange other widgets horizontally or vertically.

```dart
Row(
  children: <Widget>[
    Icon(Icons.star),
    Icon(Icons.star),
    Icon(Icons.star),
  ],
)
```
