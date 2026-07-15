---
schema_version: "1.0.0"
id: "route.{{route_slug}}"
name: "{{route_name}}"
content_status: draft
tags: []
aliases: []
summary: "{{summary}}"
references:
  - "{{related_entity_id}}"
art: []
notes: "{{editorial_notes}}"
origin_id: "{{origin_id}}"
destination_id: "{{destination_id}}"
directionality: "{{directionality}}"
route_type: "{{route_type}}"
distance:
  value: null
  unit_key: null
base_travel_time:
  value: null
  unit_key: null
access_modes:
  - "{{access_mode}}"
initial_state:
  safety: null
  capacity: null
  condition: null
  traffic: null
  magical_instability: null
controller_faction_id: null
toll:
  money:
    amount: null
    currency_key: null
  collector_id: null
  exemptions: []
  notes: null
seasonal_access:
  - season_key: "{{season_key}}"
    access_state: "{{access_state_key}}"
    travel_modifier: null
    risk_modifier: null
    notes: null
risk_profile:
  danger_keys:
    - "{{danger_key}}"
  risk_level: null
  notes: null
---

> **Aviso de template:** este arquivo não é conteúdo real. Placeholders são proibidos em conteúdo `approved`; origem e destino devem ser diferentes e usar IDs `settlement.*` ou `location.*` aprovados. Distância, duração, tráfego e pedágio aqui são propriedades ou condições iniciais, nunca estado atual da campanha.

# Visão geral

{{overview}}

## Origem e destino

{{endpoints}}

## Percurso

{{course}}

## Terreno

{{terrain}}

## Meios de viagem

{{travel_modes}}

## Controle

{{control}}

## Pedágios

{{tolls}}

## Perigos

{{dangers}}

## Variações sazonais

{{seasonal_variations}}

## Importância comercial

{{commercial_importance}}

## Acontecimentos

{{events}}

## História

{{history}}

## Observações editoriais

{{editorial_notes_text}}
