# Skill: ETL Overview (arquitectura y contrato)

## Objetivo
Crear ETLs con etapas separadas (Extract/Transform/Load), contratos estables y buena mantenibilidad.

## Principios
1. Cada etapa es un módulo separado: `extract/`, `transform/`, `load/`.
2. Extract **no valida negocio**: solo parsea y emite `Raw*`.
3. Transform aplica reglas + validación fuerte y emite modelos limpios (`*`).
4. Load no reinterpreta datos: solo persiste, con transacciones.
5. Todo ETL debe tener:
   - Config clara
   - Logging
   - Tests
   - Manejo de errores y “dead-letter” o descarte explícito

## Output esperado
- Nuevos archivos del ETL
- Tests unitarios mínimos
- Documentación breve (cómo correr)