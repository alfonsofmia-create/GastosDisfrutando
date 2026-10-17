# GastosDisfrutando

App para llevar la contabilidad de gastos compartidos entre 2 personas (estilo Splitwise), pensada para usarse sobre todo desde el móvil en vertical.

## Estado

App en uso y diseño en curso. Estilo elegido: **ticket de caja** (amarillo, monoespaciada, bordes negros gruesos).

- **App** (datos compartidos y permanentes): https://claude.ai/artifact/VwKj8MkNLWsE7tS8WjSmZ8 — fuente en [`app/index.html`](app/index.html). Cada persona entra con su cuenta de claude.ai y se registra en Cuenta. Datos en la base de datos del artefacto: colecciones `personas` (id de usuario de claude.ai), `grupos`, `gastos` y el documento `config/categorias`.
- Lienzo con los bocetos: https://claude.ai/artifact/PePYNCrFDjppLXP556QkFy (privado)
- Fuentes en [`bocetos/`](bocetos/):
  - `Inicio.dc.html` — inicio: saldo general calculado con los gastos (y desglose por persona), grupos con su saldo (foto configurable), crear grupo, «Añadir gasto» y barra inferior (Inicio · Grupos · Actividad · Cuenta).
  - `NuevoGrupo.dc.html` — crear grupo: foto, nombre (obligatorio, sin duplicados), miembros (obligatorio, de las personas registradas) y subgrupos opcionales, que heredan los miembros.
  - `AnadirGasto.dc.html` — añadir gasto: importe, concepto, categoría (obligatoria, predictiva e incremental), grupo y subgrupo (obligatorios), fecha, quién pagó (miembros del subgrupo) y reparto (igual con exclusiones, % o importes exactos).
  - `Grupos.dc.html` — lista de grupos (editar nombre, miembros y subgrupos, borrar con confirmación, añadir); al abrir un grupo, sus subgrupos (1 nivel: crear, editar nombre y miembros, borrar); en cada subgrupo, sus miembros y «Tipos de cambio» (solo dibujado).
  - `Actividad.dc.html` — gastos reales agrupados por día, con importe desde el punto de vista del usuario.
  - `Cuenta.dc.html` — datos del usuario (nombre, email, foto). Al guardar el nombre, el usuario queda registrado en «Personas registradas», visibles para todos.
  - `canvas.json` — disposición de los bocetos en el lienzo.

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
- **Forma de trabajar**: el usuario define cada pantalla paso a paso; no se construye nada sin su indicación. Cada cambio se prueba en el lienzo y se sube a GitHub solo cuando el usuario lo pide.

## Pendiente

- **Tipos de cambio** en subgrupos: solo dibujado. Con la decisión de «solo euros», confirmar si se elimina.
- **Liquidaciones**: registrar pagos entre personas.
- **Grupos de ejemplo** (Charming Life / Charming Travels): sin miembros; se asignarán manualmente.
- **Permisos**: hoy cualquier persona que abra la app puede editar o borrar grupos. Valorar restringirlo.
- **Bocetos y app**: los bocetos (`bocetos/`) siguen guardando en `localStorage`; la app es la versión real. Mantener ambos alineados.

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
