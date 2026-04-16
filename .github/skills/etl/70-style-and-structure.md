# Skill: Estilo y estructura Python

## Objetivo
Código consistente, legible y mantenible.

## Reglas
- Tipado (`list[Model]`, `Iterable[Model]`)
- Funciones pequeñas y puras en transform
- No mezclar I/O con lógica pura
- Ruff/Black si están habilitados en el repo

## Definition of Done
- `ruff check` limpio (si aplica)
- No hay lógica ETL “en el CLI”; el CLI solo orquesta