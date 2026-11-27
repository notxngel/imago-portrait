# Plan v1 — Imago Portraits (Consolidación Codecademy U1–19 → React I)

Acordado el 2026-11-22. Actualizado el 2026-11-27 (meta, páginas y categorías).
Este archivo es la **única fuente** de todo lo de la v1: páginas, sesiones y estado del código.
La meta general y los hitos por fase están en `~/mentoria/RUTA.md`.

**Meta del proyecto:** aprender el path de Codecademy construyendo desde cero el sitio real de Clara. Con el tiempo
sustituye a Pixieset (de pago); la v1 sustituye solo la parte del **sitio web**.

**Objetivo de la v1:** réplica casi idéntica del sitio actual de Clara en Pixieset, con el diseño mejorado de Stitch,
escrita a mano, demostrando dominio práctico de las **18 unidades ya completadas en Codecademy** y dejando el terreno
listo para migrar a **React** (donde estás en `React, Part I` al 62 %).

## Decisiones (2026-11-27)
- **Varias páginas**, no una sola con anclas.
- **Páginas de la v1:** Home, Services, Contact y About (About hoy existe en Pixieset fuera del menú).
- **Book Here** enlaza al Booking Site de Pixieset (`https://imagostudio9.pixieset.com/booking/`).
  **Library** enlaza a las galerías de Pixieset. Las páginas propias llegan con el backend (v3).
- **Categorías:** las que Clara vende en Services: **Couple, Maternity, Portraits**.
- **Contenido:** textos, paquetes y precios reales de su sitio actual (Services: 3 paquetes, cada uno con una opción
  más corta o más larga, 50 % de depósito).
- **Formulario de Contact (opción A):** nombre, email, mensaje + paquete de interés (Couple, Maternity, Portraits) y
  fecha aproximada. Validación en JS (email válido, campos obligatorios, fecha no pasada) con tests en Mocha/Chai.
  El envío es simulado hasta la v3; mientras tanto Clara sigue recibiendo mensajes por Pixieset.

## Estructura prevista (código escrito por ti)
```text
index.html              # Home
services.html           # Paquetes y precios
contact.html            # Formulario de contacto
about.html              # Sobre Clara
src/
  styles/               # CSS modular (tokens, base, layout, componentes)
  domain/               # Lógica pura sin DOM (clases, precios, filtros, validaciones) -> testeada con Mocha/Chai
  data/                 # Datos JSON (galería, paquetes) para consumir con fetch
  ui/                   # Renderizado, eventos del DOM y lightbox accesible
tests/                  # Pruebas unitarias Mocha + Chai de src/domain/
```

## Sesiones de la v1

| # | Misión | Unidades Codecademy | Entregable comprobable | Hecha |
|---|---|---|---|---|
| 1 | **Base editorial HTML/CSS + Accesibilidad:** las 4 páginas, cabecera y footer comunes, hero, galería por categoría (Couple/Maternity/Portraits), tarjetas de paquetes y formulario de contacto | U1–8, U14 | Páginas semánticas, responsive (móvil y escritorio), `label` en cada campo, contraste y navegación por teclado | ☐ |
| 2 | **Dominio en JS puro (Clases, Módulos, Errores):** modelar paquetes y sus opciones, filtro por categoría y validación del formulario de contacto sin tocar el DOM | U9–10, U16 | Módulos ES en `src/domain/` con clases/funciones puras y errores descriptivos | ☐ |
| 3 | **Tests automáticos (Mocha + Chai):** probar precios y depósito, filtros y validaciones del formulario (incluida la fecha pasada) | U17 | `npm test` en verde cubriendo casos normales, bordes y errores | ☐ |
| 4 | **Interactividad DOM accesible:** filtros de galería en vivo (`aria-pressed`), visor **lightbox** con teclado (`Escape`, `←`/`→`, restauración de foco) y resumen dinámico del paquete elegido | U13–14 | Toda la interacción funciona con ratón y solo con teclado | ☐ |
| 5 | **Asincronía, `fetch` y estados de Web App:** mover galería/paquetes a `src/data/*.json`, cargarlos con `fetch` + `async/await`, manejar `loading / error / empty` y simular el envío del formulario | U18–19 | El sitio carga datos de forma asíncrona y responde bien si falla la red o no hay resultados | ☐ |
| 6 | **Cierre v1 + salto a React:** revisión final (Lighthouse/a11y/código) y primer componente en React retomando `React, Part I` (lección *Components and Advanced JSX*) | U20 (62 % → 100 %) | v1 cerrada en Git, explicada sin mirar, y `plan-v2-react.md` abierto | ☐ |

## Reglas de calidad desde la Sesión 1
- **Estética:** el diseño de Stitch. Fondo neutro claro (papel/marfil), mucho espacio en blanco, tipografía serif editorial para títulos + sans limpia para interfaz, sin sombras pesadas ni efectos recargados.
- **Imágenes:** fotos ligeras en `public/images/` con `alt` descriptivos, `width`/`height` (evitar layout shift) y `loading="lazy"` fuera del hero. Solo fotos que Clara (y sus clientas) permitan publicar.
- **`public/` es público:** ahí solo van archivos del sitio, nunca notas ni datos personales.
- **Un commit por avance lógico** (Conventional Commits: `feat:`, `fix:`, `style:`, `test:`, `docs:`).

## Estado de la sesión 1 (revisado el 2026-11-27)
Todo en `~/dev/proyectos/imago-portrait`, **sin commit todavía** (`index.html`, `src/`, `public/` sin seguir en git;
último commit `d89c31a`). `npm run lint` pasaba el 26. Última edición de `index.html`: 26 nov, 7:00.

**Hecho (`index.html`):**
- [x] Cabecera: logo, menú de 4 enlaces, enlaces Library/Contact y botón de perfil con `aria-label`.
- [x] Hero: foto, título «Every Form Of Beauty», texto y dos botones (Book a Session / View Portfolio).
- [x] Bloque de valores + cita («Photographs you'll love for decades»).
- [x] Sección About (`#about-me`) con foto y bio de Clara Lus.
- [x] Sección de contacto (`#contact-me`): solo texto.
- [x] Pie de página con logo, enlaces y copyright.
- [x] `index.html` enlaza bien `src/styles/styles.css`.
- [x] Fotos con `alt` descriptivos y `width`/`height`.
- [x] Decidido: varias páginas (ver «Decisiones»).

**Falta:**
- [x] Sacar `public/images/contexto-unificado.md` del repo (datos personales; se publicaría con la web). → movido a `~/contexto-unificado.md` el 27.
- [x] Decidido el alcance del formulario de Contact: opción A (ver «Decisiones»).
- [ ] Crear `services.html`, `contact.html` y `about.html`; «Book a Session» / Book Here → Booking Site de Pixieset.
- [ ] Galería por categorías (Couple, Maternity, Portraits): `#gallery` sigue teniendo el formulario de código de galería (es de la v3) y 3 fotos sin categoría.
- [ ] Paquetes en `services.html` con los datos reales.
- [ ] CSS vacío: `src/styles/styles.css` tiene 0 bytes.
- [ ] Peso de las fotos: `mujer-embarazada-sonriendo.jpg` (hero) 26 MB y `esposa-y-esposa-celebrando-su-embarazo.jpg` 27 MB (6000×4000 px). El resto, 160–310 KB.
- [ ] Foto del hero con `loading="lazy"` (debe cargarse sin `lazy`).
- [ ] Proporción de `width`/`height`: `personas-caminando…` es 1000×1500 (2:3) pero declara 250×300.
- [ ] Detalles: nombre de marca desigual («Imago Portrait» / «Imago Portraits»), errata en la clase `aditional-info`, espacios al final de los `href` del footer.
- [ ] `docs/diario-tecnico.md` sin ninguna línea desde el 22 nov.

**Reparto de la sesión 1:**

| Día | Qué |
|---|---|
| Mié 25 nov | Terminar el HTML → no terminado; avanzaron About, contacto, footer y fotos |
| Jue 26 nov | Decidir páginas, galería, paquetes, formulario y primer commit → solo la decisión de páginas (hecha el 27) |
| Vie 27 nov | Optimizar las fotos y CSS base |
| Sáb 28 nov | Responsive, revisión con teclado, línea en `docs/diario-tecnico.md` y commit |
| Dom 29 nov · 4 PM | Revisión semanal |
