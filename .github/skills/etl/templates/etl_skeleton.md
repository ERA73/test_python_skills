# Template: ETL Skeleton (copia y rellena)

## Nombre del ETL
- **ETL id**: `<etl_id>` (ej: `users_daily`)
- **Owner**: `<team_or_person>`
- **Frecuencia**: `<cron_or_schedule>` (ej: daily 02:00 UTC)
- **SLA**: `<minutes>` min
- **Dataset**: `<domain>` (ej: users, billing, events)

## Propósito
Describe qué mueve este ETL, desde dónde hacia dónde, y para qué.

## Fuentes (Extract)
- Tipo: `<csv|http|db|s3|...>`
- Ubicación/endpoint: `<path_or_url_or_conn>`
- Volumen estimado: `<rows/day>`
- Autenticación: `<none|token|oauth|...>`
- Consideraciones: paginación, rate-limit, ventanas de tiempo

## Transformaciones (Transform)
- Reglas de limpieza:
  - [ ] trim/lowercase en `<fields>`
  - [ ] normalización de fechas `<format>`
- Reglas de negocio:
  - [ ] filtros: `<criteria>`
  - [ ] derivaciones: `<new_fields>`
- Dedupe:
  - Key: `<fields>`
  - Estrategia: `<keep_latest|keep_first|...>`
- Registros inválidos:
  - Política: `<drop|dead_letter|fail_pipeline>`
  - Motivos esperados: `<examples>`

## Destino (Load)
- Tipo: `<sqlite|postgres|bigquery|...>`
- Tabla/dataset: `<target>`
- Modo: `<replace|append|upsert>`
- Clave primaria / unique keys: `<keys>`
- Idempotencia: cómo se garantiza

## Data Quality Checks
- [ ] Uniqueness en `<field>`
- [ ] Null-rate `<field>` <= `<threshold>`
- [ ] Volumen mínimo/máximo: `<range>`
- [ ] Freshness: fecha >= `<watermark>`

## Observabilidad
- Logs esperados por etapa (conteos)
- Métricas (si aplica): duración, invalid_count, loaded_count

## Tests mínimos
- Unit tests: transform (casos válidos/inválidos)
- Integration light: run pipeline con tmp_path / DB temporal

## Runbook (operación)
- Cómo correr local:
  - `python -m etl.cli run --config <config>`
- Cómo re-ejecutar:
  - reemplazo/append/upsert
- Cómo investigar fallos:
  - logs, dónde quedan archivos intermedios, dead-letter