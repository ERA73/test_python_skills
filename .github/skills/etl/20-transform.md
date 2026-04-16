# Skill: Transform (normalización + validación)

## Objetivo
Convertir `Raw*` a modelos limpios `*` aplicando reglas de negocio.

## Checklist
- [ ] Normalización (trim, lower, formatos de fecha)
- [ ] Validación fuerte con Pydantic (o equivalente)
- [ ] Dedupe (si aplica) con estrategia documentada
- [ ] Contadores: total, válidos, inválidos, motivos

## Reglas
- Transform es el lugar para decidir “drop vs fix”
- Nunca ocultar silenciosamente: si se cae un record, loggear motivo (sin PII sensible)

## Definition of Done
- Se puede explicar qué registros se descartan y por qué
- Los modelos de salida son estables (contrato)