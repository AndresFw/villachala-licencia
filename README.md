# Licencia — Villa Chala (módulo de Transferencias)

Este repositorio es **público a propósito**: la aplicación lee `licencia.json` desde internet.
Cualquiera puede **leerlo**, pero solo el dueño del repositorio (y los colaboradores que él agregue) puede **editarlo**.

## Cómo cambiarlo
Abre `licencia.json` → lápiz (Edit) → *Commit changes*. La app lo nota en hasta ~10 minutos (GitHub tarda ~5 min en refrescar el archivo y la app lo recuerda otros 5).

| Campo | Qué hace |
|---|---|
| `transfers` | `true` = el módulo funciona · `false` = suspendido (falta de pago) |
| `message` | Texto que ve el cliente cuando está suspendido |
| `dueDate` | **Último día** en que el módulo funciona (`AAAA-MM-DD`). Al día siguiente se **bloquea solo**. Para renovar, sube la fecha un mes |
| `graceDays` | (opcional) Días de gracia después de `dueDate` en los que todavía funciona, con aviso. Por defecto 0 |
| `warnDays` | Días antes de `dueDate` en que empieza a salir el aviso pequeño (por defecto 5) |
| `warnMessage` | (opcional) Texto propio para el aviso; si no se pone, se arma solo |

## Qué ve el cliente
- `transfers: true` y faltan `warnDays` días o menos para `dueDate`: aviso pequeño "renueva para evitar bloqueos". El día siguiente a `dueDate` el módulo se bloquea solo.
- `transfers: false`: el módulo de Transferencias queda bloqueado y muestra `message`.
- Sin internet o archivo ilegible: el módulo también queda bloqueado, con su explicación.

> No guardes aquí contraseñas ni datos privados: el repositorio es público.
