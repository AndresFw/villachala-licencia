# Licencia — Villa Chala (módulo de Transferencias)

Este repositorio es **público a propósito**: la aplicación lee `licencia.json` desde internet.
Cualquiera puede **leerlo**, pero solo el dueño del repositorio (y los colaboradores que él agregue) puede **editarlo**.

## Cómo cambiarlo
Abre `licencia.json` → lápiz (Edit) → *Commit changes*. La app lo nota en unos 10 minutos.

| Campo | Qué hace |
|---|---|
| `transfers` | `true` = el módulo funciona · `false` = suspendido (falta de pago) |
| `message` | Texto que ve el cliente cuando está suspendido |
| `dueDate` | Vencimiento de la mensualidad, `AAAA-MM-DD`. Con `transfers: true` el módulo sigue funcionando aunque pase la fecha; solo sale el aviso |
| `warnDays` | Días antes de `dueDate` en que empieza a salir el aviso pequeño (por defecto 5) |
| `warnMessage` | (opcional) Texto propio para el aviso; si no se pone, se arma solo |

## Qué ve el cliente
- `transfers: true` y falta poco para `dueDate`: aviso pequeño "renueva para evitar bloqueos".
- `transfers: false`: el módulo de Transferencias queda bloqueado y muestra `message`.
- Sin internet o archivo ilegible: el módulo también queda bloqueado, con su explicación.

> No guardes aquí contraseñas ni datos privados: el repositorio es público.
