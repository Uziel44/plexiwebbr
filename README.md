# Plexiweb

Landing page de Plexiweb. Sitio estático (HTML/CSS/JS), sin build ni dependencias — no hay `package.json`.

## Estructura

```
index.html        único punto de entrada
css/style.css      todos los estilos
js/script.js       toda la lógica (carrusel, menú, cookie banner)
assets/            imágenes (logo, portfolio, fondos)
```

## Previsualizar en local

No requiere instalación. Cualquier servidor estático sirve:

```bash
# con VS Code: extensión Live Server, o
npx serve .
# o
python -m http.server 8000
```

Abrir `index.html` con doble clic también funciona, salvo que se necesite `fetch`/rutas relativas estrictas.

## Deploy

Se sube la raíz del repo tal cual (no hay carpeta `dist/`). Publicado en Cloudflare Pages: `https://plexiweb.pages.dev/`.

## Agregar un proyecto al portfolio

En `index.html`, dentro de `.portfolio-columns`, agregar otra tarjeta `<a class="portfolio-card">` en cualquiera de las 4 `.portfolio-col`. Para que la imagen recorra la captura de arriba hacia abajo al pasar el mouse o tocar, usar una captura full-page y sumar la clase `portfolio-card--scroll`. El `<img>` no lleva atributos `width`/`height`: la caja la dimensiona el `aspect-ratio` del CSS. El reparto en 2 columnas en tablet/mobile (≤900px) lo hace `initPortfolioColumns` en `js/script.js`, así que no hace falta tocar CSS ni JS.

## Notas

- Ver [ARQUITECTURA.md](./ARQUITECTURA.md) para el checklist de arquitectura del proyecto.
