---
schema_version: "1.0.0"
content_status: draft
id: "rumor.{{rumor_slug}}"
name: "{{rumor_name}}"
tags: []
aliases: []
summary: "{{summary}}"
references: []
art: []
notes: "{{editorial_notes}}"
claim:
  subject_id: null
  subject_category_key: "{{claim_subject_category_key}}"
  property_key: "{{claim_property_key}}"
  number_value: null
  boolean_value: null
  key_value: null
  entity_id_value: null
  reference_ids: []
  expressed_certainty_key: "{{claim_expressed_certainty_key}}"
  editorial_summary: "{{claim_editorial_summary}}"
subject_entity_ids: []
version:
  version_key: "{{rumor_version_key}}"
  version_label: "{{rumor_version_label}}"
  initial_version: null
genealogy:
  previous_rumor_ids: []
  derived_rumor_ids: []
  merged_rumor_ids: []
  derivation_key: "{{rumor_derivation_key}}"
  mutation_keys: []
origin:
  origin_event_id: null
  origin_evidence_key: null
  first_emitter_id: null
  first_channel_key: "{{first_channel_key}}"
  location_id: null
  occurred_at: null
  source:
    source_type_key: "{{origin_source_type_key}}"
    source_entity_id: null
    source_event_id: null
    source_description: "{{origin_source_description}}"
restricted_engine_truth:
  truth_key: "{{restricted_truth_key}}"
  subject_id: null
  property_key: "{{restricted_truth_property_key}}"
  number_value: null
  boolean_value: null
  key_value: null
  entity_id_value: null
  reference_ids: []
  source_event_ids: []
  visibility_key: "{{restricted_truth_visibility_key}}"
initial_reach:
  carrier_ids: []
  recipient_ids: []
  group_ids: []
  location_ids: []
  channel_keys: []
  scope_key: "{{initial_reach_scope_key}}"
  notes: null
initial_credibility: null
emotional_charge:
  intensity: null
  emotion_keys: []
novelty: null
intermediate_sources:
  - source_key: "{{intermediate_source_key}}"
    carrier_id: null
    channel_key: "{{intermediate_channel_key}}"
    source_rumor_id: null
    location_id: null
    occurred_at: null
initially_reached_groups: []
initially_reached_locations: []
mutations:
  - mutation_key: "{{mutation_key}}"
    mutation_type_key: "{{mutation_type_key}}"
    source_rumor_id: null
    resulting_claim_summary: "{{mutation_result_summary}}"
    cause_keys: []
    notes: null
validity:
  starts_at: null
  ends_at: null
  expiration_condition_keys: []
initial_state:
  state_key: "{{initial_rumor_state_key}}"
  effective_date: null
  public_credibility: null
  notes: null
contestations:
  - contestation_key: "{{contestation_key}}"
    source_entity_ids: []
    evidence_keys: []
    related_rumor_ids: []
    notes: null
corrections:
  - correction_key: "{{correction_key}}"
    correction_rumor_id: null
    source_entity_ids: []
    evidence_keys: []
    notes: null
transmission_rules:
  opportunity_keys: []
  allowed_channel_keys: []
  relationship_or_access_keys: []
  range_keys: []
  blocking_condition_keys: []
  aggregation_keys: []
distortion_rules:
  allowed_mutation_keys: []
  forbidden_mutation_keys: []
  preservation_keys: []
  random_stream_key: "{{distortion_random_stream_key}}"
potential_consequences:
  - consequence_key: "{{rumor_consequence_key}}"
    affected_entity_ids: []
    affected_category_keys: []
    event_type_key: "{{rumor_consequence_event_type_key}}"
    condition_keys: []
    notes: null
triggers:
  - trigger_key: "{{rumor_trigger_key}}"
    trigger_type_key: "{{rumor_trigger_type_key}}"
    scope_key: "{{rumor_trigger_scope_key}}"
    condition:
      condition_key: "{{rumor_trigger_condition_key}}"
      subject_id: null
      observed_property_key: "{{rumor_trigger_property_key}}"
      operator_key: "{{rumor_trigger_operator_key}}"
      number_value: null
      boolean_value: null
      key_value: null
      entity_id_value: null
      reference_ids: []
      description: "{{rumor_trigger_condition_description}}"
    threshold:
      value: null
      scale_key: null
      unit_key: null
    temporal_window:
      value: null
      unit_key: null
    precondition_keys: []
    observed_entity_ids: []
    repetition_key: "{{rumor_trigger_repetition_key}}"
    single_use: null
    cooldown:
      value: null
      unit_key: null
    priority: null
    delay:
      value: null
      unit_key: null
    controlled_chance: null
    random_stream_key: "{{rumor_trigger_random_stream_key}}"
    attributed_cause_keys: []
    allowed_result_keys: []
    blocking_condition_keys: []
    expiration:
      date: null
      condition_keys: []
    traceability_keys: []
visibility:
  classification_key: "{{rumor_visibility_key}}"
  restricted_field_keys:
    - restricted_engine_truth
  disclosure_condition_keys: []
deferred_decisions:
  - "{{deferred_decision}}"
---

> **Aviso de template:** este arquivo não é conteúdo real. Ele segue o [contrato de eventos, rumores, história e conflitos](../../../../docs/world/schemas/EVENT_RUMOR_HISTORY_AND_CONFLICT_ENTITIES.md). Placeholders são proibidos em conteúdo `approved`. Um rumor é uma afirmação transmissível, não fato, crença, memória ou lenda; sua verdade restrita nunca é conhecimento automático de NPC.

# Visão geral

{{overview}}

## Afirmação e assunto

{{claim_and_subject}}

## Origem e primeira transmissão

{{origin_and_first_transmission}}

## Verdade restrita

{{restricted_truth_editorial_note}}

## Genealogia e versões

{{genealogy_and_versions}}

## Alcance, credibilidade e carga emocional iniciais

{{initial_reach_credibility_and_emotion}}

## Transmissão e distorção

{{transmission_and_distortion}}

## Contestações e correções

{{contestations_and_corrections}}

## Consequências possíveis

{{potential_consequences_text}}

## Visibilidade

{{visibility_lore}}

## Observações editoriais

{{editorial_notes_text}}
