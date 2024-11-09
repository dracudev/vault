### Dynamic Pseudo-classes

Dynamic pseudo-classes affect elements based on their **interactive state**.

Applies styles when the user hovers over the element.

```css
button:hover {
  background-color: blue;
}
```

Applies styles when the element has received focus, typically in forms.

```css
input:focus {
  border-color: green;
}
```

Applies styles while the element is being activated (for example, when clicked).

```css
a:active {
  color: red;
}
```

### Structural Pseudo-classes

Selects the first child of its container.

```css
p:first-child {
  font-weight: bold;
}
```

Selects the last child of its container.

```css
li:last-child {
  color: red;
}
```

#### (n)

Selects the nth child, where `n` can be a number, a formula, or a keyword.

```css
tr:nth-child(odd) {
  background-color: #eee;
}
```

This selector affects the odd rows (`odd`) of a table.

#### (n)

Selects the nth child of the same type of element.

```css
p:nth-of-type(2) {
  font-size: 20px;
}
```

This selector affects the second paragraph within a container, regardless of other types of elements.

### Negation Pseudo-class

#### (selector)

Selects elements that **do not** match the specified selector.

```css
input:not([type="submit"]) {
  border: 1px solid grey;
}
```

This selector affects all input fields (`<input>`) that **do not** have the `type="submit"` attribute.

Here is the paragraph for the pseudo-class `:has()` in a CSS cheatsheet:

#### (selector)

Selects elements that **contain** at least one element that matches the specified selector.

```css
div:has(> p) {
  background-color: lightblue;
}
```

This selector applies a light blue background to all `<div>` elements that **contain** at least one paragraph (`<p>`) as a direct child.

## Pseudo-elements

#### ::before and ::after

Allow inserting content before or after the content of an element.

```css
h1::before {
  content: "★ ";
  color: gold;
}
```

This selector adds a star before the content of all `<h1>` elements.

```css
p::after {
  content: " ➜";
  color: blue;
}
```

This selector adds an arrow after the content of all `<p>` elements.

#### ::first-letter and ::first-line

**`::first-letter`:** Selects the first letter of a block element.

```css
p::first-letter {
  font-size: 2em;
  color: red;
}
```

**`::first-line`:** Selects the first line of text in an element.

```css
p::first-line {
  font-weight: bold;
}
```