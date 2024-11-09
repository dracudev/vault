Containers are elements that encapsulate content and are essential for the grid system. You can use two types of containers:

#### Fixed Container

Has a maximum width that adapts to different screen sizes.

```html
<div class="container">
<!-- Content -->
</div>
```

#### Fluid Container

Takes up 100% of the width.

```html
<div class="container-fluid">
  <!-- Content -->
</div>
```

#### Rows

Rows (`.row`) are necessary to group columns (`.col`). The grid system is based on 12 columns.

```html
<div class="container">
  <div class="row">
    <div class="col-md-6">Column 1</div>
    <div class="col-md-6">Column 2</div>
  </div>
</div>
```