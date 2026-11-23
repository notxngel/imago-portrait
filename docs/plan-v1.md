# Plan v1 — Imago Portraits (Consolidación Codecademy U1–19 → React I)

Acordado el 2026-11-22.
**Objetivo de la v1:** construir a mano el sitio editorial de **Imago Portraits** (retratos, parejas y familia; sin eventos), demostrando dominio práctico de las **18 unidades ya completadas en Codecademy** y dejando el terreno listo para migrar a **React** (donde estás en `React, Part I` al 62 %).

## Estructura prevista (código escrito por ti)
```text
index.html              # Portada + galería + paquetes + reserva (o multipágina si lo decides en Sesión 1)
src/
  styles/               # CSS modular (tokens, base, layout, componentes)
  domain/               # Lógica pura sin DOM (clases, precios, filtros, validaciones) -> testeada con Mocha/Chai
  data/                 # Datos JSON (sesiones, paquetes, fechas ocupadas) para consumir con fetch
  ui/                   # Renderizado, eventos del DOM y lightbox accesible
tests/                  # Pruebas unitarias Mocha + Chai de src/domain/
```

## Sesiones de la v1

| # | Misión | Unidades Codecademy | Entregable comprobable | Hecha |
|---|---|---|---|---|
| 1 | **Base editorial HTML/CSS + Accesibilidad:** cabecera, hero minimalista, rejilla de galería (retratos/parejas/familia), tarjetas de paquetes y formulario de solicitud de reserva | U1–8, U14 | Página semántica, responsive (móvil y escritorio), `label` en cada campo, contraste y navegación por teclado | ☐ |
| 2 | **Dominio en JS puro (Clases, Módulos, Errores):** modelar paquetes, extras, filtro por categoría y validación de solicitud de reserva sin tocar el DOM | U9–10, U16 | Módulos ES en `src/domain/` con clases/funciones puras y errores descriptivos | ☐ |
| 3 | **Tests automáticos (Mocha + Chai):** probar cálculo de precios, filtros, fechas pasadas/ocupadas y validaciones | U17 | `npm test` en verde cubriendo casos normales, bordes y errores | ☐ |
| 4 | **Interactividad DOM accesible:** filtros de galería en vivo (`aria-pressed`), visor **lightbox** con teclado (`Escape`, `←`/`→`, restauración de foco) y resumen dinámico del presupuesto | U13–14 | Toda la interacción funciona con ratón y solo con teclado | ☐ |
| 5 | **Asincronía, `fetch` y estados de Web App:** mover catálogo/paquetes/disponibilidad a `src/data/*.json`, cargarlos con `fetch` + `async/await`, manejar `loading / error / empty` y simular envío de reserva | U18–19 | La app carga datos de forma asíncrona y responde bien si falla la red o no hay resultados | ☐ |
| 6 | **Cierre v1 + salto a React:** revisión final (Lighthouse/a11y/código) y primer componente en React retomando `React, Part I` (lección *Components and Advanced JSX*) | U20 (62 % → 100 %) | v1 cerrada en Git, explicada sin mirar, y `plan-v2-react.md` abierto | ☐ |

## Reglas de calidad desde la Sesión 1
- **Estética Pixieset más limpia:** fondo neutro claro (papel/marfil), mucho espacio en blanco, tipografía serif editorial para títulos + sans limpia para interfaz, sin sombras pesadas ni efectos recargados.
- **Imágenes:** usa placeholders propios o fotos ligeras en `public/images/` con `alt` descriptivos, `width`/`height` (evitar layout shift) y `loading="lazy"` fuera del hero.
- **Un commit por avance lógico** (Conventional Commits: `feat:`, `fix:`, `style:`, `test:`, `docs:`).
