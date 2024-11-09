#### Grid Structure

The grid system uses 12 columns per row and is responsive.

```html
<div class="container">
  <div class="row">
    <div class="col-md-6">Column 1 (6 columns)</div>
    <div class="col-md-6">Column 2 (6 columns)</div>
  </div>
</div>
```

#### Column Classes

Bootstrap allows you to adjust the behavior of columns at different screen sizes:

- `col-`: Extra small (mobile)
- `col-sm-`: Small (screens ≥ 576px)
- `col-md-`: Medium (screens ≥ 768px)
- `col-lg-`: Large (screens ≥ 992px)
- `col-xl-`: Extra large (screens ≥ 1200px)

#### Column Alignment

- Vertical alignment:

|Clase|Descripción|
|---|---|
|`.align-items-start`|Alinea las columnas en la parte de arriba de la fila.|
|`.align-items-center`|Alinea las columnas en el centro de la fila.|
|`.align-items-end`|Alinea las columnas en la parte de abajo de la fila.|
|`.align-self-start`|Alinea individualmente una columna en la parte de arriba de la fila.|
|`.align-self-center`|Alinea individualmente una columna al centro de la fila.|
|`.align-self-end`|Alinea individualmente una columna en la parte de abajo de la fila.|
- Horizontal alignment:

|Clase|Descripción|
|---|---|
|`.justify-content-start`|Alinea las columnas al inicio de la fila.|
|`.justify-content-center`|Alinea las columnas al centro de la fila.|
|`.justify-content-end`|Alinea las columnas al final de la fila.|
|`.justify-content-between`|Distribuye el espacio entre las columnas de manera uniforme, con la primera columna al inicio y la última al final de la fila.|
|`.justify-content-around`|Distribuye el espacio alrededor de las columnas de manera uniforme.|
|`.justify-content-evenly`|Distribuye el espacio entre y alrededor de las columnas de manera uniforme.|