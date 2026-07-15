---
schema_version: "1.0.0"
id: "settlement.{{settlement_slug}}"
name: "{{settlement_name}}"
content_status: draft
tags: []
aliases: []
summary: "{{summary}}"
references:
  - "{{related_entity_id}}"
art: []
notes: "{{editorial_notes}}"
region_id: "{{region_id}}"
settlement_type: "{{settlement_type}}"
administrative_roles: []
ruler_id: null
governing_faction_ids: []
local_law_ids: []
dominant_religion_ids: []
tolerated_religion_ids: []
institution_ids: []
initial_state:
  population: null
  housing_capacity: null
  wealth: null
  security: null
  health: null
  sanitation: null
  literacy: null
  openness_to_outsiders: null
  acceptance_of_magic: null
  prosperity: null
  tension: null
production:
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
consumption:
  - flow_id: "{{consumption_flow_id}}"
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
trade:
  - trade_id: "{{trade_id}}"
    resource_id: null
    item_id: null
    quantity:
      value: null
      unit_key: null
    period_key: null
    direction: "{{trade_direction_key}}"
    counterparty_id: null
    initial_price:
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
initial_stocks:
  - resource_id: null
    item_id: null
    quantity:
      value: null
      unit_key: null
    quality_key: null
    storage_location_id: null
    reserved_quantity:
      value: null
      unit_key: null
    notes: null
initial_prices:
  - resource_id: null
    item_id: null
    price:
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
faction_presence:
  - faction_id: "{{faction_id}}"
    presence: null
    visibility: "{{visibility_key}}"
    notes: null
local_problems:
  - problem_key: "{{problem_key}}"
    severity: null
    visibility: "{{visibility_key}}"
    related_entity_ids: []
    notes: null
---

> **Aviso de template:** este arquivo não é conteúdo real. Placeholders são proibidos em conteúdo `approved`. Produção, consumo, comércio, estoques e preços representam somente capacidades, relações e valores iniciais; valores atuais pertencem ao estado futuro da simulação.

# Visão geral

{{overview}}

## Posição regional

{{regional_position}}

## Governo

{{government}}

## População

{{population}}

## Bairros e organização

{{districts_and_organization}}

## Economia

{{economy}}

## Comércio

{{trade_text}}

## Instituições

{{institutions}}

## Religião

{{religion}}

## Magia

{{magic}}

## Cotidiano

{{daily_life}}

## Problemas locais

{{local_problems_text}}

## Eventos recentes

{{recent_events}}

## História

{{history}}

## Observações editoriais

{{editorial_notes_text}}
