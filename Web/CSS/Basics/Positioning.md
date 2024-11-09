#### Static (default)

The default positioning. Elements flow in the document.

```css
div {
  position: static;
}
```

#### Relative

Positions an element relative to its original position.

```css
div {
  position: relative;
  top: 10px;
  left: 20px;
}
```

#### Absolute

Positions an element relative to its nearest container that **has a position other than static**.

```css
div {
  position: absolute;
  top: 0;
  right: 0;
}
```

#### Fixed

Positions an element relative to the browser window.

```css
div {
  position: fixed;
  bottom: 0;
  width: 100%;
}
```

#### Sticky

Allows an element to be treated as relative until a specific scroll position is reached, then behaves like fixed.

```css
div {
  position: sticky;
  top: 10px;
}
```