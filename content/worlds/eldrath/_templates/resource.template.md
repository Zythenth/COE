---
schema_version: "1.0.0"
id: "resource.{{resource_slug}}"
name: "{{resource_name}}"
content_status: draft
tags: []
aliases: []
summary: "{{summary}}"
references: []
art: []
notes: "{{editorial_notes}}"
resource_category_key: "{{resource_category_key}}"
base_unit_key: "{{unit_key}}"
fungible: null
renewable: null
perishable: null
magical: null
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
quality_keys: []
extraction_methods:
  - method_id: "{{extraction_method_id}}"
    method_type_key: "{{extraction_method_type_key}}"
    required_profession_ids: []
    required_location_type_keys: []
    required_item_ids: []
    inputs:
      - flow_id: "{{extraction_input_flow_id}}"
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
    outputs:
      - flow_id: "{{extraction_output_flow_id}}"
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
    duration:
      value: null
      unit_key: null
    condition_keys: []
    risk_keys: []
    notes: null
production_methods:
  - method_id: "{{production_method_id}}"
    method_type_key: "{{production_method_type_key}}"
    required_profession_ids: []
    required_location_type_keys: []
    required_item_ids: []
    inputs: []
    outputs: []
    duration:
      value: null
      unit_key: null
    condition_keys: []
    risk_keys: []
    notes: null
consumption_uses:
  - use_id: "{{consumption_use_id}}"
    use_key: "{{consumption_use_key}}"
    consumption_flows: []
    required_profession_ids: []
    required_location_type_keys: []
    required_item_ids: []
    condition_keys: []
    notes: null
legal_status_key: null
hazard_keys: []
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
---

> **Aviso de template:** este arquivo não é conteúdo real. Placeholders são exclusivos de `_templates/` e são proibidos em conteúdo `approved`.

# Visão geral

{{overview}}

## Natureza

{{nature}}

## Obtenção

{{extraction}}

## Processamento

{{processing}}

## Usos

{{uses}}

## Armazenamento

{{storage}}

## Riscos

{{risks}}

## Valor econômico

{{economic_value}}

## Relação com magia

{{magic_relation}}

## Legalidade

{{legality}}

## História

{{history}}

## Observações editoriais

{{editorial_notes_text}}
