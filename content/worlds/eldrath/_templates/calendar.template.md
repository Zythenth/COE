---
schema_version: "1.0.0"
id: "calendar.{{calendar_slug}}"
name: "{{calendar_name}}"
content_status: draft
tags: []
aliases: []
summary: "{{summary}}"
references: []
art: []
notes: "{{editorial_notes}}"
epoch:
  name: "{{epoch_name}}"
  description: null
eras:
  - id: "{{era_id}}"
    name: "{{era_name}}"
    order: "{{era_order}}"
months:
  - id: "{{month_id}}"
    name: "{{month_name}}"
    order: "{{month_order}}"
    days: "{{days_in_month}}"
    season_id: null
weekdays:
  - id: "{{weekday_id}}"
    name: "{{weekday_name}}"
    order: "{{weekday_order}}"
seasons:
  - id: "{{season_id}}"
    name: "{{season_name}}"
    order: "{{season_order}}"
year_rules:
  common_year: "{{common_year_rule}}"
  exceptional_year: null
  day_count_method: "{{day_count_method}}"
date_format: null
abbreviations: {}
recurring_events: []
---

> **Aviso de template:** este arquivo não é conteúdo real. Placeholders são proibidos em conteúdo `approved`.

# Funcionamento

{{calendar_operation}}

## Uso cultural

{{cultural_use}}

## Observações editoriais

{{editorial_notes_text}}
