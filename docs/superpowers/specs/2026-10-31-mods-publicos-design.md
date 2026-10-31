# Diseño: repositorio público de mods de Claude Code

Fecha: 2026-10-31. Estado: aprobado por el autor (decisiones de repositorio, lista de mods y licencia).

## Intención

Publicar en un repositorio aparte los mods genéricos de Claude Code, para que otra
persona pueda cargarlos o usarlos como base. No se mezclan con la configuración
personal (`claude-code-entorno`), que está pensada para una sola máquina.

## Alcance

Incluidos: `caveman-badge`, `ctx-budget`, `guard-kill-visible`, `secret-guard`,
`sound-notify`, `spec-gate`, `tdd-gate` y `tablero` (derivado de Flightdeck, MIT).

Excluidos:
- Mods ligados a servicios o plugins internos de una empresa.
- Mods ligados a una cuenta o carpeta personal de sincronización (OneDrive).
- Specs, planes y ledgers del trabajo interno.
- Archivos de tipos del motor (`.d.ts` del proveedor): se generan localmente, no se redistribuyen.

## Reglas

1. Ninguna ruta de usuario, nombre de empresa, correo, IP, clave ni nombre de equipo.
   Las pruebas usan rutas de ejemplo (`C:\Users\usuario\...`).
2. Licencia MIT en la raíz. `tablero` conserva su aviso MIT original.
3. Cada mod pasa `claude plugin test` y `claude plugin validate` antes de publicar.
4. No hay historial heredado: el repositorio empieza desde cero, sin los commits de los mods originales.

## Verificación

- Pruebas por mod en verde (ver el mensaje de commit).
- Búsqueda de datos privados sobre todos los archivos del repo antes del primer commit.
- Pendiente de la publicación: crear el repositorio remoto y hacer push, solo con confirmación explícita.
