The box model in CSS defines how an element’s dimensions and spacing are calculated.

|Property|Description|
|---|---|
|`width`|Width of the content|
|`height`|Height of the content|
|`padding`|Inner space between the content and the border|
|`border`|Border around the element|
|`margin`|Outer space around the border|

#### Using CSS Resets

They are used to eliminate inconsistent default styles across browsers.

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```