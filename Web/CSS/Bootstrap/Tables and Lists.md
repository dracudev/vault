### Tables

| Clase                      | Descripción                                                                                                 |
|----------------------------|-------------------------------------------------------------------------------------------------------------|
| `table`                    | Clase base para crear una tabla básica                                                                      |
| `table-striped`            | Alterna colores de fila para mejorar la legibilidad                                                         |
| `table-bordered`           | Añade bordes a las celdas de la tabla                                                                       |
| `table-borderless`         | Elimina los bordes de la tabla y las celdas                                                                 |
| `table-hover`              | Resalta las filas al pasar el ratón por encima                                                              |
| `table-active`             | Resaltar una fila o celda                                                                                   |
| `table-sm`                 | Reduce el tamaño de fuente y el espaciado de la tabla, no se ajusta al contenedor                           |
| `table-responsive`         | Hace que la tabla sea responsive. Se pone en el contenedor padre de `<table>`                               |
| `.table-responsive-{xx}`   | Hace que la tabla sea responsive en los tamaños inferiores a los siguientes:                                |
| `.table-responsive-sm`     | `< 576px`                                                                                                   |
| `.table-responsive-md`     | `< 768px`                                                                                                   |
| `.table-responsive-lg`     | `< 992px`                                                                                                   |
| `.table-responsive-xl`     | `< 1200px`                                                                                                  |
| `caption-top`              | Poner el título de la tabla arriba                                                                         |

### Tables color

| Clase               | Descripción                                                              |
|---------------------|--------------------------------------------------------------------------|
| `table-dark`        | Aplica un tema oscuro a la tabla.                                        |
| `table-light`       | Aplica un tema claro a la tabla.                                         |
| `table-primary`     | Aplica un color de fondo de estilo primario a la tabla.                  |
| `table-secondary`   | Aplica un color de fondo de estilo secundario a la tabla.                |
| `table-success`     | Aplica un color de fondo de estilo éxito a la tabla.                     |
| `table-danger`      | Aplica un color de fondo de estilo peligro a la tabla.                   |
| `table-warning`     | Aplica un color de fondo de estilo advertencia a la tabla.               |
| `table-info`        | Aplica un color de fondo de estilo informativo a la tabla.               |
| `table-light`       | Aplica un color de fondo de estilo claro a la tabla.                     |
| `table-dark`        | Aplica un color de fondo de estilo oscuro a la tabla.                    |
| `table-active`      | Resalta una fila o celda específica con un color de fondo activo.        |

### Tables color

| Clase          | Descripción                                                  |
|----------------|--------------------------------------------------------------|
| `align-middle` | Alinea el contenido verticalmente al centro de la celda.     |
| `align-top`    | Alinea el contenido verticalmente en la parte superior de la celda. |
| `align-bottom` | Alinea el contenido verticalmente en la parte inferior de la celda. |
| `text-start`   | Alinea el texto a la izquierda.                              |
| `text-center`  | Alinea el texto al centro.                                   |
| `text-end`     | Alinea el texto a la derecha.                                |

#### Table with Default Style

```html
<table class="table">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Name</th>
      <th scope="col">Email</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Luis</td>
      <td>juan@example.com</td>
    </tr>
  </tbody>
</table>
```

#### Table with Colors and Stripes

```html
<table class="table table-striped table-hover">
  <thead>
    <tr>
      <th>#</th>
      <th>Product</th>
      <th>Price</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Product A</td>
      <td>$50</td>
    </tr>
  </tbody>
</table>
```

### Lists

#### Inline List

```html
<ul class="list-inline">
  <li class="list-inline-item">Item 1</li>
  <li class="list-inline-item">Item 2</li>
  <li class="list-inline-item">Item 3</li>
</ul>
```

#### Grouped List

```html
<ul class="list-group">
  <li class="list-group-item">Item 1</li>
  <li class="list-group-item">Item 2</li>
  <li class="list-group-item">Item 3</li>
</ul>
```



