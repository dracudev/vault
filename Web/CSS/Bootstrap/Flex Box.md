### Clases de Contenedor Flex

- **`d-flex`**: Establece el contenedor como un flex container.
- **`d-inline-flex`**: Establece el contenedor como un flex container en línea.

### Dirección del Eje Principal

- **`flex-row`**: Establece la dirección del eje principal en fila (horizontal).
- **`flex-row-reverse`**: Establece la dirección del eje principal en fila invertida.
- **`flex-column`**: Establece la dirección del eje principal en columna (vertical).
- **`flex-column-reverse`**: Establece la dirección del eje principal en columna invertida.

### Alineación del Eje Principal

- **`justify-content-start`**: Alinea los elementos al inicio del contenedor.
- **`justify-content-end`**: Alinea los elementos al final del contenedor.
- **`justify-content-center`**: Centra los elementos en el contenedor.
- **`justify-content-between`**: Distribuye los elementos con espacio entre ellos.
- **`justify-content-around`**: Distribuye los elementos con espacio alrededor de ellos.
- **`justify-content-evenly`**: Distribuye los elementos con espacio igual entre ellos.

### Alineación del Eje Transversal

- **`align-items-start`**: Alinea los elementos al inicio del eje transversal.
- **`align-items-end`**: Alinea los elementos al final del eje transversal.
- **`align-items-center`**: Centra los elementos en el eje transversal.
- **`align-items-baseline`**: Alinea los elementos según su línea base.
- **`align-items-stretch`**: Estira los elementos para que ocupen todo el espacio del contenedor (por defecto).

### Alineación Vertical de Elementos Individuales

- **`align-self-start`**: Alinea un elemento individual al inicio del eje transversal.
- **`align-self-end`**: Alinea un elemento individual al final del eje transversal.
- **`align-self-center`**: Centra un elemento individual en el eje transversal.
- **`align-self-baseline`**: Alinea un elemento individual según su línea base.
- **`align-self-stretch`**: Estira un elemento individual para que ocupe todo el espacio del contenedor.

### Clases de Orden

- **`order-first`**: Coloca el elemento al inicio del contenedor.
- **`order-last`**: Coloca el elemento al final del contenedor.
- **`order-0`, `order-1`, `order-2`, ... `order-12`**: Establece el orden de los elementos en el contenedor, donde el número más bajo aparece primero.

### Clases de Espaciado

- **`g-0`, `g-1`, `g-2`, ..., `g-5`**: Establece el espaciado (gap) entre los elementos flex.

### Clases de Flex Wrap

- **`flex-nowrap`**: Impide que los elementos se envuelvan.
- **`flex-wrap`**: Permite que los elementos se envuelvan.
- **`flex-wrap-reverse`**: Envuelve los elementos en orden inverso.

### Uso en Responsividad

Puedes combinar estas clases con los modificadores de pantalla de Bootstrap para aplicar estilos en diferentes tamaños de pantalla. Por ejemplo:

- **`flex-md-row`**: Aplica `flex-row` en pantallas medianas y más grandes.
- **`align-items-sm-center`**: Aplica `align-items-center` en pantallas pequeñas y más grandes.