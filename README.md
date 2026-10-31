# claude-mods

Mods (plugins de observación y guardias) para [Claude Code](https://code.claude.com),
escritos en TypeScript sobre la API de mods del motor. Cada mod vive en su carpeta
dentro de `mods/` y se puede cargar o apagar por separado.

## Mods

| Mod | Qué hace |
|---|---|
| [`caveman-badge`](mods/caveman-badge) | Muestra en la línea de estado el modo caveman (aproximado). |
| [`ctx-budget`](mods/ctx-budget) | Avisa cuando el contexto cruza el 70 % y el 85 %. |
| [`guard-kill-visible`](mods/guard-kill-visible) | Avisa cuando un comando mata procesos por nombre. Solo avisa, no bloquea. |
| [`secret-guard`](mods/secret-guard) | Bloquea escribir secretos en archivos y comandos; pregunta antes de leer archivos sensibles. |
| [`sound-notify`](mods/sound-notify) | Avisa al terminar un turno largo y cuando Claude espera un permiso. |
| [`spec-gate`](mods/spec-gate) | Pregunta una vez por sesión si se edita código de producción sin una spec reciente. |
| [`tdd-gate`](mods/tdd-gate) | Pregunta una vez por sesión si se edita código de producción sin haber tocado antes una prueba. |
| [`tablero`](mods/tablero) | Panel en español con carpeta, modelo, costo, contexto, subagentes, permisos y uso. Derivado de Flightdeck (MIT). |

Todos los mods son de observación o de guardia: no reescriben llamadas a herramientas
ni prompts. Los guardias (`secret-guard`, `spec-gate`, `tdd-gate`) actúan solo
sobre las llamadas que indican en su README.

## Probar

Cada mod trae sus pruebas (`hooks/*.test.ts`). Con Claude Code instalado:

```bash
claude plugin test mods/<nombre>
claude plugin validate mods/<nombre>
```

## Cargar un mod

Mientras no haya un marketplace publicado, carga la carpeta del mod directamente:

```bash
claude --plugin-dir ./mods/<nombre>
```

## Licencia

MIT. Ver [LICENSE](LICENSE). `tablero` conserva el aviso de copyright original de
Flightdeck en su propia carpeta.
