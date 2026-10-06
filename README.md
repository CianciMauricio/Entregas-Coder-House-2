# El mundo del ilusionismo

Sitio web de portafolio sobre el arte de la magia y el ilusionismo. Desarrollado a lo largo de varios checkpoints de un curso: HTML semántico, integración de Bootstrap (navbar responsive y carousel), migración completa de los estilos a una arquitectura Sass con partials, y una capa final de animaciones y responsive.

## Páginas

- `index.html` — Inicio
- `pages/beneficios.html` — Beneficios del arte de la magia
- `pages/tipos-de-magia.html` — Tipos de magia
- `pages/grandes-magos.html` — Grandes magos de la historia
- `pages/aprender-magia.html` — Escuelas y academias de magia

## Tecnologías

- HTML5
- Sass (SCSS) — compilado a CSS, arquitectura de partials (patrón 7-1)
- [Bootstrap 5](https://getbootstrap.com/) (vía CDN) — navbar responsive y carousel de imágenes
- [AOS](https://michalsnik.github.io/aos/) (vía CDN) — animaciones al hacer scroll
- Google Fonts (Playfair Display)

## Estructura del proyecto

```
├── index.html
├── pages/
│   ├── beneficios.html
│   ├── tipos-de-magia.html
│   ├── grandes-magos.html
│   └── aprender-magia.html
├── imagenes/
├── css/
│   ├── style.css          ← archivo generado, no editar a mano
│   └── style.css.map
└── scss/
    ├── main.scss           ← único punto de entrada (@use de todo lo demás)
    ├── utilities/
    │   ├── _variables.scss
    │   ├── _mixins.scss
    │   └── _extend.scss
    ├── base/
    │   ├── _base.scss
    │   └── _tipografia.scss
    ├── layout/
    │   ├── _header.scss
    │   ├── _nav.scss
    │   ├── _footer.scss
    │   ├── _main.scss
    │   └── _grid.scss
    └── components/
        ├── _buttons.scss
        └── _cards.scss
```

> El carousel y los ajustes puntuales sobre clases de Bootstrap no viven en los partials de Sass — quedan en reglas CSS manuales, ya que no forman parte de la arquitectura SCSS del proyecto.

## Cómo compilar el SCSS

Este proyecto no escribe CSS a mano: todo el diseño nace en `scss/` y se compila a `css/style.css`.

**1. Instalar las dependencias** (una sola vez, o cada vez que clones el repo):

```bash
npm install
```

**2. Compilar una vez:**

```bash
npx sass scss/main.scss css/style.css
```

**3. Compilar en modo "watch"** (recompila solo cada vez que guardás un cambio — recomendado mientras trabajás):

```bash
npx sass --watch scss/main.scss css/style.css
```

> Si tu `package.json` ya tiene un script definido (por ejemplo `"sass": "sass scss/main.scss css/style.css --watch"`), podés simplemente correr `npm run sass` en vez del comando largo de arriba.

## Cómo visualizar el sitio

Es un sitio estático: no necesita un servidor backend.

- **Opción simple:** abrí `index.html` directamente en el navegador (doble click, o "Abrir con" → tu navegador).
- **Opción recomendada:** si usás VS Code, instalá la extensión **Live Server** y hacé click derecho sobre `index.html` → "Open with Live Server". Esto evita algunos problemas de rutas relativas y recarga la página sola cada vez que guardás un cambio.

Para que los estilos se vean actualizados, recordá tener corriendo el compilador de Sass (paso anterior) en paralelo mientras edités cualquier archivo `.scss`.
