### Syntax

```ts
const handleEvent = (event: React.MouseEvent<HTMLButtonElement>) => {
  event.preventDefault();
  console.log(event.target);
};
```

| **Category**       | **Event Name**        | **React Type**                  | **HTML Elements**                        |
|---------------------|-----------------------|----------------------------------|------------------------------------------|
| **Mouse Events**    | `onClick`            | `React.MouseEvent`              | `button`, `div`, `a`, etc.               |
|                     | `onDoubleClick`      | `React.MouseEvent`              | `button`, `div`, `a`, etc.               |
|                     | `onMouseEnter`       | `React.MouseEvent`              | Any HTML element                         |
|                     | `onMouseLeave`       | `React.MouseEvent`              | Any HTML element                         |
|                     | `onMouseMove`        | `React.MouseEvent`              | Any HTML element                         |
|                     | `onMouseDown`        | `React.MouseEvent`              | Any HTML element                         |
|                     | `onMouseUp`          | `React.MouseEvent`              | Any HTML element                         |
| **Keyboard Events** | `onKeyPress`         | `React.KeyboardEvent`           | `input`, `textarea`, etc.                |
|                     | `onKeyDown`          | `React.KeyboardEvent`           | `input`, `textarea`, etc.                |
|                     | `onKeyUp`            | `React.KeyboardEvent`           | `input`, `textarea`, etc.                |
| **Focus Events**    | `onFocus`            | `React.FocusEvent`              | `input`, `textarea`, `button`, etc.      |
|                     | `onBlur`             | `React.FocusEvent`              | `input`, `textarea`, `button`, etc.      |
| **Form Events**     | `onSubmit`           | `React.FormEvent`               | `form`                                   |
|                     | `onChange`           | `React.ChangeEvent`             | `input`, `textarea`, `select`, etc.      |
|                     | `onInput`            | `React.FormEvent`               | `input`, `textarea`                      |
| **Clipboard Events**| `onCopy`             | `React.ClipboardEvent`          | `input`, `textarea`, etc.                |
|                     | `onPaste`            | `React.ClipboardEvent`          | `input`, `textarea`, etc.                |
|                     | `onCut`              | `React.ClipboardEvent`          | `input`, `textarea`, etc.                |
| **Drag Events**     | `onDrag`             | `React.DragEvent`               | Any draggable HTML element               |
|                     | `onDragStart`        | `React.DragEvent`               | Any draggable HTML element               |
|                     | `onDragEnd`          | `React.DragEvent`               | Any draggable HTML element               |
|                     | `onDrop`             | `React.DragEvent`               | Droppable areas                          |
| **Wheel Events**    | `onWheel`            | `React.WheelEvent`              | Any scrollable or wheel-detectable element |
| **Touch Events**    | `onTouchStart`       | `React.TouchEvent`              | Touch-capable elements                   |
|                     | `onTouchMove`        | `React.TouchEvent`              | Touch-capable elements                   |
|                     | `onTouchEnd`         | `React.TouchEvent`              | Touch-capable elements                   |
| **Media Events**    | `onPlay`             | `React.SyntheticEvent`          | `audio`, `video`                         |
|                     | `onPause`            | `React.SyntheticEvent`          | `audio`, `video`                         |
|                     | `onEnded`            | `React.SyntheticEvent`          | `audio`, `video`                         |
|                     | `onTimeUpdate`       | `React.SyntheticEvent`          | `audio`, `video`                         |
| **General Events**  | `onScroll`           | `React.UIEvent`                 | Scrollable elements                      |
|                     | `onResize`           | `React.UIEvent`                 | Window or resizable containers           |
