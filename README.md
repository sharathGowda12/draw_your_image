# draw_your_image

draw_your_image is a Flutter package for drawing picture with fingers.

# Demo

![Demo](https://github.com/chooyan-eng/draw_your_image/raw/main/assets/draw_sample.gif)

# Note

Though this package is available with a couple of features, it's still under development. Any feedbacks or bug reports, and off course Pull Requests, are welcome. Feel free to visit the GitHub repository below.

[https://github.com/chooyan-eng/draw_your_image](https://github.com/chooyan-eng/draw_your_image)

# Usage

## Basic

### Draw

The very first step for draw_your_image is to place `Draw` widget at anywhere you want in the widget tree.

```dart
final _controller = DrawController();

@override
Widget build(BuildContext context) {
    return Draw(
        controller: _controller,
        backgroundColor: Colors.blue.shade50,
        strokeColor: Colors.red,
        strokeWidth: 8,
        isErasing: false,
    );
}
```

`Draw` widget would display a simple canvas which users can draw whatever they want with given `strokeColor` and `strokeWidth`.

`isErasing` is a flag for erasing drawn strokes. If `true`, new strokes will erase drawn strokes.

If you change colors or width, you can simply manage states representing them in your widgets, maybe `StatefulWidgets`, and path it to the properties of `Draw`.

For `undo()`, `redo()` or other actions, pass instance of `DrawController` and pass it to `controller` property. See `DrawController` section below for detail.

### DrawController

`DrawController` provides interfaces to control canvas. Below are provided methods

- `undo()` will undo the last stroke. It returns `false` if no stroke can be performed.
- `redo()` will redo the last performed undo stroke. It returns `false` if no stroke can be performed.