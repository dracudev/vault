### Navbar

- **`navbar-expand-sm`**: El navbar estará expandido a partir de pantallas **pequeñas** (576px o más).
- **`navbar-expand-md`**: El navbar estará expandido a partir de pantallas **medianas** (768px o más).
- **`navbar-expand-lg`**: El navbar estará expandido a partir de pantallas **grandes** (992px o más).
- **`navbar-expand-xl`**: El navbar estará expandido a partir de pantallas **extra grandes** (1200px o más).

```html
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">Mi Sitio</a>
  <div class="collapse navbar-collapse" id="navbarNav">
    <ul class="navbar-nav ms-auto">
      <li class="nav-item"><a class="nav-link" href="#">Inicio</a></li>
      <li class="nav-item"><a class="nav-link" href="#">Servicios</a></li>
      <li class="nav-item"><a class="nav-link" href="#">Contacto</a></li>
    </ul>
  </div>
</nav>
```

### Toggler

- **`class="navbar-toggler"`**: Aplica los estilos de Bootstrap que dan formato al botón toggler.
- **`type="button"`**: Define que es un botón.
- **`data-bs-toggle="collapse"`**: Indica que este botón está asociado con el comportamiento de colapsar/expandir el contenido.
- **`data-bs-target="#navbarNav"`**: Define cuál es el contenido que se colapsará o expandirá. El valor `#navbarNav` es el ID del contenedor del contenido (en este caso, el menú de navegación).
- **`aria-controls="navbarNav"`**: Es un atributo de accesibilidad que indica qué elemento controla el toggler.
- **`aria-expanded="false"`**: Indica el estado inicial del menú, que está colapsado (no expandido).
- **`aria-label="Toggle navigation"`**: Proporciona una etiqueta accesible para usuarios de tecnología de asistencia (como lectores de pantalla).

```html
<button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
  <span class="navbar-toggler-icon"></span>
</button>
```

### Button

- **`btn-lg`**: Crea un botón de tamaño **grande**.
- **`btn-sm`**: Crea un botón de tamaño **pequeño**.
- **`btn`**: Crea un botón de tamaño **normal** (por defecto).

- **`btn-primary`**: Indica la acción **principal** en una página.
- **`btn-secondary`**: Usado para acciones **alternativas**.
- **`btn-success`**: Indica una acción **exitosa**.
- **`btn-danger`**: Indica una acción **destructiva**.
- **`btn-warning`**: Indica una **advertencia**.
- **`btn-info`**: Indica información **adicional**.
- **`btn-light`**: Usado para acciones menos **prominentes**.
- **`btn-dark`**: Usado para un diseño más **serio** o para resaltar acciones.
- **`btn-link`**: Un botón que se comporta como un **enlace**.

