# Imago Portraits

Web y plataforma propia de fotografía editorial para **Imago Portraits** (retratos, parejas y familia), construida **100 % a mano** siguiendo la ruta **Codecademy Full-Stack Engineer** con foco en servidores y ciberseguridad.

## Alcance por versiones
- **v1 (U1–19):** Portfolio editorial limpio (inspirado en Pixieset), galería filtrable con lightbox accesible, paquetes/precios y solicitud de reserva con lógica modular, tests automáticos (**Mocha + Chai**) y carga vía `fetch`.
- **v2 (U20–24):** Migración a **React** (componentes, estado, rutas y pruebas).
- **v3 (U25–35):** Backend en **Node + Express + PostgreSQL** con reservas reales, panel privado y galerías privadas por cliente.
- **v4–v5 (U36–43):** Seguridad aplicada (OWASP Top 10: prevención de IDOR en galerías privadas, subida segura de imágenes, XSS/CSRF/rate limiting) y despliegue reproducible con **Docker** en el Mac mini.

## Scripts
```bash
npm run lint     # Comprueba reglas de ESLint
npm run format   # Formatea con Prettier
npm test         # Ejecuta la suite de pruebas (Mocha + Chai)
```

Ver el plan activo en [`docs/plan-v1.md`](docs/plan-v1.md) y el diario en [`docs/diario-tecnico.md`](docs/diario-tecnico.md).
