---
schema_version: "1.0.0"
content_status: draft
id: "magic_school.{{magic_school_slug}}"
name: "{{magic_school_name}}"
tags: []
aliases: []
summary: "{{summary}}"
references: []
art: []
notes: "{{editorial_notes}}"
parent_school_id: null
origin:
  description: "{{origin_description}}"
  date: null
  period_key: null
  event_id: null
principles:
  - principle_key: "{{principle_key}}"
    editorial_name: "{{principle_name}}"
    summary: "{{principle_summary}}"
domain:
  category_keys: []
  inclusion_keys: []
  exclusion_keys: []
  summary: "{{domain_summary}}"
related_phenomena:
  - phenomenon_key: "{{phenomenon_key}}"
    related_entity_ids: []
    relation_key: "{{phenomenon_relation_key}}"
    notes: null
power_sources:
  - source_key: "{{power_source_key}}"
    category_key: "{{power_source_category_key}}"
    condition_keys: []
    notes: null
methods:
  - method_key: "{{method_key}}"
    editorial_name: "{{method_name}}"
    purpose_key: "{{method_purpose_key}}"
    condition_keys: []
    notes: null
affinities:
  - affinity_key: "{{affinity_key}}"
    relation_key: "{{affinity_relation_key}}"
    condition_keys: []
    notes: null
related_aptitude_keys: []
typical_cost_profiles:
  - profile_key: "{{typical_cost_profile_key}}"
    category_keys: []
    bearer_keys: []
    condition_keys: []
    notes: null
typical_risk_profiles:
  - profile_key: "{{typical_risk_profile_key}}"
    risk_category_keys: []
    severity_keys: []
    condition_keys: []
    notes: null
corruption_relation:
  source_keys: []
  resistance_keys: []
  symptom_keys: []
  evidence_keys: []
  notes: null
common_signals:
  - signal_key: "{{common_signal_key}}"
    modality_key: "{{signal_modality_key}}"
    intensity_key: null
    detection_condition_keys: []
    notes: null
common_evidence:
  - evidence_key: "{{common_evidence_key}}"
    evidence_type_key: "{{evidence_type_key}}"
    persistence_key: null
    detection_condition_keys: []
    notes: null
school_relations:
  - relation_key: "{{school_relation_key}}"
    target_magic_school_id: "magic_school.{{target_magic_school_slug}}"
    relation_type_key: "{{school_relation_type_key}}"
    relevance: null
    foundation: "{{school_relation_foundation}}"
    condition_keys: []
    expected_symmetry: null
    notes: null
regulation:
  category_keys: []
  magic_tag_keys: []
  license_requirement_keys: []
  notes: null
editorial_history:
  - revision_key: "{{taxonomy_revision_key}}"
    date: null
    decision: "{{taxonomy_revision_decision}}"
    affected_magic_school_ids: []
    notes: null
deferred_decisions:
  - "{{deferred_decision}}"
---

> **Aviso de template:** este arquivo não é conteúdo real. Ele segue o [contrato do sistema mágico](../../../../docs/world/schemas/MAGIC_SYSTEM_ENTITIES.md). Placeholders são proibidos em conteúdo `approved`; escola não é facção e não possui membros, líder, professores, cargos, sede ou tesouro.

# Visão geral

{{overview}}

## Origem

{{origin_lore}}

## Princípios e domínio

{{principles_and_domain}}

## Fenômenos e fontes de poder

{{phenomena_and_power_sources}}

## Métodos, afinidades e aptidões

{{methods_affinities_and_aptitudes}}

## Custos, riscos e corrupção típicos

{{typical_costs_risks_and_corruption}}

## Sinais e evidências

{{signals_and_evidence}}

## Relações com outras escolas

{{school_relations_lore}}

## Regulação contextual

{{regulation_lore}}

## História editorial da taxonomia

{{editorial_taxonomy_history}}

## Observações editoriais

{{editorial_notes_text}}
