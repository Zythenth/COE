---
schema_version: "1.0.0"
id: "family.{{family_slug}}"
name: "{{family_name}}"
content_status: draft
tags: []
aliases: []
summary: "{{summary}}"
references: []
art: []
notes: "{{editorial_notes}}"
family_type_key: "{{family_type_key}}"
origin:
  description: "{{origin_description}}"
  date: null
  period_key: null
  event_id: null
culture_id: null
origin_region_ids: []
shared_identity:
  identity_keys:
    - "{{shared_identity_key}}"
  summary: "{{shared_identity_summary}}"
lineage_concept:
  lineage_key: "{{lineage_concept_key}}"
  belonging_rule_keys: []
  branch_keys: []
  summary: "{{lineage_concept_summary}}"
naming_conventions:
  convention_keys:
    - "{{naming_convention_key}}"
  summary: "{{naming_conventions_summary}}"
traditions:
  - tradition_key: "{{family_tradition_key}}"
    editorial_name: "{{family_tradition_name}}"
    summary: "{{family_tradition_summary}}"
values:
  - value_key: "{{family_value_key}}"
    editorial_name: "{{family_value_name}}"
    summary: "{{family_value_summary}}"
taboos:
  - taboo_key: "{{family_taboo_key}}"
    editorial_name: "{{family_taboo_name}}"
    summary: "{{family_taboo_summary}}"
traditional_profession_ids: []
traditional_religion_ids: []
symbols:
  - symbol_key: "{{family_symbol_key}}"
    editorial_name: "{{family_symbol_name}}"
    meaning: "{{family_symbol_meaning}}"
coat_of_arms:
  description: "{{coat_of_arms_description}}"
motto: null
traditional_seat_location_id: null
dynastic_condition:
  is_dynastic: null
  scope_keys: []
  summary: "{{dynastic_condition_summary}}"
traditional_titles:
  - title_key: "{{traditional_title_key}}"
    editorial_name: "{{traditional_title_name}}"
    scope_key: "{{traditional_title_scope_key}}"
    summary: "{{traditional_title_summary}}"
family_succession_rules:
  - rule_key: "{{family_succession_rule_key}}"
    scope_keys: []
    criterion_keys: []
    exception_keys: []
    summary: "{{family_succession_rule_summary}}"
family_inheritance_rules:
  - rule_key: "{{family_inheritance_rule_key}}"
    asset_category_keys: []
    criterion_keys: []
    exception_keys: []
    summary: "{{family_inheritance_rule_summary}}"
legacy:
  legacy_keys:
    - "{{legacy_key}}"
  summary: "{{legacy_summary}}"
founding_event_ids: []
historical_event_ids: []
content_secret_ids: []
historical_reputation:
  - audience_key: "{{historical_reputation_audience_key}}"
    reputation_key: "{{historical_reputation_key}}"
    summary: "{{historical_reputation_summary}}"
initial_state:
  effective_date: null
  prominence_key: "{{initial_prominence_key}}"
  continuity_status_key: "{{initial_continuity_status_key}}"
  dynastic_status_key: "{{initial_dynastic_status_key}}"
  notes: null
deferred_decisions:
  - "{{deferred_decision}}"
---

> **Aviso de template:** este arquivo não é conteúdo real. Ele segue o [contrato de sociedade, instituições e lei](../../../../docs/world/schemas/SOCIETY_INSTITUTIONS_AND_LAW_ENTITIES.md). Placeholders são proibidos em conteúdo `approved`; membros e parentesco concreto pertencem aos futuros NPCs e eventos.

# Visão geral

{{overview}}

## Origem e identidade

{{origin_and_identity}}

## Linhagem e convenções de nome

{{lineage_and_naming}}

## Tradições, valores e tabus

{{traditions_values_and_taboos}}

## Condição dinástica

{{dynastic_condition_lore}}

## Símbolos, brasão e lema

{{symbols_coat_of_arms_and_motto}}

## Títulos, sucessão e herança

{{titles_succession_and_inheritance}}

## Legado e reputação histórica

{{legacy_and_historical_reputation}}

## Vínculos culturais, religiosos e profissionais

{{cultural_religious_and_professional_links}}

## Vínculos institucionais derivados

{{derived_institutional_links}}

## Segredos familiares

{{family_secrets}}

## História

{{history}}

## Observações editoriais

{{editorial_notes_text}}
