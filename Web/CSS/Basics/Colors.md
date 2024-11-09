#### Color Formats

|**Format**|**Description**|**Example**|
|---|---|---|
|`Hex`|Hexadecimal representation of colors.|`#ff5733` (red)|
|`RGB`|Color values in red, green, and blue.|`rgb(255, 87, 51)`|
|`RGBA`|Similar to RGB, but includes the alpha channel for opacity.|`rgba(255, 87, 51, 0.5)`|
|`HSL`|Color representation based on hue, saturation, and lightness.|`hsl(9, 100%, 60%)`|
|`HSLA`|Similar to HSL, but includes the alpha channel.|`hsla(9, 100%, 60%, 0.5)`|

#### Color Mixing

`color-mix()` allows mixing two colors in a specific proportion, generating a new color from them.

```css
element {
  color:  color-mix(in srgb, var(--my-color), #0000 75%); 
}
```

#### Defining Color from Another

`color(from)` defines a color from a specific color model (like `srgb`, `hsl`, etc.).

```css
element {
  color: hsl(from var(--my-color) h 52% 45%);
}
```