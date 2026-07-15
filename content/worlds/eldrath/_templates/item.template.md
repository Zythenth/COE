---
schema_version: "1.0.0"
id: "item.{{item_slug}}"
name: "{{item_name}}"
content_status: draft
tags: []
aliases: []
summary: "{{summary}}"
references: []
art: []
notes: "{{editorial_notes}}"
item_category_key: "{{item_category_key}}"
stackable: null
unique_definition: null
provenance_mode: null
base_unit_key: null
default_stack_limit:
  value: null
  unit_key: null
durability:
  enabled: null
  maximum: null
  degradation_keys: []
  repair_profession_ids: []
  repair_resource_ids: []
  notes: null
quality_keys: []
resource_composition:
  - resource_id: "{{resource_id}}"
    quantity:
      value: null
      unit_key: null
    quality_key: null
    condition_keys: []
    notes: null
production_methods:
  - method_id: "{{production_method_id}}"
    method_type_key: "{{production_method_type_key}}"
    required_profession_ids: []
    required_location_type_keys: []
    required_item_ids: []
    inputs:
      - flow_id: "{{production_input_flow_id}}"
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
    outputs: []
    duration:
      value: null
      unit_key: null
    condition_keys: []
    risk_keys: []
    notes: null
required_profession_ids: []
usage_keys: []
legal_status_key: null
magical: null
magical_properties:
  magic_school_ids: []
  effect_applications:
    - application_key: "{{item_effect_application_key}}"
      magic_effect_id: "magic_effect.{{item_magic_effect_slug}}"
      target_binding_key: "{{item_effect_target_binding_key}}"
      parameters:
        - parameter_key: "{{item_effect_parameter_key}}"
          number_value: null
          boolean_value: null
          key_value: null
          entity_id: null
          quantity:
            value: null
            unit_key: null
      condition_keys: []
      trigger_keys: []
  activation_rules:
    - activation_key: "{{item_activation_key}}"
      trigger_keys: []
      condition_keys: []
      costs:
        - cost_key: "{{item_activation_cost_key}}"
          category_key: "{{item_activation_cost_category_key}}"
          bearer_key: "{{item_activation_cost_bearer_key}}"
          timing_key: "{{item_activation_cost_timing_key}}"
          resource_id: null
          item_id: null
          quantity:
            value: null
            unit_key: null
          condition_key: null
          mechanical_state_key: null
          consumption_mode_key: "{{item_activation_cost_consumption_mode_key}}"
          deferred_trigger_key: null
          condition_keys: []
          notes: null
      effect_application_keys: []
      notes: null
  regulation_tag_keys: []
  notes: null
reference_value:
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
storage_requirements:
  - condition_keys: []
    maximum_duration:
      value: null
      unit_key: null
    required_location_type_keys: []
    loss_rate:
      quantity:
        value: null
        unit_key: null
      period_key: null
    hazard_keys: []
    notes: null
---

> **Aviso de template:** este arquivo não é conteúdo real. Placeholders são exclusivos de `_templates/` e são proibidos em conteúdo `approved`. A definição nunca registra proprietário, localização ou quantidade atual de uma instância; artefatos apontam para o item-base e a relação inversa é derivada.

# Visão geral

{{overview}}

## Função

{{function}}

## Materiais

{{materials}}

## Produção

{{production}}

## Uso

{{use}}

## Durabilidade

{{durability_text}}

## Reparo

{{repair}}

## Qualidade

{{quality}}

## Armazenamento

{{storage}}

## Legalidade

{{legality}}

## Propriedades mágicas

{{magical_properties}}

## Relação derivada com artefatos

{{artifact_relation}}

## História

{{history}}

## Observações editoriais

{{editorial_notes_text}}
