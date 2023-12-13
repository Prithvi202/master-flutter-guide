# Navigation in Flutter

Welcome to the Navigation in Flutter guide! In this section, we'll explore navigation concepts and methods in Flutter.

## Introduction to Navigation

Navigation is an essential part of any app. In Flutter, navigation is the process of moving from one screen (or page) to another.

### Navigator Widget

The `Navigator` widget is used to manage the navigation stack.

```dart
Navigator.push(
  context,
  MaterialPageRoute(builder: (context) => SecondScreen()),
);
```

### MaterialPageRoute
The MaterialPageRoute is a built-in page route that uses material page transitions.

Passing Data Between Screens
You can pass data between screens using the constructor of the destination screen.

```dart
class FirstScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return ElevatedButton(
      onPressed: () {
        Navigator.push(
          context,
          MaterialPageRoute(builder: (context) => SecondScreen(data: 'Hello from FirstScreen!')),
        );
      },
      child: Text('Go to SecondScreen'),
    );
  }
}

class SecondScreen extends StatelessWidget {
  final String data;

  SecondScreen({required this.data});

  @override
  Widget build(BuildContext context) {
    return Text('Data from FirstScreen: $data');
  }
}
```
