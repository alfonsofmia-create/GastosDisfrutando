# GastosDisfrutando

App para llevar la contabilidad de gastos compartidos entre 2 personas (estilo Splitwise), pensada para usarse sobre todo desde el móvil en vertical.

## Estado

Fase de diseño. Estilo elegido: **ticket de caja** (amarillo, monoespaciada, bordes negros gruesos).

- Lienzo con los bocetos: https://claude.ai/artifact/PePYNCrFDjppLXP556QkFy (privado)
- Fuentes en [`bocetos/`](bocetos/):
  - `Inicio.dc.html` — inicio: deuda total, grupos (con foto configurable), crear grupo, «Añadir gasto» y barra inferior (Inicio · Grupos · Actividad · Cuenta). Enlaces navegables.
  - `NuevoGrupo.dc.html` — crear grupo (pendiente de definir).
  - `AnadirGasto.dc.html` — añadir gasto (pendiente de definir).
  - `Grupos.dc.html` — lista de grupos (editar, borrar con confirmación, añadir); al abrir un grupo, sus subgrupos (1 nivel: crear, editar, borrar); en cada subgrupo, «Tipos de cambio» (solo dibujado, pendiente de definir).
  - `Actividad.dc.html` — últimos movimientos agrupados por día.
  - `Cuenta.dc.html` — datos básicos del usuario: editar nombre, email y moneda (con validación) y foto de perfil. De momento se guarda solo en el navegador.
  - `canvas.json` — disposición de los bocetos en el lienzo.

## Funcionalidad prevista

- Añadir gastos: importe, concepto, fecha, quién pagó y reparto (50/50, porcentajes o importes exactos).
- Saldo en tiempo real y registro de liquidaciones.
- Historial, categorías, filtros por mes y exportar a CSV.
- Datos compartidos entre las dos personas.

## Limitaciones conocidas

- La otra persona necesita acceso de edición al artefacto (y probablemente cuenta en claude.ai).
- Sin notificaciones push ni modo sin conexión fiable.
- Varias monedas: tipo de cambio manual.
