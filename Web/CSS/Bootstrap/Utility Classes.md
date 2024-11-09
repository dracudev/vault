### Spacing

Spacing classes allow you to control the margins and padding of elements. You can use classes that affect all sides or just one or two specific sides.

### Width

- **`w-25`**: 25% del ancho.
- **`w-50`**: 50% del ancho.
- **`w-75`**: 75% del ancho.
- **`w-100`**: 100% del ancho (toma todo el ancho disponible).
- **`w-auto`**: El ancho automático basado en el contenido.
- **`w-sm-50`**: El ancho será del **50%** en pantallas pequeñas (576px) o mayores.
- **`w-md-75`**: El ancho será del **75%** en pantallas medianas (768px) o mayores.
- **`w-lg-100`**: El ancho será del **100%** en pantallas grandes (992px) o mayores.
- `min-w-100`: El ancho mínimo será del 100%.
- `min-w-75`: El ancho mínimo será del 75%.
- `min-w-50`: El ancho mínimo será del 50%.
- `min-w-25`: El ancho mínimo será del 25%.

#### Margins & Padding

Margin classes: `m-{t|b|l|r|x|y}-{breakpoint}-{size}`

- **`t`**: Top
- **`b`**: Bottom
- **`l`**: Left
- **`r`**: Right
- **`x`**: Horizontal (left and right)
- **`y`**: Vertical (top and bottom)

Breakpoints: `sm`, `md`, `lg`, `xl`, `xxl` to apply margins at different screen sizes.

Sizes: Values from `0` to `5`, where `0` removes the margin and `5` applies the maximum.

```html
<div class="m-3">Margin on all sides</div>
<div class="mt-3 mb-3">Margin top and bottom of 3</div>
<div class="mx-auto">Horizontal center</div>
```

|Clase|Descripción|
|---|---|
|`.p-0` `.py-0` `.px-0`|Aplica un padding de 0 (sin padding) a todos los lados (.p-0), solo verticalmente (.py-0) o solo horizontalmente (.px-0).|
|`.p-1` `.py-1` `.px-1`|Aplica un padding pequeño a todos los lados (.p-1), solo verticalmente (.py-1) o solo horizontalmente (.px-1).|
|`.p-2` `.py-2` `.px-2`|Aplica un padding mediano a todos los lados (.p-2), solo verticalmente (.py-2) o solo horizontalmente (.px-2).|
|`.p-3` `.py-3` `.px-3`|Aplica un padding grande a todos los lados (.p-3), solo verticalmente (.py-3) o solo horizontalmente (.px-3).|
|`.p-4` `.py-4` `.px-4`|Aplica un padding extra grande a todos los lados (.p-4), solo verticalmente (.py-4) o solo horizontalmente (.px-4).|
|`.p-5` `.py-5` `.px-5`|Aplica un padding gigante a todos los lados (.p-5), solo verticalmente (.py-5) o solo horizontalmente (.px-5).|
|`.m-0` `.my-0` `.mx-0`|Aplica un margin de 0 (sin margen) a todos los lados (.m-0), solo verticalmente (.my-0) o solo horizontalmente (.mx-0).|
|`.m-1` `.my-1` `.mx-1`|Aplica un margin pequeño a todos los lados (.m-1), solo verticalmente (.my-1) o solo horizontalmente (.mx-1).|
|`.m-2` `.my-2` `.mx-2`|Aplica un margin mediano a todos los lados (.m-2), solo verticalmente (.my-2) o solo horizontalmente (.mx-2).|
|`.m-3` `.my-3` `.mx-3`|Aplica un margin grande a todos los lados (.m-3), solo verticalmente (.my-3) o solo horizontalmente (.mx-3).|
|`.m-4` `.my-4` `.mx-4`|Aplica un margin extra grande a todos los lados (.m-4), solo verticalmente (.my-4) o solo horizontalmente (.mx-4).|
|`.m-5` `.my-5` `.mx-5`|Aplica un margin gigante a todos los lados (.m-5), solo verticalmente (.my-5) o solo horizontalmente (.mx-5).|
|`.m-t` `.p-t`|Aplica margin-top o padding-top, dependiendo de la propiedad que utilices (.m para margin y .p para padding).|
|`.m-b` `.p-b`|Aplica margin-bottom o padding-bottom, dependiendo de la propiedad que utilices (.m-b para margin y .p-b para padding).|
|`.m-s` `.p-s`|Aplica margin-left o un padding-left.|
|`.m-e` `.p-e`|Aplica margin-right o un padding-right.|
|`.m-x` `.p-x`|Aplica tanto margin-left como margin-right o padding-right y padding-left.|
|`.m-y` `.p-y`|Aplica tanto margin-top y margin-bottom como padding-top y padding-bottom.|
|`.m-auto`, `.p-auto`|Aplica margin o padding en los cuatro lados del elemento y establece el valor «auto» para la propiedad, lo que permite centrar horizontalmente el elemento en el contenedor.|

### Alignment

Alignment classes allow you to easily align text and elements.

- `text-left`: Left alignment
- `text-center`: Center alignment
- `text-right`: Right alignment
- `text-justify`: Justified text

```html
<p class="text-center">Centered text</p>
<p class="text-right">Right-aligned text</p>
```

Alignment of flexible elements (using Flexbox):

- `align-items-start`: Align to start
- `align-items-center`: Align to center
- `align-items-end`: Align to end
- `justify-content-between`: Space between elements

```html
<div class="d-flex justify-content-between">
  <div>Item 1</div>
  <div>Item 2</div>
</div>
```

### Background Colors

You can apply background colors to elements using Bootstrap’s predefined classes.

Background classes: `bg-{color}`

- **`bg-opacity-0`**: Opacidad del 0% (completamente transparente).
- **`bg-opacity-10`**: Opacidad del 10%.
- **`bg-opacity-25`**: Opacidad del 25%.
- **`bg-opacity-50`**: Opacidad del 50%.
- **`bg-opacity-75`**: Opacidad del 75%.
- **`bg-opacity-100`**: Opacidad del 100% (completamente visible).

- **`bg-primary`**: Fondo primario.
- **`bg-secondary`**: Fondo secundario.
- **`bg-success`**: Fondo de éxito.
- **`bg-danger`**: Fondo de peligro.
- **`bg-warning`**: Fondo de advertencia.
- **`bg-info`**: Fondo de información.
- **`bg-light`**: Fondo claro.
- **`bg-dark`**: Fondo oscuro.
- **`bg-white`**: Fondo blanco

```html
<div class="bg-primary text-white">Blue background</div>
<div class="bg-danger text-white">Red background</div>
<div class="bg-light text-dark">Light background</div>
```

### Typography and Texts

Bootstrap provides several classes to adjust typography and text styling.

#### Headings

- Use heading classes for predefined styles.

```html
<h1 class="display-1">Large Heading</h1>
<h2 class="display-2">Medium Heading</h2>
<h3 class="display-3">Small Heading</h3>
```

#### Text Alignment

In addition to text alignment, you can apply other formatting classes.

```html
<p class="text-center">Centered text</p>
<p class="text-right">Right-aligned text</p>
```

#### Text Colors

Text classes: `text-{color}`

- Available colors: `primary`, `secondary`, `success`, `danger`, `warning`, `info`, `light`, `dark`, `muted`, `white`.

```html
<p class="text-primary">Primary text</p>
<p class="text-danger">Red text</p>
<p class="text-muted">Muted text</p>
```

#### Font Change

Bootstrap offers classes to change font style.

- `font-weight-bold`: Bold
- `font-weight-light`: Light
- `font-italic`: Italic
- `font-monospace`: Monospace font

```html
<p class="font-weight-bold">Bold text</p>
<p class="font-italic">Italic text</p>
<p class="font-monospace">Text with monospace font</p>
```

#### Visibility

Control the visibility of elements at different screen sizes.

Visibility classes: `d-{breakpoint}-{value}`

- `d-none`: Hides the element
- `d-block`: Shows the element as block
- `d-inline`: Shows the element inline

```html
<div class="d-none d-md-block">Visible only on medium screens and above</div>
```

#### Borders

Apply classes to control border styles.

`border`, `border-{color}`, `rounded`, `rounded-{size}`

```html
<div class="border border-primary rounded">Div with blue border and rounded corners</div>
```

|Clase|Descripción|
|---|---|
|`.rounded`|Agrega bordes redondeados a todos los lados del elemento.|
|`.rounded-top`|Agrega bordes redondeados solo a la parte superior del elemento.|
|`.rounded-end`|Agrega bordes redondeados solo al extremo derecho del elemento (depende de la dirección del texto).|
|`.rounded-bottom`|Agrega bordes redondeados solo a la parte inferior del elemento.|
|`.rounded-start`|Agrega bordes redondeados solo al extremo izquierdo del elemento (depende de la dirección del texto).|
|`.rounded-circle`|Crea un borde redondeado para hacer que el elemento tenga forma de círculo.|
|`.rounded-0`|Elimina los bordes redondeados para que el elemento tenga esquinas cuadradas.|
|`.rounded-*`|Agrega esquina redondeada. El tamaño va de .rounded-1 (menor redondeo) a rounded 3.|
|`.border`|Agrega un borde al elemento.|
|`.border-0`|Elimina el borde del elemento.|
|`.border-*`|Agrega un borde de grosor 1, 2, 3, 4 o 5. Siendo .border-1 el grosor menor.|
|`.border-top`|Agrega un borde solo en la parte superior del elemento.|
|`.border-end`|Agrega un borde solo en el extremo derecho del elemento (depende de la dirección del texto).|
|`.border-bottom`|Agrega un borde solo en la parte inferior del elemento.|
|`.border-start`|Agrega un borde solo en el extremo izquierdo del elemento (depende de la dirección del texto).|
|`.border-primary`|Agrega un borde de color primario al elemento.|
|`.border-secondary`|Agrega un borde de color secundario al elemento.|
|`.border-success`|Agrega un borde de color de éxito al elemento.|
|`.border-danger`|Agrega un borde de color de peligro o error al elemento.|
|`.border-warning`|Agrega un borde de color de advertencia al elemento.|
|`.border-info`|Agrega un borde de color de información al elemento.|
|`.border-light`|Agrega un borde de color claro al elemento.|
|`.border-dark`|Agrega un borde de color oscuro al elemento.|
|`.border-white`|Agrega un borde de color blanco al elemento.|
#### Shadows

Add shadows to elements for greater depth.

`shadow`, `shadow-sm`, `shadow-lg`

```html
<div class="shadow">Div with normal shadow</div>
<div class="shadow-lg">Div with large shadow</div>
```