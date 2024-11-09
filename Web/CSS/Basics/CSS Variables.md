#### Defining Variables

Allow defining reusable values. They must start with `--`.

```css
:root {
  --main-color: #3498db;
}
```

#### Accessing Variables

Use the `var()` function.

```css
h1 {
  color: var(--main-color);
}
```