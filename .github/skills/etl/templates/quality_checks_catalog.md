# Template: Catálogo de Data Quality Checks

Usa este documento para estandarizar checks reutilizables por ETL.

## Checks de esquema/contrato
- Schema drift: columnas nuevas/faltantes
- Tipos esperados (date/int/bool)

## Checks de completitud
- Null-rate por campo: `nulls/total <= threshold`
- Campos obligatorios no vacíos

## Checks de unicidad
- Unique key: `<key_fields>`
- Duplicados permitidos: sí/no (explicar)

## Checks de validez
- Rango numérico: min/max
- Fechas: no futuras, ventana esperada
- Regex: emails/ids

## Checks de volumen
- Conteo mínimo/máximo por corrida
- Comparación vs. promedio histórico (si existe)

## Checks de frescura (freshness)
- watermark actualizado
- max(signup_date) >= hoy-1 (ejemplo)

## Severidad
Define severidad por check:
- **critical**: falla el pipeline
- **warning**: log y continua