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
  - resource_id: "{{resource_id}}"
    amount: null
    unit: null
    period: "{{period_key}}"
    modifiers: []
    notes: null
consumption:
  - resource_id: "{{resource_id}}"
    amount: null
    unit: null
    period: "{{period_key}}"
    modifiers: []
    notes: null
trade:
  - resource_id: "{{resource_id}}"
    amount: null
    unit: null
    period: "{{period_key}}"
    direction: "{{trade_direction_key}}"
    counterparty_id: null
    modifiers: []
    notes: null
resource_stocks:
  - resource_id: "{{resource_id}}"
    amount: null
    unit: null
    capacity: null
    notes: null
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

> **Aviso de template:** este arquivo não é conteúdo real. Placeholders são proibidos em conteúdo `approved`.

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
