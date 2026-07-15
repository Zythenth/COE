---
schema_version: "1.0.0"
id: "profession.{{profession_slug}}"
name: "{{profession_name}}"
content_status: draft
tags: []
aliases: []
summary: "{{summary}}"
references: []
art: []
notes: "{{editorial_notes}}"
profession_category_key: "{{profession_category_key}}"
required_skill_keys: []
recommended_attribute_keys: []
training_paths:
  - path_id: "{{training_path_id}}"
    path_type_key: "{{training_path_type_key}}"
    entry_requirement_keys: []
    required_profession_ids: []
    institution_ids: []
    duration:
      value: null
      unit_key: null
    applicable_rank_keys: []
    condition_keys: []
    notes: null
rank_keys: []
typical_tasks:
  - task_key: "{{task_key}}"
    applicable_rank_keys: []
    required_skill_keys: []
    required_item_ids: []
    condition_keys: []
    duration:
      value: null
      unit_key: null
    notes: null
production_profiles:
  - profile_id: "{{production_profile_id}}"
    applicable_rank_keys: []
    production_flows:
      - flow_id: "{{production_flow_id}}"
        resource_id: null
        item_id: null
        quantity:
          value: null
          unit_key: null
        period_key: null
        required_profession_ids: []
        required_location_type_keys: []
        required_item_ids: []
        input_refs: []
        output_refs: []
        condition_keys: []
        waste_outputs: []
        notes: null
    consumption_flows: []
    condition_keys: []
    modifiers:
      - modifier_key: "{{modifier_key}}"
        operation: "{{modifier_operation}}"
        value: null
        condition_keys: []
        notes: null
    notes: null
required_item_ids: []
consumed_resource_ids: []
produced_resource_ids: []
produced_item_ids: []
workplace_type_keys: []
institution_ids: []
faction_ids: []
legal_requirements:
  - requirement_key: "{{legal_requirement_key}}"
    jurisdiction_id: null
    law_id: null
    license_key: null
    issuing_authority_id: null
    applicable_rank_keys: []
    condition_keys: []
    notes: null
magical_requirements:
  - requirement_key: "{{magical_requirement_key}}"
    required_school_ids: []
    required_spell_ids: []
    required_affinity_keys: []
    applicable_rank_keys: []
    condition_keys: []
    notes: null
risks:
  - risk_key: "{{risk_key}}"
    applicable_rank_keys: []
    condition_keys: []
    notes: null
social_status:
  status_key: null
  variation_keys: []
  condition_keys: []
  notes: null
income_model:
  model_keys: []
  payment_basis_key: null
  reference_compensation:
    money:
      amount: null
      currency_key: null
    quantity_basis:
      value: null
      unit_key: null
    quality_key: null
    settlement_id: null
    effective_date: null
    source: null
  condition_keys: []
  notes: null
---

> **Aviso de template:** este arquivo não é conteúdo real. Placeholders são exclusivos de `_templates/` e são proibidos em conteúdo `approved`. `rank_keys` usa somente estágios aplicáveis entre `apprentice`, `worker`, `specialist`, `master`, `leader` e `retired`.

# Visão geral

{{overview}}

## Função social

{{social_function}}

## Responsabilidades

{{responsibilities}}

## Formação

{{training}}

## Progressão

{{progression}}

## Tarefas

{{tasks}}

## Ferramentas

{{tools}}

## Recursos

{{resources}}

## Produção

{{production}}

## Riscos

{{risks_text}}

## Relação com magia

{{magic_relation}}

## Instituições

{{institutions}}

## Prestígio

{{prestige}}

## Observações editoriais

{{editorial_notes_text}}
