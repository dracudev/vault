# 📄 HTML

## ✅ Fundamentos explicados

---

### 1. Estructura básica de un documento HTML

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Título de la página</title>
  </head>
  <body>
    <!-- Contenido va aquí -->
  </body>
</html>
```

- `<!DOCTYPE html>` indica el tipo de documento (HTML5).
    
- `<meta charset="UTF-8">` evita problemas con acentos y ñ.
    
- `<meta viewport>` es clave para responsive design.
    

---

### 2. Etiquetas semánticas

Usa etiquetas con significado para mejorar accesibilidad y SEO:

- `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`.
    
- `<h1>` a `<h6>`: jerarquía de títulos.
    
- `<p>`, `<ul>`, `<ol>`, `<li>`, `<a>`, `<img>`, `<strong>`, `<em>`.
    

Ejemplo:

```html
<article>
  <h2>Noticia</h2>
  <p>Texto de la noticia...</p>
</article>
```

---

### 3. Atributos comúnmente usados

- `class`: para estilos y JS.
    
- `id`: identificador único (evitar en exceso).
    
- `src`, `href`, `alt`, `target`, `rel`, `type`, `value`.
    
- `aria-*`: para accesibilidad.
    

---

### 4. Formularios y accesibilidad

```html
<form action="/enviar" method="POST">
  <label for="email">Correo:</label>
  <input type="email" id="email" name="email" required />
  <button type="submit">Enviar</button>
</form>
```

- Usa `label` asociado a `input` con `for`/`id`.
    
- Usa `required`, `type`, `placeholder` correctamente.
    
- Considera atributos `aria-label`, `aria-describedby`.
    

---

### 5. Buenas prácticas

- Usa etiquetas semánticas, no `<div>` para todo.
    
- Valida HTML en [https://validator.w3.org](https://validator.w3.org/).
    
- No anides `h1` dentro de otro `h1`, mantén jerarquía clara.
    
- Siempre usa `alt` en las imágenes.
    

---

## 🎯 Preguntas comunes de entrevista

### 🧠 ¿Cuál es la diferencia entre HTML y HTML5?

> HTML5 es la versión moderna con soporte para audio/video, nuevas etiquetas semánticas, `localStorage`, y mejor estructura.

### 🧠 ¿Para qué sirven las etiquetas semánticas?

> Dan significado al contenido, mejoran la accesibilidad y el SEO.

### 🧠 ¿Qué es la accesibilidad web?

> Diseñar para que personas con distintas capacidades puedan navegar la web. Ej: `alt`, `aria-*`, buen contraste, etiquetas claras.

### 🧠 ¿Diferencia entre `id` y `class`?

> `id` es único, `class` puede repetirse. En CSS, `#id` tiene mayor especificidad.

### 🧠 ¿Cuáles son los tipos de input más comunes?

> `text`, `email`, `password`, `checkbox`, `radio`, `file`, `date`, `number`, `submit`.

### 🧠 ¿Cuándo usar `target="_blank"` y cuáles son sus riesgos?

> Para abrir enlaces en nueva pestaña. Se recomienda usar `rel="noopener noreferrer"` por seguridad.

---

## 🧠 Tips para ti

- Si te preguntan por SEO, menciona el uso correcto de `<title>`, etiquetas `<h1>`, semánticas, `alt` y estructura clara.
    
- Accesibilidad: habla de `aria-label`, contraste de color, focus visible.
    
- Practica montando una página desde cero con etiquetas semánticas, formulario y enlaces internos.
    

# 🎨 CSS

## ✅ Fundamentos explicados

---

### 1. Selectores y especificidad

#### 🔹 Selectores básicos

- `elemento`: selecciona todos los elementos de ese tipo (`p`, `h1`, etc).
    
- `.clase`: selecciona elementos con esa clase.
    
- `#id`: selecciona un elemento con ese ID (⚠️ evita usar muchos `id` para estilos).
    

#### 🔹 Combinadores

- `div p`: selecciona todos los `p` dentro de un `div`.
    
- `div > p`: selecciona solo los hijos directos.
    
- `div + p`: selecciona el `p` inmediatamente siguiente a un `div`.
    

#### 🔹 Pseudo-clases y pseudo-elementos

- `:hover`, `:focus`, `:nth-child()`, `:first-of-type`.
    
- `::before`, `::after` para insertar contenido decorativo.
    

#### 🔹 Especificidad

- `#id` > `.clase` > `elemento`.
    
- Inline styles (`style=""`) > todo lo anterior.
    
- `!important` lo sobrescribe todo, pero se recomienda evitarlo.
    

---

### 2. Modelo de Caja (Box Model)

Cada elemento en CSS es una “caja”:

```
| margin |
| border |
| padding |
| content |
```

- `box-sizing: content-box` (por defecto): padding y border se **suman** al ancho.
    
- `box-sizing: border-box`: el ancho incluye padding y border (👈 **usa siempre este por defecto**).
    

```css
* {
  box-sizing: border-box;
}
```

---

### 3. Posicionamiento

#### Valores comunes:

- `static`: por defecto. Sigue el flujo del documento.
    
- `relative`: se posiciona respecto a sí mismo, pero mantiene su espacio.
    
- `absolute`: respecto al ancestro con `relative`, `absolute` o `fixed`.
    
- `fixed`: respecto a la ventana (viewport).
    
- `sticky`: actúa como `relative`, pero se vuelve `fixed` al hacer scroll.
    

```css
.card {
  position: absolute;
  top: 0;
  left: 0;
}
```

---

### 4. Flexbox

**Sistema de maquetación en una dimensión (fila o columna).**

```css
.container {
  display: flex;
  justify-content: center; /* eje horizontal */
  align-items: center;     /* eje vertical */
}
```

#### Propiedades clave:

- `flex-direction`: `row`, `row-reverse`, `column`, `column-reverse`.
    
- `justify-content`: alinea horizontalmente.
    
- `align-items`: alinea verticalmente.
    
- `gap`: espacio entre elementos.
    
- `flex-wrap`: permite que los hijos bajen de línea si no caben.
    

---

### 5. Grid

**Sistema bidimensional** (columnas y filas).

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
}
```

#### Propiedades útiles:

- `grid-template-rows`
    
- `grid-column`, `grid-row`
    
- `grid-area`
    
- `place-items`
    

---

### 6. Responsive Design

- Media queries: adaptan el diseño a distintos tamaños de pantalla.
    

```css
@media (max-width: 768px) {
  .container {
    flex-direction: column;
  }
}
```

- Unidades relativas: `%`, `em`, `rem`, `vw`, `vh`.
    
- Enfoque mobile-first.
    

---

### 7. Buenas prácticas

- Usa `box-sizing: border-box` por defecto.
    
- Mantén una jerarquía clara de estilos.
    
- Usa variables CSS si son muchas propiedades repetidas.
    
- Evita `!important`, clases innecesarias y sobrespecificación.
    

---

## 🎯 Preguntas comunes de entrevista

### 🧠 ¿Cuál es la diferencia entre `relative` y `absolute`?

> "`relative` posiciona un elemento respecto a su posición original, `absolute` lo hace respecto al contenedor con posición relativa más cercano."

### 🧠 ¿Cuándo usar Flexbox y cuándo Grid?

> "Flexbox es ideal para alineaciones lineales (1D), Grid para layouts estructurados (2D)."

### 🧠 ¿Cómo haces que una web sea responsive?

> "Uso un enfoque mobile-first, con `rem`, `vh`, `vw`, media queries y a veces Tailwind si lo permite el stack."

### 🧠 ¿Qué es el modelo de caja?

> "Una representación visual de cómo se calcula el espacio de un elemento: contenido, padding, border y margin."

### 🧠 ¿Qué pasa si pones `overflow: hidden`?

> "El contenido que sobrepase el contenedor será cortado. Se usa para evitar scrolls o limpiar floats."

### 🧠 ¿Qué pasa con `z-index` si no hay posicionamiento?

> "No tiene efecto si el elemento no tiene `position` distinto de `static`."

### 🧠 ¿Cuál es la diferencia entre `em` y `rem`?

> "`em` hereda del padre, `rem` hereda del root (`html`). `rem` da más consistencia al diseño."

### 🧠 ¿Cómo centrarías un elemento?

> Flexbox:

```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

> Margin auto (bloques):

```css
.block {
  margin: 0 auto;
}
```

---

## 🧠 Tips para ti

- Repasa Flexbox y Grid en una web como [flexboxfroggy.com](https://flexboxfroggy.com/) y [cssgridgarden.com](https://cssgridgarden.com/).
    
- Practica maquetando desde cero un layout simple (landing, galería, blog...).
    
- En entrevistas, **habla de decisiones técnicas**: "usé grid por..." o "elegí usar media queries porque...".

# 🧠 JavaScript

## ✅ Fundamentos esenciales explicados

---

### 1. ¿Qué es JavaScript y para qué sirve?

JavaScript (JS) es un lenguaje de programación interpretado que se ejecuta en el navegador (y también en servidores con Node.js). Se usa para crear interactividad en páginas web: formularios dinámicos, sliders, efectos, validaciones, SPA, etc.

---

### 2. Sintaxis básica y tipos de datos

#### Tipos primitivos

```js
string, number, boolean, null, undefined, symbol, bigint
```

#### Variables

```js
let nombre = 'Javi'; // se puede reasignar
const edad = 25; // constante, no se puede reasignar
var obsoleto = true; // evitar su uso
```

#### Operadores comunes

```js
=== // igualdad estricta
!== // desigualdad estricta
&&, || // lógicos
+ - * / % // aritméticos
```

---

### 3. Estructuras de control

```js
if (edad > 18) {
  console.log('Mayor de edad');
} else {
  console.log('Menor de edad');
}

for (let i = 0; i < 3; i++) {
  console.log(i);
}

while (condición) {
  // bucle mientras
}
```

---

### 4. Funciones

```js
function saludar(nombre) {
  return `Hola, ${nombre}`;
}

const despedir = (nombre) => `Adiós, ${nombre}`;
```

Las funciones son ciudadanos de primera clase → se pueden pasar como argumentos y devolver como resultado.

---

### 5. Objetos y Arrays

```js
const persona = {
  nombre: 'Javi',
  edad: 25,
};

const frutas = ['manzana', 'pera', 'plátano'];
```

Destructuring:

```js
const { nombre } = persona;
const [primera] = frutas;
```

---

### 6. DOM y eventos básicos

```js
document.querySelector('button').addEventListener('click', () => {
  alert('¡Click!');
});
```

Manipular el DOM (Document Object Model) permite actualizar el HTML desde JS.

---

### 7. Scope y hoisting

- `let` y `const` tienen _bloque_ scope.
    
- `var` tiene _función_ scope.
    
- Hoisting: las `var` y funciones _declaradas_ se “elevan” al inicio del código (pero no las funciones flecha ni `let/const`).
    

---

### 8. Asincronía básica

```js
fetch('/datos')
  .then(res => res.json())
  .then(data => console.log(data))
  .catch(err => console.error(err));

// async/await
async function cargarDatos() {
  try {
    const res = await fetch('/datos');
    const data = await res.json();
    console.log(data);
  } catch (err) {
    console.error(err);
  }
}
```

---

### 9. JSON

- Formato de texto para intercambiar datos.
    
- Métodos:
    

```js
JSON.stringify(objeto) // objeto a string JSON
JSON.parse(stringJSON) // string a objeto
```

---

### 10. Métodos de Array muy comunes

```js
map, filter, find, some, every, forEach, reduce

const nombres = usuarios.map(u => u.nombre);
const mayores = usuarios.filter(u => u.edad > 18);
```

---

## 💬 Preguntas frecuentes en entrevistas (y qué responder)

### ❓ ¿Qué diferencia hay entre `let`, `const` y `var`?

- `var` tiene ámbito de función y se puede redeclarar. `let` y `const` tienen ámbito de bloque.
    
- `const` no se puede reasignar (aunque sí modificar si es un objeto).
    

### ❓ ¿Qué es hoisting?

Es cuando las declaraciones (no inicializaciones) de `var` y funciones se "mueven" arriba del código al ejecutarse.

### ❓ ¿Qué es el event loop?

El mecanismo que permite a JS ejecutar código de forma no bloqueante (asincronía con callbacks, promises, async/await).

### ❓ ¿Cómo manejas errores en JS?

- Try/catch para errores en ejecución.
    
- `.catch()` para promesas.
    

### ❓ ¿Qué es una función de orden superior?

Función que recibe otra función como argumento o devuelve una función (como `map`, `filter`, `reduce`).

### ❓ ¿Qué es el DOM y cómo se manipula con JS?

El DOM es la representación del HTML como un árbol de nodos. Se puede acceder y modificar con JS usando métodos como:

```js
document.getElementById
querySelector
innerHTML
textContent
classList.add/remove
```

### ❓ ¿Qué diferencias hay entre `==` y `===`?

- `==` compara valores (con conversión implícita).
    
- `===` compara valor y tipo. Siempre usar `===`.
    

### ❓ ¿Qué es una promesa y cómo funciona?

Objeto que representa una operación asincrónica que puede:

- resolverse (resolve)
    
- fallar (reject)
    

```js
new Promise((resolve, reject) => {
  if (todoBien) resolve('OK');
  else reject('Error');
});
```

---

## 🧠 Consejos para la entrevista

- Muestra que sabes cómo leer código JS y explicar qué hace.
    
- Si te preguntan por asincronía, haz énfasis en cómo `fetch`, `.then()` y `async/await` funcionan.
    
- Si no te acuerdas exactamente de algo, explica la idea general y di que sueles consultarlo en MDN (es mejor que inventar).
    

---

## 📌 Prácticas recomendadas

- Usa siempre `const` por defecto, `let` si hay que reasignar.
    
- Comenta el código cuando sea poco intuitivo.
    
- Nombra variables y funciones de forma clara y consistente.
    
- No uses `var`, y evita anidar callbacks (callback hell → usa async/await).
    


# 🧠 TypeScript

## ✅ ¿Qué es TypeScript y por qué importa?

TypeScript es un superset de JavaScript que añade tipado estático y herramientas de desarrollo más robustas. Se compila a JavaScript, y su propósito es ayudar a detectar errores antes de ejecutar el código.

---

## 🔍 Conceptos esenciales explicados

### 1. Tipos básicos

```ts
let nombre: string = "Javi";
let edad: number = 25;
let esActivo: boolean = true;
```

### 2. Tipos compuestos

```ts
let hobbies: string[] = ["leer", "código"];
let datos: (string | number)[] = ["usuario", 42];
```

### 3. Objetos y tipado estructurado

```ts
type Usuario = {
  nombre: string;
  edad: number;
  activo?: boolean; // opcional
};

const user: Usuario = {
  nombre: "Javi",
  edad: 25,
};
```

### 4. Funciones tipadas

```ts
function saludar(nombre: string): string {
  return `Hola, ${nombre}`;
}

const sumar = (a: number, b: number): number => a + b;
```

### 5. Enums y Literales

```ts
enum Rol {
  ADMIN = "admin",
  USER = "user",
}

let rol: Rol = Rol.ADMIN;
```

### 6. Interfaces

```ts
interface Producto {
  id: number;
  nombre: string;
  precio: number;
}

const libro: Producto = {
  id: 1,
  nombre: "Clean Code",
  precio: 29.99,
};
```

### 7. Uniones y type narrowing

```ts
function imprimir(valor: string | number) {
  if (typeof valor === "string") {
    console.log(valor.toUpperCase());
  } else {
    console.log(valor.toFixed(2));
  }
}
```

### 8. Type Assertion

```ts
const input = document.querySelector("#nombre") as HTMLInputElement;
console.log(input.value);
```

---

## 💬 Preguntas frecuentes de entrevista

### ❓ ¿Por qué usar TypeScript?

- Detección de errores en tiempo de compilación.
    
- Mejora la autocompletación y el desarrollo colaborativo.
    
- Más mantenible en proyectos grandes.
    

### ❓ ¿Qué diferencias hay entre type e interface?

**Similitudes**:

- Ambos se usan para describir la forma de un objeto.
    

**Diferencias**:

- `interface` se puede extender (herencia) y combinar con otras interfaces declaradas del mismo nombre. Esto lo hace ideal para librerías y APIs.
    

```
interface A {
  nombre: string;
}

interface A {
  edad: number;
}
// A tiene nombre y edad ahora.
```

- `type` es más versátil: se puede usar para uniones, tipos literales, y composiciones complejas.
    

```
type ID = number | string;
type User = { nombre: string } & { edad: number };
```

**Recomendación**: usa `interface` para estructuras orientadas a objetos y `type` para tipos más funcionales o complejos.

### ❓ ¿Qué es type narrowing?

Es refinar el tipo de una variable usando lógica (como `typeof`, `in`, etc.) para que TypeScript sepa con qué está trabajando.

### ❓ ¿Qué son los enums?

Conjuntos de valores posibles. Se usan para representar opciones finitas.

### ❓ ¿Qué pasa si usas TypeScript sin definir tipos?

TypeScript infiere tipos automáticamente. Es útil, pero se recomienda tipar explícitamente cuando sea importante.

---

## 📌 Buenas prácticas para tu perfil

- Siempre define tipos en funciones públicas.
    
- Prefiere `type` para definir estructuras reutilizables.
    
- Usa enums solo si son realmente necesarios.
    
- Activa `strict` en `tsconfig.json` para máxima seguridad.
    

---

## 🧠 Recomendaciones de repaso

- Practica migrar pequeños archivos JS a TS.
    
- Usa playgrounds como [TypeScript Playground](https://www.typescriptlang.org/play).
    
- Familiarízate con errores típicos de tipado y cómo resolverlos.
    

---

Este nivel de conocimiento es más que suficiente para una entrevista junior, especialmente si puedes explicar cómo TypeScript mejora tu código del día a día. ¡Vamos bien!

# ⚛️ React

## ✅ ¿Qué es React y por qué es tan usado?

React es una biblioteca de JavaScript desarrollada por Meta para construir interfaces de usuario. Su mayor ventaja es el Virtual DOM, que permite una actualización eficiente y selectiva del DOM real cuando cambian los datos, lo que mejora el rendimiento.

---

## 🔍 Conceptos fundamentales

### 1. Componentes

Son las piezas fundamentales de una app en React. Puedes pensarlos como funciones que devuelven HTML (a través de JSX):

```jsx
function Saludo({ nombre }) {
  return <h1>Hola, {nombre}</h1>;
}
```

Cada componente puede tener sus propios datos (props, estado) y lógica.

### 2. JSX (JavaScript XML)

JSX permite escribir HTML-like en JavaScript. Aunque parece HTML, en realidad es sintaxis transformada en llamadas a `React.createElement()`.

```jsx
const elemento = <div className="card">Contenido</div>;
```

JSX no permite `if` directamente, pero sí expresiones condicionales dentro de `{}`.

### 3. Props (propiedades)

Las props son la forma de pasar información de un componente padre a un hijo. Son inmutables:

```jsx
function Bienvenida({ nombre }) {
  return <p>Hola, {nombre}</p>;
}
```

### 4. Estado – `useState`

El estado es lo que hace que tu componente "reaccione" a cambios. Con `useState`, puedes declarar y actualizar variables reactivas:

```jsx
const [contador, setContador] = useState(0);
```

Cambiar el estado vuelve a renderizar el componente con los nuevos valores.

### 5. Efectos – `useEffect`

Sirve para ejecutar efectos secundarios como peticiones a API, suscripciones, o manipulación directa del DOM.

```jsx
useEffect(() => {
  console.log("Se montó el componente o cambió 'contador'");
}, [contador]);
```

- Si el array de dependencias está vacío, se ejecuta solo al montar.
    
- Si contiene variables, se ejecuta cada vez que alguna cambia.
    

### 6. Eventos

Manejo de eventos al estilo JS, pero en camelCase:

```jsx
<button onClick={() => setContador(c => c + 1)}>+</button>
```

### 7. Renderizado condicional

```jsx
{logueado ? <Dashboard /> : <Login />}
```

También puedes usar `&&` o funciones.

### 8. Listas y `key`

```jsx
{usuarios.map(user => <li key={user.id}>{user.nombre}</li>)}
```

React necesita `key` única para cada elemento renderizado dinámicamente para optimizar cambios.

### 9. Formularios controlados

Se vincula el valor del input al estado del componente:

```jsx
<input value={nombre} onChange={e => setNombre(e.target.value)} />
```

Esto te da control completo sobre lo que escribe el usuario.

### 10. Lifting State Up

Cuando dos componentes necesitan compartir datos, se sube el estado al padre común.

---

## ❓ Preguntas comunes de entrevista

### ¿Qué diferencia hay entre `props` y `state`?

- `props`: datos pasados desde el padre, no se pueden modificar.
    
- `state`: datos locales del componente que sí pueden cambiar con `setState` o `useState`.
    

### ¿Qué es `useEffect` y cómo se usa?

Es un hook que ejecuta efectos secundarios. Lo usas para cosas como peticiones a API, temporizadores, etc. Puedes controlar cuándo se ejecuta con el array de dependencias.

### ¿Qué pasa si olvido poner una `key` en una lista?

React no podrá identificar bien qué elementos cambiaron y puede causar renderizados ineficientes o incluso errores visuales.

### ¿Qué es un componente controlado?

Un input cuyo valor se gestiona desde el estado de React. Permite validaciones y lógica personalizada en formularios.

### ¿Qué es el Virtual DOM?

Es una representación en memoria del DOM real. React compara versiones anteriores con nuevas (diffing) y actualiza solo los nodos necesarios.

### ¿Qué es `lifting state up`?

Cuando varios componentes hijos necesitan el mismo estado, se mueve (se "eleva") a su componente padre para que lo compartan.

### ¿Qué es un Hook en React?

Una función especial que te permite usar funcionalidades de React como estado (`useState`), efectos (`useEffect`), contexto (`useContext`), etc. Solo se pueden usar dentro de componentes.

---

## 🧪 Ideas prácticas que te conviene tener frescas

- Contador simple (con botón + y -)
    
- Formulario de login con validación
    
- Lista de tareas (añadir, eliminar, marcar completadas)
    
- App que consuma una API (por ejemplo, Rick & Morty, Pokédex, clima)
    

---

# 🗄️ SQL

## ✅ ¿Qué es SQL y para qué sirve?

SQL (Structured Query Language) es el lenguaje estándar para gestionar bases de datos relacionales. Se usa para crear, consultar, actualizar y eliminar datos.

---

## 📦 Conceptos fundamentales

### 1. Bases de datos y tablas

Una base de datos es una colección organizada de datos. Dentro de ella hay **tablas**, que representan entidades (como usuarios, productos, pedidos).

### 2. Tipos de datos comunes

- `INT`: Números enteros
    
- `VARCHAR(n)`: Texto de longitud variable
    
- `TEXT`: Texto largo
    
- `DATE`, `DATETIME`: Fechas
    
- `BOOLEAN`: Verdadero o falso
    

### 3. CRUD básico (Create, Read, Update, Delete)

#### Crear registros (INSERT)

```sql
INSERT INTO usuarios (nombre, email) VALUES ('Javi', 'javi@mail.com');
```

#### Leer registros (SELECT)

```sql
SELECT * FROM usuarios;
SELECT nombre FROM usuarios WHERE id = 2;
```

#### Actualizar registros (UPDATE)

```sql
UPDATE usuarios SET nombre = 'Javier' WHERE id = 2;
```

#### Eliminar registros (DELETE)

```sql
DELETE FROM usuarios WHERE id = 2;
```

### 4. Cláusulas comunes

- `WHERE`: Filtra registros
    
- `ORDER BY`: Ordena los resultados
    
- `LIMIT`: Limita el número de resultados
    
- `GROUP BY`: Agrupa resultados
    
- `HAVING`: Filtra después de agrupar
    

```sql
SELECT ciudad, COUNT(*) FROM usuarios GROUP BY ciudad HAVING COUNT(*) > 1;
```

### 5. Joins

Permiten combinar datos de varias tablas relacionadas.

```sql
SELECT pedidos.id, usuarios.nombre
FROM pedidos
JOIN usuarios ON pedidos.usuario_id = usuarios.id;
```

Tipos de joins:

- `INNER JOIN`: Solo los que coinciden en ambas tablas
    
- `LEFT JOIN`: Todos los de la izquierda y los coincidentes de la derecha
    
- `RIGHT JOIN`, `FULL OUTER JOIN` (menos comunes)
    

### 6. Índices y claves

- **PRIMARY KEY**: Identificador único por fila
    
- **FOREIGN KEY**: Relación con otra tabla
    
- **INDEX**: Acelera consultas en columnas concretas
    

### 7. Subconsultas y alias

```sql
SELECT nombre FROM (
  SELECT * FROM usuarios WHERE activo = 1
) AS usuarios_activos;
```

Alias:

```sql
SELECT u.nombre FROM usuarios AS u;
```

---

## ❓ Preguntas de entrevista comunes y respuestas

### 🔹 ¿Qué es SQL y para qué se utiliza?

> Es un lenguaje para interactuar con bases de datos relacionales: crear tablas, insertar, leer, actualizar y eliminar datos.

### 🔹 ¿Cuál es la diferencia entre `WHERE` y `HAVING`?

> `WHERE` filtra antes de agrupar, `HAVING` después.

### 🔹 ¿Qué tipos de joins conoces y en qué se diferencian?

> `INNER`, `LEFT`, `RIGHT`, `FULL OUTER`. La diferencia está en qué registros se mantienen según si coinciden entre las tablas.

### 🔹 ¿Qué es una clave primaria?

> Una columna o conjunto de columnas que identifican de forma única cada fila en una tabla.

### 🔹 ¿Qué es una subconsulta?

> Una consulta anidada dentro de otra. Sirve para obtener datos intermedios.

### 🔹 ¿Qué es normalización?

> Proceso de estructurar una base de datos para reducir redundancia y mejorar integridad.

---

## 🧠 Buenas prácticas

- Usa nombres descriptivos para tablas y columnas.
    
- Evita SELECT * en producción.
    
- Indexa columnas usadas en filtros JOIN y WHERE.
    
- Controla el acceso con roles/usuarios.
    
- Evita duplicidad de datos con claves primarias y únicas.
    

---

## 🧪 Ideas para practicar

- Base de datos de usuarios y pedidos.
    
- Sistema de gestión de tareas con estados.
    
- Base de datos de películas, directores y géneros.
    

---

# 🧬 Git

## ✅ Conceptos fundamentales

### 1. ¿Qué es Git?

Git es una herramienta que permite registrar los cambios realizados en el código a lo largo del tiempo. Funciona de forma distribuida, lo que significa que cada desarrollador tiene una copia completa del repositorio.

### 2. Repositorios

- **Repositorio local**: el que tienes en tu máquina.
    
- **Repositorio remoto**: por ejemplo, el de GitHub o GitLab.
    

```bash
# Iniciar un repositorio local
git init
```

### 3. Commits

Un commit es un snapshot del código. Deben ser atómicos (un cambio específico) y tener mensajes descriptivos.

```bash
# Añadir archivos al área de preparación (staging area)
git add archivo.js

# Crear un commit
git commit -m "Añadir función de login"
```

### 4. Ramas (branches)

Permiten trabajar en funcionalidades aisladas sin afectar el código principal.

```bash
# Crear una rama nueva
git branch nueva-funcionalidad

# Cambiar de rama
git checkout nueva-funcionalidad

# Crear y cambiar a la vez
git checkout -b hotfix-bug
```

### 5. Fusionar ramas (merge)

Combina los cambios de una rama con otra. Si hay conflictos, se resuelven manualmente.

```bash
# Desde la rama principal
git merge nueva-funcionalidad
```

### 6. Repositorio remoto

Conectarse a un repositorio remoto como GitHub:

```bash
# Añadir origen
git remote add origin https://github.com/usuario/repositorio.git

# Subir al repositorio remoto
git push origin main
```

### 7. Clonar y actualizar

```bash
# Clonar un repo existente
git clone https://github.com/usuario/repositorio.git

# Traer los cambios del remoto
git pull origin main
```

### 8. Ignorar archivos

Con `.gitignore` puedes evitar que ciertos archivos se suban.

```
node_modules/
.env
```

---

## ❓ Preguntas comunes de entrevista (con respuestas)

### ¿Qué es Git y para qué se utiliza?

Es un sistema de control de versiones que permite guardar el historial de cambios y colaborar con otros desarrolladores.

### ¿Qué diferencia hay entre `git add`, `git commit` y `git push`?

- `git add`: prepara los archivos para el commit.
    
- `git commit`: guarda los cambios en el historial local.
    
- `git push`: sube los commits al repositorio remoto.
    

### ¿Cómo funciona `git merge`? ¿Y qué pasa si hay conflictos?

`git merge` une dos ramas. Si hay cambios incompatibles, Git marca los conflictos y se deben resolver manualmente antes de hacer commit.

### ¿Qué es un conflicto y cómo se resuelve?

Un conflicto ocurre cuando dos ramas han modificado la misma línea de código. Se resuelve editando el archivo manualmente y haciendo un nuevo commit.

### ¿Qué es un `pull request` o `merge request`?

Es una petición para revisar y fusionar cambios desde una rama a otra, muy usado en plataformas como GitHub o GitLab.

### ¿Qué es `git clone` y `git pull`?

- `git clone`: crea una copia completa del repositorio.
    
- `git pull`: sincroniza tu repositorio local con el remoto.
    

---

## 🧠 Buenas prácticas

- Commits pequeños y descriptivos.
    
- Usa ramas para cada funcionalidad.
    
- Siempre haz pull antes de empezar a trabajar.
    
- Revisa conflictos antes de hacer merge.
    
- Usa `.gitignore` correctamente.
    
- Escribe buenos mensajes de commit.
    

---

## 🧪 Prácticas recomendadas

- Crear un repositorio local y subirlo a GitHub.
    
- Clonar un repositorio remoto y trabajar desde ahí.
    
- Hacer ramas para features, bugs y hotfixes.
    
- Simular un conflicto con otro compañero o tú mismo.
    

---

# 🧪 Testing

## ✅ ¿Por qué es importante el testing?

El testing en el desarrollo web permite verificar que las funcionalidades del código funcionan como se espera, previniendo bugs y regresiones en futuras versiones. A nivel profesional, demuestra calidad de código, confianza en los despliegues y facilita el mantenimiento.

---

## 🧰 Herramientas de testing populares

### 🟩 Jest

- Framework de testing mantenido por Meta.
    
- Muy usado con React.
    
- Permite mocks, assertions, testing de async, coverage.
    

### ⚡ Vitest

- Similar a Jest pero más rápido y moderno.
    
- Integración nativa con proyectos Vite.
    
- Sintaxis y API casi idénticas a Jest.
    

---

## 🧪 Tipos de tests

|Tipo|Qué prueba|Nivel|
|---|---|---|
|Unitario|Funciones individuales|Bajo|
|Integración|Varias partes que trabajan juntas|Medio|
|End to End (E2E)|Flujo completo de la app|Alto (usualmente con Cypress o Playwright)|

---

## 🧱 Sintaxis básica con Jest o Vitest

```ts
import { describe, it, expect } from 'vitest';

describe('suma', () => {
  it('debería sumar dos números', () => {
    expect(1 + 2).toBe(3);
  });
});
```

### Mock de funciones

```ts
const mockFn = vi.fn();
mockFn('llamada');
expect(mockFn).toHaveBeenCalled();
```

### Async/Await

```ts
it('espera resultado async', async () => {
  const data = await fetchData();
  expect(data).toEqual({ nombre: 'Javi' });
});
```

---

## 📚 Buenas prácticas

- Testea lo que puede fallar, no lo obvio.
    
- Nombra bien los tests: qué hacen y qué esperan.
    
- Evita dependencias innecesarias (mockea APIs).
    
- No testees implementación, testea comportamiento.
    
- Usa `coverage` para revisar qué partes no están cubiertas.
    

---

## ❓ Preguntas comunes de entrevista (con respuestas)

### 🔸 ¿Qué es un test unitario?

Un test que comprueba una parte aislada del código (como una función). Debe ser rápido y no depender de otras partes del sistema.

### 🔸 ¿Cuál es la diferencia entre test unitario e integración?

El test unitario prueba unidades pequeñas (como una función). El de integración verifica cómo interactúan varias unidades entre sí (por ejemplo, un formulario que actualiza estado y hace una llamada).

### 🔸 ¿Por qué usar mocks?

Para simular dependencias externas (como APIs, bases de datos o funciones costosas). Así mantenemos los tests rápidos y controlados.

### 🔸 ¿Qué cobertura de código se recomienda?

No hay número mágico, pero entre 70-90% suele ser saludable. Lo importante es cubrir casos críticos y evitar zonas sin testeo.

### 🔸 ¿Cómo testearías un formulario en React?

- Simulando cambios de input (`fireEvent` o `userEvent` si usas Testing Library).
    
- Enviando el formulario y comprobando el resultado esperado (p. ej. mensaje de éxito o petición enviada).
    

---

## 🧪 Ejemplo simple (React + Testing Library + Vitest)

```tsx
import { render, screen, fireEvent } from '@testing-library/react';
import MiBoton from './MiBoton';

describe('MiBoton', () => {
  it('cambia texto al hacer clic', () => {
    render(<MiBoton />);
    const boton = screen.getByText('Haz clic');
    fireEvent.click(boton);
    expect(boton.textContent).toBe('¡Gracias!');
  });
});
```

---
# 📝 WordPress
### 🧠 ¿Qué es WordPress?

WordPress es un sistema de gestión de contenidos (CMS) que permite crear y administrar sitios web sin necesidad de escribir mucho código. Es ampliamente utilizado por su flexibilidad, facilidad de uso y gran ecosistema de temas y plugins.

Existen dos versiones:

- **WordPress.com**: alojado y limitado (más enfocado a bloggers).
    
- **WordPress.org**: autoalojado y totalmente personalizable.
    

---

### ⚙️ ¿Para qué se usa?

- Creación y gestión de blogs.
    
- Webs corporativas.
    
- E-commerce (con WooCommerce).
    
- Portfolios, foros, membresías, landing pages, etc.
    

---

### 🔧 Conceptos clave

#### 1. **Panel de Administración (Back Office)**

Desde aquí puedes gestionar el contenido, apariencia, plugins, usuarios y configuraciones generales del sitio.

#### 2. **Temas (Themes)**

Controlan el diseño del sitio. Puedes:

- Instalar temas gratuitos o de pago.
    
- Personalizarlos con el editor visual (personalizador) o con código (`style.css`, `functions.php`, etc.).
    

#### 3. **Plugins**

Extienden la funcionalidad del sitio sin necesidad de programar. Algunos muy conocidos y útiles:

- **Yoast SEO**: para optimización en motores de búsqueda.
    
- **Elementor**: editor visual tipo "drag and drop".
    
- **WooCommerce**: para tiendas online.
    
- **WPForms**: creación sencilla de formularios.
    
- **Contact Form 7**: otra alternativa de formularios.
    
- **UpdraftPlus**: copias de seguridad.
    
- **Wordfence**: seguridad.
    
- **Smush**: optimización de imágenes.
    

Para instalar un plugin:

1. Ir a la sección "Plugins" > "Añadir nuevo".
    
2. Buscarlo por nombre.
    
3. Instalar y activar.
    
4. Configurarlo según sus opciones internas.
    

> ⚠️ Importante: Instalar muchos plugins puede ralentizar el sitio. Se recomienda usar sólo los necesarios y mantenerlos actualizados.

#### 4. **Entradas vs Páginas**

- **Entradas**: contenido cronológico como blogs o noticias. Pueden tener categorías y etiquetas.
    
- **Páginas**: contenido estático como "Inicio", "Contacto", "Servicios", etc.
    

#### 5. **Editor de bloques (Gutenberg)**

Desde WordPress 5.x, se utiliza Gutenberg: un editor basado en "bloques" visuales (párrafos, imágenes, vídeos, botones, etc.) que puedes mover y personalizar fácilmente.

#### 6. **Widgets y Menús**

- **Widgets**: pequeños módulos (como calendarios, formularios, listas de entradas, etc.) colocables en barras laterales, pies de página u otras áreas del tema.
    
- **Menús**: gestionan la navegación del sitio y pueden incluir páginas, enlaces personalizados, categorías, etc.
    

#### 7. **Usuarios y roles**

WordPress gestiona permisos mediante roles:

- **Administrador**: acceso completo.
    
- **Editor**: gestiona todo el contenido.
    
- **Autor**: puede escribir y publicar sus propias entradas.
    
- **Colaborador**: puede escribir pero no publicar.
    
- **Suscriptor**: sólo ve contenido y gestiona su perfil.
    

#### 8. **SEO básico**

- Instalar plugins como **Yoast SEO**.
    
- Usar títulos jerárquicos (`<h1>`, `<h2>`, ...).
    
- Estructura clara y amigable de URLs.
    
- Metadescripciones adecuadas.
    
- Uso de imágenes optimizadas con textos alternativos.
    

#### 9. **Personalización avanzada: Tema hijo (Child Theme)**

Cuando necesitas editar un tema sin perder cambios al actualizarlo, se crea un **tema hijo** que hereda del tema padre.

Pasos básicos:

1. Crear una carpeta nueva en `/wp-content/themes`.
    
2. Añadir un archivo `style.css` con cabecera especial.
    
3. Importar estilos del tema padre.
    
4. Modificar archivos (plantillas, funciones, estilos).
    

---

### 📦 Experiencia típica para poner en tu CV

> "Creación, gestión y personalización de sitios en WordPress. Gestión de contenido, maquetación con Gutenberg y Elementor, optimización SEO básica, instalación y configuración de plugins como Yoast SEO y WPForms."

---

### ❓ Preguntas comunes de entrevista (con respuestas)

#### 1. ¿Qué es WordPress y para qué lo has usado?

> WordPress es un CMS que permite crear sitios web de forma visual y rápida. Lo he usado para gestionar contenido, crear páginas y entradas, instalar plugins y modificar la apariencia mediante temas.

#### 2. ¿Qué diferencias hay entre una entrada y una página?

> Las entradas son artículos cronológicos, ideales para blogs. Las páginas son contenido estático, como "Quiénes somos" o "Contacto".

#### 3. ¿Has trabajado con plugins? ¿Cuáles?

> Sí, he usado plugins como Yoast SEO para optimización, Elementor para construir páginas, WPForms para formularios y Smush para optimizar imágenes.

#### 4. ¿Qué es un tema hijo y por qué se usa?

> Es un tema que hereda de otro y permite hacer modificaciones sin perderlas al actualizar el tema original.

#### 5. ¿Sabes cómo optimizar WordPress para SEO?

> Sí, aplico títulos jerarquizados, metadescripciones, URLs amigables, textos alternativos para imágenes y uso de plugins como Yoast SEO.

#### 6. ¿Has tocado código en WordPress?

> He editado `style.css` para ajustar estilos y añadido funciones simples en `functions.php`, como registrar menús personalizados o modificar el comportamiento del tema.

#### 7. ¿Cómo se estructura un sitio en WordPress?

> Mediante entradas y páginas organizadas por menús, con diseño controlado por temas, funcionalidades añadidas con plugins y módulos visuales como bloques y widgets.

---

### 🧪 Ideas para practicar

- Crea un blog personal.
    
- Haz una web para un restaurante ficticio.
    
- Instala y personaliza Elementor.
    
- Instala WooCommerce y configura una tienda.
    
- Crea un formulario de contacto con WPForms o Contact Form 7.
    
- Crea un tema hijo y haz cambios sencillos en el CSS.
    

---

### 📌 Recomendaciones finales

- Familiarízate con el panel de administración.
    
- Aprende lo básico del editor Gutenberg.
    
- Practica la instalación/configuración de plugins.
    
- Toca el código con cuidado y usa tema hijo para aprender.
    
- Optimiza cada sitio en rendimiento y SEO con herramientas básicas.
    

---


# 🧼 Clean Code

✅ **Fundamentos Técnicos Explicados para Entrevistas**

## 1. ¿Qué es Clean Code?

**Clean Code** se refiere a un conjunto de principios y prácticas que hacen que el código sea:

- **Legible**: fácil de leer y comprender.
    
- **Mantenible**: fácil de modificar, extender y depurar.
    
- **Escalable**: puede crecer sin volverse incontrolable.
    
- **Expresivo**: refleja claramente su intención.
    

Es un concepto promovido por Robert C. Martin ("Uncle Bob") en su libro _Clean Code: A Handbook of Agile Software Craftsmanship_.

---

## 2. Nombrado Significativo (Meaningful Names)

### Principios:

- Nombres que indiquen el **propósito** de la variable, función o clase.
    
- Evitar abreviaciones crípticas.
    
- Las funciones booleanas deben sonar como **preguntas**: `isVisible`, `hasAccess`.
    

```js
// ❌ Malo
let x = true;

// ✅ Bueno
let isAuthenticated = true;
```

---

## 3. Funciones con Un Solo Propósito (Single Responsibility Principle)

Este es el primer principio de **SOLID**:

- Una función debe tener una sola responsabilidad.
    
- Facilita las pruebas, mantenimiento y reutilización.
    

```js
// ❌ Hace demasiado
function handleUser() {
  getUser();
  validateUser();
  renderUser();
}

// ✅ Separa responsabilidades
function getUser() {}
function validateUser(user) {}
function renderUser(user) {}
```

---

## 4. Comentarios Útiles

- El mejor código **se explica solo**.
    
- Usa comentarios sólo para aclarar lógica compleja o justificar decisiones técnicas.
    
- No comentes lo obvio o redundante.
    

```js
// ❌ Comentario innecesario
let age = 30; // guarda la edad

// ✅ Comentario últil
// Consideramos mayor a los usuarios mayores de 18
if (age >= 18) {}
```

---

## 5. Manejo de Errores

- Anticipa y maneja errores de forma clara y segura.
    
- Usa `try...catch` o `Promise.catch()` para errores asíncronos.
    

```js
try {
  await fetchData();
} catch (error) {
  console.error('Error al obtener datos', error);
}
```

---

## 6. Evita la duplicación (DRY: Don't Repeat Yourself)

- Si repites código, considera extraer una función reutilizable.
    
- Fomenta la reutilización modular.
    

```js
// ❌ Repetido
createUser(user);
createUser(admin);

// ✅ Reutilizado
function createUserProfile(type) {
  // lógica genérica
}
```

---

## 7. Principios SOLID (muy comunes en entrevistas)

### S - Single Responsibility

Una clase/función debe tener una única razón para cambiar.

### O - Open/Closed

Debe estar **abierta a extensión** pero **cerrada a modificación**.

### L - Liskov Substitution

Una subclase debe poder sustituir a su clase base sin errores.

### I - Interface Segregation

No forzar a implementar métodos que no necesita.

### D - Dependency Inversion

Depender de **abstracciones**, no de implementaciones concretas.

---

## 🎯 Preguntas comunes de entrevista

### 🧠 ¿Qué es clean code?

"Código que es fácil de leer, entender, mantener y escalar. Usa buenas prácticas como funciones pequeñas, nombres claros y evita duplicaciones."

### 🧠 ¿Puedes explicar el principio de responsabilidad única?

"Una función o clase debe hacer una sola cosa. Si cambia por más de una razón, está violando el principio."

### 🧠 ¿Por qué es malo usar nombres genéricos como `data` o `info`?

"Porque no transmiten intención. `userData` o `productInfo` son más descriptivos y claros."

### 🧠 ¿Cuál es la diferencia entre errores sincrónicos y asincrónicos?

"Sincrónicos se manejan con try/catch; asincrónicos requieren await/async y .catch()."

### 🧠 ¿Qué es DRY y por qué es importante?

"Don't Repeat Yourself. Evitar duplicar lógica reduce errores y mejora el mantenimiento."

### 🧠 ¿Cuándo usarías un comentario en el código?

"Cuando el código es complejamente necesario o contraintuitivo, nunca para repetir lo que ya es evidente."

### 🧠 ¿Qué significa que una función sea pura?

"Que no tiene efectos secundarios y devuelve el mismo resultado para los mismos inputs."

### 🧠 ¿Por qué evitar funciones muy largas?

"Son más difíciles de entender, probar y mantener."

### 🧠 ¿Qué es la inversión de dependencias?

"Depender de interfaces o abstracciones, no de clases concretas. Permite flexibilidad y pruebas."

### 🧠 ¿Cuál es la diferencia entre cohesion y acoplamiento?

"Cohesión es qué tan relacionadas están las partes de un módulo. Acoplamiento es qué tanto dependen unos módulos de otros. Queremos alta cohesión y bajo acoplamiento."

---

# 🔍 SEO / SEM

✅ **Fundamentos Técnicos Explicados para Entrevistas**

## 1. ¿Qué es SEO (Search Engine Optimization)?

SEO es el proceso de optimizar una web para mejorar su **visibilidad orgánica** en los motores de búsqueda como Google.

**Objetivo:** aumentar el tráfico sin pagar anuncios, posicionando mejor en los resultados de búsqueda (SERPs).

### Tipos de SEO:

- **SEO On-Page**: contenido, estructura HTML, keywords, performance.
    
- **SEO Off-Page**: backlinks, autoridad del dominio, menciones externas.
    
- **SEO Técnico**: estructura del sitio, sitemap, robots.txt, rendimiento, indexabilidad.
    

---

## 2. ¿Qué es SEM (Search Engine Marketing)?

SEM incluye el SEO, pero también **publicidad de pago** como:

- Google Ads
    
- Campañas PPC (Pay-Per-Click)
    
- Publicidad display y remarketing
    

**Diferencia clave:** SEO es orgánico; SEM implica inversión económica para posicionarse.

---

## 3. Fundamentos de SEO On-Page

### 📌 HTML Semántico

- Usa etiquetas como `<header>`, `<main>`, `<article>`, `<footer>` para estructurar contenido.
    
- `<h1>` debe ser único por página y describir claramente el contenido principal.
    

### 📌 Meta Tags

```html
<title>Mejor Título para tu Página</title>
<meta name="description" content="Breve descripción que aparece en Google">
```

### 📌 Uso de Keywords

- Investigación previa con herramientas como Google Keyword Planner o Ahrefs.
    
- Inserción natural en:
    
    - títulos (`<title>`, `<h1>`)
        
    - URL (`/mejor-producto`)
        
    - contenido visible
        
    - atributos `alt` de imágenes
        

### 📌 Optimización de Imágenes

```html
<img src="producto.jpg" alt="Zapatillas deportivas negras" loading="lazy" />
```

### 📌 URL Amigables

```
❌ /producto?id=123
✅ /zapatillas-deportivas-negras
```

### 📌 Responsive Design

- Google prioriza el **mobile-first indexing**.
    
- Sitio debe funcionar bien en dispositivos móviles.
    

---

## 4. Fundamentos de SEO Técnico

### 📌 Sitemap y robots.txt

```txt
User-agent: *
Disallow:

Sitemap: https://tusitio.com/sitemap.xml
```

### 📌 Core Web Vitals

- **LCP** (Largest Contentful Paint)
    
- **FID** (First Input Delay)
    
- **CLS** (Cumulative Layout Shift)
    

### 📌 Velocidad de carga

- Usa herramientas como Google PageSpeed Insights o Lighthouse.
    
- Minimiza CSS/JS, activa compresión gzip, usa lazy loading.
    

### 📌 Canonical Tags

Evita contenido duplicado:

```html
<link rel="canonical" href="https://tusitio.com/producto" />
```

---

## 5. Fundamentos de SEM

### 📌 Google Ads

- Campañas de **búsqueda**: aparecen arriba de resultados orgánicos.
    
- Campañas **display**: banners en sitios afiliados.
    
- **Anuncios de shopping**: productos con foto y precio.
    

### 📌 Métricas clave

- CTR (Click Through Rate)
    
- CPC (Costo por Clic)
    
- CPA (Costo por Adquisición)
    
- ROI (Retorno de inversión)
    

### 📌 Estructura de campaña

- Campañas → Grupos de anuncios → Anuncios → Keywords
    

### 📌 Tipos de concordancia de keywords

- Concordancia amplia: zapatillas deportivas
    
- Concordancia de frase: "zapatillas deportivas"
    
- Concordancia exacta: [zapatillas deportivas]
    

---

## 🎯 Preguntas comunes de entrevista

### 🧠 ¿Cuál es la diferencia entre SEO y SEM?

"SEO es posicionamiento orgánico, mientras que SEM incluye publicidad pagada como Google Ads. SEO es gratis pero más lento; SEM es rápido pero cuesta."

### 🧠 ¿Qué factores afectan el posicionamiento SEO?

"Contenido relevante, estructura del sitio, velocidad de carga, mobile-first, backlinks y uso correcto de etiquetas HTML."

### 🧠 ¿Qué es una meta description?

"Una etiqueta que resume el contenido de la página. Aparece en los resultados de búsqueda y puede mejorar el CTR."

### 🧠 ¿Qué son los Core Web Vitals?

"Son métricas de rendimiento que Google usa para evaluar la experiencia de usuario: velocidad de carga, interactividad y estabilidad visual."

### 🧠 ¿Qué hace el archivo robots.txt?

"Indica a los motores de búsqueda qué partes del sitio pueden o no pueden indexar."

### 🧠 ¿Qué es un sitemap y para qué sirve?

"Es un archivo XML que lista las URLs importantes de un sitio. Ayuda a los buscadores a rastrear e indexar mejor el contenido."

### 🧠 ¿Qué herramientas usarías para analizar SEO?

"Google Search Console, Lighthouse, PageSpeed Insights, Ahrefs, Screaming Frog."

### 🧠 ¿Qué significa CTR y cómo mejorarlo?

"Click Through Rate: proporción de clics sobre impresiones. Mejora con títulos atractivos, buenas meta descriptions y rich snippets."

### 🧠 ¿Cómo elegir keywords para SEO?

"Analizando volumen de búsqueda, competencia y relevancia. Se usan herramientas como Keyword Planner o Ubersuggest."

### 🧠 ¿Cómo optimizas una imagen para SEO?

"Nombre de archivo descriptivo, atributo alt, formato webp si es posible, peso reducido y lazy loading."

---

## ✅ Conclusión

Conocer SEO y SEM es clave para cualquier desarrollador web. Aunque no seas especialista en marketing, aplicar buenas prácticas técnicas mejora el posicionamiento y experiencia del usuario, y es muy valorado en entrevistas.

Prepárate para hablar de etiquetas HTML, rendimiento web, y cómo tu trabajo de frontend impacta el tráfico y conversión del sitio.