### Width

- **`w-25`**: 25% del ancho.
- **`w-50`**: 50% del ancho.
- **`w-75`**: 75% del ancho.
- **`w-100`**: 100% del ancho (toma todo el ancho disponible).
- **`w-auto`**: El ancho automático basado en el contenido.
- **`w-sm-50`**: El ancho será del **50%** en pantallas pequeñas (576px) o mayores.
- **`w-md-75`**: El ancho será del **75%** en pantallas medianas (768px) o mayores.
- **`w-lg-100`**: El ancho será del **100%** en pantallas grandes (992px) o mayores.

- `min-w-100`: El ancho mínimo será del 100%.
- `min-w-75`: El ancho mínimo será del 75%.
- `min-w-50`: El ancho mínimo será del 50%.
- `min-w-25`: El ancho mínimo será del 25%.

### Margin

	m{lado}-{tamaño}-{valor}

- **`m`**: Es la abreviatura de `margin`.
- **`lado`**: El lado donde quieres aplicar el margen:
    - `t` para margen superior (top).
    - `b` para margen inferior (bottom).
    - `s` para margen izquierdo (start, anteriormente `l` en Bootstrap 4).
    - `e` para margen derecho (end, anteriormente `r` en Bootstrap 4).
    - `x` para márgenes izquierdo y derecho.
    - `y` para márgenes superior e inferior.
    - Sin lado para aplicar el margen a los cuatro lados.
- **`tamaño`**: El tamaño de pantalla en el que deseas aplicar el margen:
    - `sm` para pantallas pequeñas.
    - `md` para pantallas medianas.
    - `lg` para pantallas grandes.
    - `xl` para pantallas extra grandes.
    - Sin tamaño si se quiere que el margen se aplique a todas las pantallas.
- **`valor`**: La cantidad de margen que quieres aplicar (del 0 al 5, o `auto`):
    - `0` significa sin margen.
    - `1` a `5` aumenta el margen progresivamente.
    - `auto` para márgenes automáticos.

### Padding

- **`p-*`**: Relleno (padding) en todos los lados.
- **`pt-*`**: Relleno superior (padding-top).
- **`pr-*`**: Relleno derecho (padding-right).
- **`pb-*`**: Relleno inferior (padding-bottom).
- **`pl-*`**: Relleno izquierdo (padding-left).

### Display

- **`d-none`**: Oculta el elemento completamente (display: none).
- **`d-inline`**: Muestra el elemento como un elemento en línea (display: inline).
- **`d-inline-block`**: Muestra el elemento como un bloque en línea (display: inline-block).
- **`d-block`**: Muestra el elemento como un bloque (display: block).
- **`d-flex`**: Aplica un contenedor flex (display: flex).
	- **`justify-content-end`**
	- **`justify-content-center`**
- **`d-grid`**: Aplica un contenedor de cuadrícula (display: grid).

### Border

- **`border-0`**: Esta clase elimina el borde del botón toggler.
- **`border`**: Añade un borde en todos los lados del elemento.
- **`border-top`**: Añade un borde solo en la parte superior.
- **`border-end`**: Añade un borde solo en el lado derecho (final).
- **`border-bottom`**: Añade un borde solo en la parte inferior.
- **`border-start`**: Añade un borde solo en el lado izquierdo (inicio)

- **`border-primary`**: Borde primario.
- **`border-secondary`**: Borde secundario.
- **`border-success`**: Borde de éxito.
- **`border-danger`**: Borde de peligro.
- **`border-warning`**: Borde de advertencia.
- **`border-info`**: Borde de información.
- **`border-light`**: Borde claro.
- **`border-dark`**: Borde oscuro.
- **`border-white`**: Borde blanco.

- **`rounded`**: Bordes redondeados en todos los lados.
- **`rounded-top`**: Bordes redondeados en la parte superior.
- **`rounded-end`**: Bordes redondeados en el lado derecho (final).
- **`rounded-bottom`**: Bordes redondeados en la parte inferior.
- **`rounded-start`**: Bordes redondeados en el lado izquierdo (inicio).
- **`rounded-circle`**: Bordes completamente redondeados, creando un círculo.
- **`rounded-pill`**: Bordes en forma de píldora (más ovalados).

- **`border-top-0`**, **`border-end-0`**, **`border-bottom-0`**, **`border-start-0`**: Elimina el borde en el lado especificado.

(Para que funcione la opacity debes ponerle un color al borde)
- **`border-opacity-0`**: Opacidad del 0% (completamente transparente).
- **`border-opacity-10`**: Opacidad del 10%.
- **`border-opacity-25`**: Opacidad del 25%.
- **`border-opacity-50`**: Opacidad del 50%.
- **`border-opacity-75`**: Opacidad del 75%.
- **`border-opacity-100`**: Opacidad del 100% (completamente visible).

### Color

- **`text-primary`**: Color primario.
- **`text-secondary`**: Color secundario.
- **`text-success`**: Color de éxito.
- **`text-danger`**: Color de peligro.
- **`text-warning`**: Color de advertencia.
- **`text-info`**: Color de información.
- **`text-light`**: Color claro (usualmente en un fondo oscuro).
- **`text-dark`**: Color oscuro (usualmente en un fondo claro).
- **`text-white`**: Color blanco.

### Font

- **`fs-1`**: Tamaño de fuente muy grande.
- **`fs-2`**: Tamaño de fuente grande.
- **`fs-3`**: Tamaño de fuente mediano.
- **`fs-4`**: Tamaño de fuente ligeramente pequeño.
- **`fs-5`**: Tamaño de fuente pequeño.
- **`fs-6`**: Tamaño de fuente muy pequeño.

- **`text-primary`**: Aplica el color principal (azul por defecto).
- **`text-secondary`**: Aplica un color secundario (gris por defecto).
- **`text-success`**: Aplica un color verde.
- **`text-danger`**: Aplica un color rojo.
- **`text-warning`**: Aplica un color amarillo.
- **`text-info`**: Aplica un color azul claro.
- **`text-light`**: Aplica un color blanco claro (puede no ser visible en fondos claros).
- **`text-dark`**: Aplica un color negro.
- **`text-white`**: Aplica un color blanco

- **`fw-normal`**: Establece el peso de fuente en normal (400).
- **`fw-bold`**: Establece el peso de fuente en negrita (700).
- **`fw-bolder`**: Establece el peso de fuente en bolder (más pesado que el elemento padre).
- **`fw-lighter`**: Establece el peso de fuente en lighter (más ligero que el elemento padre).
- **`fw-100`**: Establece el peso de fuente en 100 (extremadamente ligero).
- **`fw-200`**: Establece el peso de fuente en 200.
- **`fw-300`**: Establece el peso de fuente en 300.
- **`fw-400`**: Establece el peso de fuente en 400 (normal).
- **`fw-500`**: Establece el peso de fuente en 500.
- **`fw-600`**: Establece el peso de fuente en 600.
- **`fw-700`**: Establece el peso de fuente en 700 (negrita).
- **`fw-800`**: Establece el peso de fuente en 800.
- **`fw-900`**: Establece el peso de fuente en 900 (muy pesado).

- **`text-start`**: Alinea el texto a la izquierda.
- **`text-center`**: Centra el texto.
- **`text-end`**: Alinea el texto a la derecha.
- **`text-sm-start`**: Alinea el texto a la izquierda en pantallas pequeñas (`sm`) en adelante.
### Background

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

