# Template: PR Checklist (ETL)

## Alcance
- [ ] Este PR implementa: `Extract` / `Transform` / `Load` / `Quality` / `Observability` / `Tests`

## Contratos y etapas
- [ ] Extract emite `Raw*` (sin reglas de negocio)
- [ ] Transform valida fuerte y define política de inválidos (drop/dead-letter/fail)
- [ ] Load es idempotente (replace/append/upsert definido)

## Calidad y seguridad
- [ ] No se loggea PII/secretos
- [ ] Manejo de errores claro (mensajes accionables)
- [ ] Reintentos/timeouts si hay HTTP
- [ ] Transacciones si hay DB

## Configuración
- [ ] Config en YAML/ENV documentada
- [ ] Valores por defecto sensatos
- [ ] README/Runbook actualizado

## Tests
- [ ] Unit tests de transform
- [ ] Integration light del pipeline (tmp_path / DB temporal)
- [ ] Casos de inválidos cubiertos

## Performance
- [ ] Procesamiento por streams/iterators donde aplique
- [ ] Inserts en batch (no row-by-row) si hay DB

## Observabilidad
- [ ] Logs por etapa con conteos
- [ ] Duración o resumen final del run

## Definition of Done
- [ ] `pytest` pasa
- [ ] Lint/format (si aplica) pasa
- [ ] Se puede re-ejecutar sin duplicar datos (si aplica)