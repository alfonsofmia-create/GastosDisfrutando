# GastosDisfrutando

App para llevar la contabilidad de gastos compartidos entre 2 personas (estilo Splitwise), pensada para usarse sobre todo desde el móvil en vertical.

## Estado

Fase de diseño. Estilo elegido: **ticket de caja** (amarillo, monoespaciada, bordes negros gruesos).

- Lienzo con los bocetos: https://claude.ai/artifact/PePYNCrFDjppLXP556QkFy (privado)
- Fuentes en [`bocetos/`](bocetos/):
  - `Inicio.dc.html` — inicio: deuda total, grupos (con foto configurable), crear grupo, «Añadir gasto» y barra inferior (Inicio · Grupos · Actividad · Cuenta). Enlaces navegables.
  - `NuevoGrupo.dc.html` — crear grupo: foto, nombre (obligatorio, sin duplicados) y subgrupos opcionales. El grupo aparece en Inicio y en Grupos.
  - `AnadirGasto.dc.html` — añadir gasto (pendiente de definir).
  - `Grupos.dc.html` — lista de grupos (editar nombre y subgrupos, borrar con confirmación, añadir); al abrir un grupo, sus subgrupos (1 nivel: crear, editar, borrar); en cada subgrupo, «Tipos de cambio» (solo dibujado, pendiente de definir).
  - `Actividad.dc.html` — últimos movimientos agrupados por día.
  - `Cuenta.dc.html` — datos básicos del usuario: editar nombre y email (con validación) y foto de perfil. De momento se guarda solo en el navegador.
  - `canvas.json` — disposición de los bocetos en el lienzo.

## Decisiones tomadas

- **Diseño**: opción D, «ticket de caja». Fondo `#FFD43B`, texto `#111111`, fuente IBM Plex Mono, bordes negros de 3px, sombras planas. Verde `#1C6B3A` con «+» = te deben; rojo `#B3261E` con «−» = debes.
- **Uso**: 90 % desde móvil en vertical (pantallas de 390×844).
- **Personas**: siempre las mismas 2 personas en todos los grupos (no se piden miembros).
- **Moneda**: solo euros en toda la aplicación.
- **Grupos**: con foto opcional y un solo nivel de subgrupos.
- **Menú inferior**: Inicio · Grupos · Actividad · Cuenta (se quitó «Amigos»).
- **Inicio**: sin lupa, sin filtro y sin textos de grupos saldados; se quitó «Gastos sin grupo».
- **Forma de trabajar**: el usuario define cada pantalla paso a paso; no se construye nada sin su indicación. Cada cambio se prueba en el lienzo y se sube a GitHub solo cuando el usuario lo pide.

## Pendiente

- **Añadir gasto**: por definir (siguiente paso propuesto).
- **Tipos de cambio** en subgrupos: solo dibujado. Con la decisión de «solo euros», confirmar si se elimina.
- **Actividad**: hoy muestra datos de ejemplo; se conectará a los gastos reales.
- **Datos compartidos**: ahora todo se guarda en `localStorage` del navegador (claves `gastosdisfrutando.grupos` y `gastosdisfrutando.cuenta`). Pasar a datos compartidos entre las dos personas.
- Saldos de los grupos de ejemplo (Charming Life / Charming Travels) son inventados.

## Funcionalidad prevista

- Añadir gastos: importe, concepto, fecha, quién pagó y reparto (50/50, porcentajes o importes exactos).
- Saldo en tiempo real y registro de liquidaciones.
- Historial, categorías, filtros por mes y exportar a CSV.
- Datos compartidos entre las dos personas.

## Limitaciones conocidas

- La otra persona necesita acceso de edición al artefacto (y probablemente cuenta en claude.ai).
- Sin notificaciones push ni modo sin conexión fiable.
- Moneda única: euros. Grupos siempre entre las mismas 2 personas.
