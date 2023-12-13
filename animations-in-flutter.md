# Animations in Flutter

Welcome to the Animations in Flutter guide! In this section, we'll explore animation concepts and how to implement them in Flutter.

## Overview of Animations in Flutter

Animations add life and interactivity to your Flutter apps. Flutter provides a rich set of tools for creating smooth and engaging animations.

### Animation Controllers

The `AnimationController` class is used to control animations. It allows you to define the animation duration, start, stop, and reverse animations.

```dart
AnimationController controller = AnimationController(
  duration: Duration(seconds: 2),
  vsync: this, // TickerProvider
);

Animation<double> animation = Tween<double>(begin: 0, end: 1).animate(controller);
```

### Tweens and Curves
Tween objects define the range of values for an animation, and Curves define the rate of change of an animation.

```dart
Animation<double> animation = Tween<double>(begin: 0, end: 1).animate(controller);

// Applying a curve
animation = CurvedAnimation(parent: controller, curve: Curves.easeInOut);
```

### Examples of Common Animations
Fade Animation

```dart
FadeTransition(
  opacity: animation,
  child: YourWidget(),
)
```
Slide Animation

```dart
SlideTransition(
  position: Tween<Offset>(begin: Offset(-1, 0), end: Offset(0, 0)).animate(controller),
  child: YourWidget(),
)
```
