# GastosDisfrutando

App para llevar la contabilidad de gastos compartidos entre 2 personas (estilo Splitwise), pensada para usarse sobre todo desde el móvil en vertical.

## Estado

Fase de diseño: 4 bocetos de la pantalla inicial (donde se añaden los gastos).

- Lienzo con los bocetos: https://claude.ai/artifact/PePYNCrFDjppLXP556QkFy (privado)
- Fuentes en [`bocetos/`](bocetos/):
  - `Main.dc.html` — **A · Teclado primero**: importe grande con teclado numérico propio.
  - `Chat.dc.html` — **B · Conversación**: cada gasto es una burbuja; entrada de texto libre.
  - `Tarjetas.dc.html` — **C · Balance y tarjetas**: tarjeta de saldo, formulario con categorías y últimos gastos.
  - `Ticket.dc.html` — **D · Ticket de caja**: estilo ticket, botones grandes «Pagué yo / Pagó Sam».
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
