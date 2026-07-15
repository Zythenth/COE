---
schema_version: "1.0.0"
id: "location.{{location_slug}}"
name: "{{location_name}}"
content_status: draft
tags: []
aliases: []
summary: "{{summary}}"
references:
  - "{{related_entity_id}}"
art: []
notes: "{{editorial_notes}}"
region_id: "{{region_id}}"
settlement_id: null
parent_location_id: null
location_type: "{{location_type}}"
access:
  access_level: "{{access_level}}"
  requirements: []
  authority_ids: []
  schedule: null
  notes: null
capacity: null
resource_presence:
  - resource_id: "{{resource_id}}"
    abundance: "{{abundance_key}}"
    accessibility: "{{accessibility_key}}"
    seasonality: "{{seasonality_key}}"
    notes: null
danger_keys:
  - "{{danger_key}}"
secret_ids: []
event_ids: []
magical_properties:
  - property_key: "{{magical_property_key}}"
    intensity: null
    notes: null
initial_visibility:
  discovery_state_key: "{{discovery_state_key}}"
  interface_visibility_key: "{{interface_visibility_key}}"
  notes: null
---

> **Aviso de template:** este arquivo não é conteúdo real. Placeholders são proibidos em conteúdo `approved`. `content_status`, acesso físico, descoberta, segredo e visibilidade de interface são dimensões diferentes.

# Visão geral

{{overview}}

## Função

{{function}}

## Localização

{{location_context}}

## Acesso

{{access_text}}

## Controle institucional derivado

{{derived_institutional_control}}

## Características

{{characteristics}}

## Recursos

{{resources}}

## Perigos

{{dangers}}

## Propriedades mágicas

{{magical_properties_text}}

## Segredos

{{secrets}}

## Acontecimentos relacionados

{{related_events}}

## História

{{history}}

## Observações editoriais

{{editorial_notes_text}}
