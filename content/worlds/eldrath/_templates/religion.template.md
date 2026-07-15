---
schema_version: "1.0.0"
id: "religion.{{religion_slug}}"
name: "{{religion_name}}"
content_status: draft
tags: []
aliases: []
summary: "{{summary}}"
references: []
art: []
notes: "{{editorial_notes}}"
tradition_type_key: "{{tradition_type_key}}"
origin:
  description: "{{origin_description}}"
  date: null
  period_key: null
  event_id: null
origin_culture_id: null
cosmology:
  principles:
    - principle_key: "{{cosmology_principle_key}}"
      editorial_name: "{{cosmology_principle_name}}"
      summary: "{{cosmology_principle_summary}}"
  world_structure: []
  creation_accounts: []
  eschatology: []
sacred_entities_or_principles:
  - principle_key: "{{sacred_principle_key}}"
    editorial_name: "{{sacred_principle_name}}"
    type_key: "{{sacred_principle_type_key}}"
    function: "{{sacred_principle_function}}"
doctrines:
  - doctrine_key: "{{doctrine_key}}"
    editorial_name: "{{doctrine_name}}"
    summary: "{{doctrine_summary}}"
    centrality_key: "{{doctrine_centrality_key}}"
    visibility_key: "{{doctrine_visibility_key}}"
values:
  - value_key: "{{value_key}}"
    editorial_name: "{{value_name}}"
    summary: "{{value_summary}}"
virtues:
  - virtue_key: "{{virtue_key}}"
    editorial_name: "{{virtue_name}}"
    summary: "{{virtue_summary}}"
violations:
  - violation_key: "{{violation_key}}"
    editorial_name: "{{violation_name}}"
    summary: "{{violation_summary}}"
taboos:
  - taboo_key: "{{taboo_key}}"
    editorial_name: "{{taboo_name}}"
    summary: "{{taboo_summary}}"
practices:
  - practice_key: "{{practice_key}}"
    editorial_name: "{{practice_name}}"
    purpose: "{{practice_purpose}}"
    participation_rule_keys: []
rites:
  - rite_key: "{{rite_key}}"
    editorial_name: "{{rite_name}}"
    purpose: "{{rite_purpose}}"
    participation_rule_keys: []
festivals:
  - festival_key: "{{festival_key}}"
    editorial_name: "{{festival_name}}"
    calendar_id: null
    calendar_marker_key: null
liturgical_calendar:
  calendar_id: null
  rule_keys: []
sacred_texts:
  - text_key: "{{sacred_text_key}}"
    editorial_title: "{{sacred_text_title}}"
    item_id: null
    status_key: "{{sacred_text_status_key}}"
symbols:
  - symbol_key: "{{religious_symbol_key}}"
    editorial_name: "{{religious_symbol_name}}"
    meaning: "{{religious_symbol_meaning}}"
sacred_object_ids: []
sacred_location_ids: []
funerary_practices:
  - practice_key: "{{funerary_practice_key}}"
    editorial_name: "{{funerary_practice_name}}"
    summary: "{{funerary_practice_summary}}"
afterlife_conceptions:
  - conception_key: "{{afterlife_conception_key}}"
    editorial_name: "{{afterlife_conception_name}}"
    summary: "{{afterlife_conception_summary}}"
magic_position:
  position_key: "{{magic_position_key}}"
  principle_keys: []
  restriction_keys: []
magic_school_positions:
  - school_id: "{{school_id}}"
    position_key: "{{school_position_key}}"
    basis_doctrine_keys: []
participation_rules:
  - participation_rule_key: "{{participation_rule_key}}"
    subject_key: "{{participation_subject_key}}"
    condition_keys: []
    restriction_keys: []
conceptual_organization:
  role_models:
    - role_key: "{{religious_role_key}}"
      editorial_name: "{{religious_role_name}}"
      purpose: "{{religious_role_purpose}}"
  organization_model_keys: []
  authority_principle_keys: []
internal_diversity:
  diversity_keys:
    - "{{diversity_key}}"
  notes: "{{internal_diversity_notes}}"
interpretations:
  - interpretation_key: "{{interpretation_key}}"
    editorial_name: "{{interpretation_name}}"
    scope_key: "{{interpretation_scope_key}}"
    doctrine_keys: []
    distinction: "{{interpretation_distinction}}"
branches:
  - branch_key: "{{branch_key}}"
    editorial_name: "{{branch_name}}"
    distinction: "{{branch_distinction}}"
ancestor_religion_id: null
doctrinal_relations:
  - relation_key: "{{doctrinal_relation_key}}"
    target_religion_id: "{{target_religion_id}}"
    relation_type_key: "{{doctrinal_relation_type_key}}"
    stance_key: "{{doctrinal_stance_key}}"
    foundation_doctrine_keys: []
    symmetric: null
initial_state:
  effective_date: null
  diffusion:
    - region_id: null
      settlement_id: null
      presence_key: "{{diffusion_presence_key}}"
      visibility_key: "{{diffusion_visibility_key}}"
      initial_date: null
      notes: null
deferred_decisions:
  - "{{deferred_decision}}"
---

> **Aviso de template:** este arquivo não é conteúdo real. Ele segue o [contrato de sociedade, instituições e lei](../../../../docs/world/schemas/SOCIETY_INSTITUTIONS_AND_LAW_ENTITIES.md). Placeholders são proibidos em conteúdo `approved`.

# Visão geral

{{overview}}

## Origem

{{origin_lore}}

## Cosmologia

{{cosmology_lore}}

## Doutrinas, valores e tabus

{{doctrines_values_and_taboos}}

## Práticas, ritos e festividades

{{practices_rites_and_festivals}}

## Vida, morte e pós-vida

{{life_death_and_afterlife}}

## Magia

{{magic_position_lore}}

## Organização conceitual

{{conceptual_organization_lore}}

## Diversidade e interpretações

{{diversity_and_interpretations}}

## Relações doutrinárias

{{doctrinal_relations_lore}}

## Difusão inicial

{{initial_diffusion_lore}}

## História

{{history}}

## Observações editoriais

{{editorial_notes_text}}
