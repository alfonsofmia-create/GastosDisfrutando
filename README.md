# GastosDisfrutando

App para llevar la contabilidad de gastos compartidos entre 2 personas (estilo Splitwise), pensada para usarse sobre todo desde el móvil en vertical.

## Estado

App en uso y diseño en curso. Estilo elegido: **ticket de caja** (amarillo, monoespaciada, bordes negros gruesos).

- **App** (datos compartidos y permanentes): https://claude.ai/artifact/VwKj8MkNLWsE7tS8WjSmZ8 — fuente en [`app/index.html`](app/index.html). Cada persona entra con su cuenta de claude.ai y se registra en Cuenta. Datos en la base de datos del artefacto: colecciones `personas` (id de usuario de claude.ai), `grupos`, `gastos` y el documento `config/categorias`. En Inicio, tocar un grupo abre «Añadir gasto» en ese grupo (con el subgrupo del último gasto); la foto del grupo se cambia al editarlo en Grupos.
- **Diseño**: la cabecera muestra «GASTOS_DISFRUTANDO» centrado, con «←» a la izquierda que vuelve a la pantalla anterior (deshabilitado en Inicio); el título de cada pantalla va al principio del contenido.
- **Archivo histórico** (no se mantiene sincronizado con la app): lienzo de bocetos https://claude.ai/artifact/PePYNCrFDjppLXP556QkFy y sus fuentes en [`bocetos/`](bocetos/). Se usa solo para dibujar pantallas nuevas complejas antes de construirlas.

## Decisiones tomadas

- **Diseño**: opción D, «ticket de caja». Fondo `#FFD43B`, texto `#111111`, fuente IBM Plex Mono, bordes negros de 3px, sombras planas. Verde `#1C6B3A` con «+» = te deben; rojo `#B3261E` con «−» = debes.
- **Uso**: 90 % desde móvil en vertical (pantallas de 390×844).
- **Personas**: cada usuario se registra en Cuenta; su nombre es visible para todos y puede añadirse a cualquier grupo. Cada grupo tiene sus miembros (el usuario no tiene que estar en todos); los subgrupos los heredan al crearse y se editan entre los miembros del grupo. Añadir a alguien a un grupo no lo añade a subgrupos existentes; quitarlo sí lo quita de ellos. No se puede quitar a quien ya tiene gastos.
- **Gastos**: pagador elegido entre los miembros del subgrupo; reparto igual (con exclusiones), por porcentajes (suman 100 %) o importes exactos (suman el total). Saldos por persona.
- **Categorías**: sin categorías iniciales; el usuario las crea y se guardan para el futuro. Se sugieren según gastos anteriores con palabras en común en el concepto, y se pueden cambiar.
- **Moneda**: solo euros en toda la aplicación.
- **Grupos**: con foto opcional y un solo nivel de subgrupos.
- **Menú inferior**: Inicio · Grupos · Actividad · Cuenta (se quitó «Amigos»).
- **Inicio**: sin lupa, sin filtro y sin textos de grupos saldados; se quitó «Gastos sin grupo».
- **Forma de trabajar**: el usuario define cada pantalla paso a paso; no se construye nada sin su indicación. Cada cambio se hace y se prueba en la app; se sube a GitHub solo cuando el usuario lo pide.

## Pendiente

- **Tipos de cambio** en subgrupos: solo dibujado. Con la decisión de «solo euros», confirmar si se elimina.
- **Liquidaciones**: registrar pagos entre personas.
- **Grupos de ejemplo** (Charming Life / Charming Travels): sin miembros; se asignarán manualmente.
- **Permisos**: hoy cualquier persona que abra la app puede editar o borrar grupos. Valorar restringirlo.

## Funcionalidad prevista

- Añadir gastos: importe, concepto, fecha, quién pagó y reparto (50/50, porcentajes o importes exactos).
- Saldo en tiempo real y registro de liquidaciones.
- Historial, categorías, filtros por mes y exportar a CSV.
- Datos compartidos entre las dos personas.

## Limitaciones conocidas

- La otra persona necesita acceso de edición al artefacto (y probablemente cuenta en claude.ai).
- Sin notificaciones push ni modo sin conexión fiable.
- Moneda única: euros.
- La app solo la pueden usar personas de la misma organización de claude.ai, con el artefacto compartido.
- Capacidad de la base de datos: unos 25.000 documentos (cada gasto es uno).
