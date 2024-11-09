**Selectors** in CSS are essential for targeting the HTML elements to which we want to apply styles.

### Basic Selectors

#### Type Selector (element)

Selects all elements of a specific type.

```css
p {
  color: blue;
}
```

#### Class Selector*

Selects any element with a specific class. Classes are identified with a dot (`.`) followed by the class name.

```css
.button {
  background-color: green;
}
```

**Note** A single element can have multiple classes.

```html
<div class="button primary large"></div>
```

#### ID Selector

Selects a single element that has a specific ID. IDs are identified with a hash symbol (`#`).

```css
#header {
  background-color: red;
}
```

#### Universal Selector

Selects **all** elements in the document.

```css
* {
  margin: 0;
  padding: 0;
}
```

This selector is useful for applying general styles to all elements, such as a CSS reset, removing default margins and padding.

#### Group Selector

Allows grouping multiple selectors to apply the same style to multiple elements.

```css
h1, h2, h3 {
  font-family: Arial, sans-serif;
}
```

### Combinator Selectors

#### Descendant Selector (indirect child)

Selects all elements that **are inside** another element (descendants).

```css
div p {
  color: blue;
}
```

This selector selects all paragraphs (`<p>`) that are descendants of a `<div>` container.

#### Direct Child Selector

Selects only the elements that are **direct children** of an element.

```css
ul > li {
  list-style-type: none;
}
```

This selector only affects `<li>` elements that are direct children of a `<ul>`, ignoring deeper descendants.

#### General Sibling Selector

Selects any element that is a **sibling** of another, meaning they share the same parent and appear afterwards.

```css
h1 ~ p {
  color: green;
}
```

This selector selects all paragraphs (`<p>`) that are siblings of an `<h1>` and appear after it in the HTML.

#### Adjacent Sibling Selector

Selects the **immediate sibling** of an element.

```css
h1 + p {
  color: red;
}
```

This selector affects the first paragraph (`<p>`) that appears immediately after an `<h1>`.

### Attribute Selectors

Attribute selectors allow selecting elements based on specific HTML attributes and their values.

#### Basic Attribute Selector

Selects elements that have a specific attribute.

```css
input[type="text"] {
  border: 1px solid black;
}
```

This selector will affect any `<input>` that has the attribute `type="text"`.

#### Partial Value Attribute Selector

- **`[attr^="value"]`:** Selects elements whose attribute value **starts** with “value”.
- **`[attr$="value"]`:** Selects elements whose attribute value **ends** with “value”.
- **`[attr*="value"]`:** Selects elements whose attribute value **contains** “value”.

```css
a[href^="https"] {
  color: green;
}
```

In this example, any link (`<a>`) whose `href` attribute starts with `"https"` will be displayed in green.

#### Space-separated Value Attribute Selector

Selects elements whose attribute contains a list of space-separated values, where one of the values matches.

```css
[class~="highlight"] {
  background-color: yellow;
}
```

This selector will affect any element whose class includes “highlight” within a list of classes.

#### Hyphen-separated Value Attribute Selector

Selects elements whose attributes contain hyphen-separated values, and selects those that start with the specified value.

```css
[lang|="en"] {
  font-style: italic;
}
```

This selector selects elements whose `lang` attribute starts with “en”, such as `en-US` or `en-GB`.