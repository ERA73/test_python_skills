# Skill: Load (destinos)

## Objetivo
Persistir datos transformados de forma segura e idempotente.

## Checklist
- [ ] Transacción
- [ ] Modo `replace/append/upsert` definido
- [ ] Idempotencia: claves/constraints
- [ ] Batch inserts / executemany
- [ ] Logging: filas escritas, duración

## Definition of Done
- Se puede re-ejecutar sin duplicar (si aplica)
- Falla con error claro si el schema destino no cuadra