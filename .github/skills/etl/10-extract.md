# Skill: Extract (fuentes)

## Objetivo
Implementar extracción sin lógica de negocio.

## Checklist
- [ ] Un extractor por fuente (CSV, API, DB)
- [ ] Timeouts/retries si es HTTP
- [ ] Emitir `Iterable[RawRecord]` o `Iterator[RawRecord]`
- [ ] Logging: inicio/fin y conteo
- [ ] Errores: parse errors -> warning + skip, o “dead-letter” (definir)

## Reglas
- No deduplicar aquí
- No normalizar strings aquí (salvo lo mínimo para parse)
- No aplicar validación fuerte (eso va en Transform)

## Definition of Done
- Extractor devuelve objetos `Raw*` consistentes
- Maneja filas/records inválidos sin tumbar todo el pipeline