---
schema_version: "1.0.0"
id: "region.{{region_slug}}"
name: "{{region_name}}"
content_status: draft
tags: []
aliases: []
summary: "{{summary}}"
references:
  - "{{related_entity_id}}"
art: []
notes: "{{editorial_notes}}"
kingdom_id: "{{kingdom_id}}"
biome_key: "{{biome_key}}"
climate_key: "{{climate_key}}"
terrain_keys:
  - "{{terrain_key}}"
initial_state:
  population_estimate: null
  prosperity: null
  security: null
  tension: null
  danger_level: null
  magical_tension: null
magical_traditions:
  - "{{magical_tradition_key}}"
faction_influence:
  - faction_id: "{{faction_id}}"
    influence: null
    visibility: "{{visibility_key}}"
    notes: null
resource_presence:
  - resource_id: "{{resource_id}}"
    abundance: "{{abundance_key}}"
    accessibility: "{{accessibility_key}}"
    seasonality: "{{seasonality_key}}"
    notes: null
borders:
  - boundary_type: "{{boundary_type}}"
    adjacent_region_id: "{{adjacent_region_id}}"
    external_boundary_key: null
    natural_obstacle_key: null
    notes: null
reputation: null
---

> **Aviso de template:** este arquivo não é conteúdo real. Placeholders são proibidos em conteúdo `approved`.

# Visão geral

{{overview}}

## Geografia

{{geography}}

## Clima

{{climate}}

## População

{{population}}

## Economia

{{economy}}

## Tradição mágica

{{magical_traditions_text}}

## Influência política

{{political_influence}}

## Perigos

{{dangers}}

## Reputação

{{reputation_text}}

## História

{{history}}

## Observações editoriais

{{editorial_notes_text}}
