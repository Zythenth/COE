---
schema_version: "1.0.0"
content_status: draft
id: "event.{{event_slug}}"
name: "{{event_name}}"
tags: []
aliases: []
summary: "{{summary}}"
references: []
art: []
notes: "{{editorial_notes}}"
content_event_role_key: "{{content_event_role_key}}"
event_type_key: "{{event_type_key}}"
event_subtype_key: "{{event_subtype_key}}"
temporal_scope:
  occurred_before_campaign: null
  start_date: null
  end_date: null
  precision_key: "{{temporal_precision_key}}"
  calendar_id: null
  notes: null
location_scope:
  location_ids: []
  settlement_ids: []
  region_ids: []
  route_ids: []
  scope_key: "{{location_scope_key}}"
actors:
  - actor_key: "{{actor_key}}"
    entity_id: null
    entity_category_key: "{{actor_entity_category_key}}"
    role_key: "{{actor_role_key}}"
    motivation_keys: []
    notes: null
targets:
  - target_key: "{{target_key}}"
    entity_id: null
    entity_category_key: "{{target_entity_category_key}}"
    role_key: "{{target_role_key}}"
    notes: null
participants:
  - participant_key: "{{participant_key}}"
    entity_id: null
    entity_category_key: "{{participant_entity_category_key}}"
    role_key: "{{participant_role_key}}"
    notes: null
observer_scope:
  historical_observer_ids: []
  possible_observer_category_keys: []
  observation_condition_keys: []
  notes: null
causality:
  causal_classification_key: "{{causal_classification_key}}"
  root_basis:
    root_basis_key: null
    scope_key: null
    justification: null
  cause_event_ids: []
  cause_entity_ids: []
  preconditions:
    - condition_key: "{{precondition_key}}"
      subject_id: null
      observed_property_key: "{{precondition_property_key}}"
      operator_key: "{{precondition_operator_key}}"
      number_value: null
      boolean_value: null
      key_value: null
      entity_id_value: null
      reference_ids: []
      description: "{{precondition_description}}"
  agent_entity_ids: []
  motive_keys: []
  capabilities:
    - capability_key: "{{causal_capability_key}}"
      source_entity_ids: []
      condition_keys: []
      notes: null
  opportunities:
    - opportunity_key: "{{causal_opportunity_key}}"
      source_entity_ids: []
      condition_keys: []
      notes: null
  correlations:
    - correlation_key: "{{correlation_key}}"
      related_entity_ids: []
      related_event_ids: []
      notes: null
parent_event_id: null
related_events:
  - event_id: "event.{{related_event_slug}}"
    relation_key: "{{related_event_relation_key}}"
    notes: null
triggers:
  - trigger_key: "{{trigger_key}}"
    trigger_type_key: "{{trigger_type_key}}"
    scope_key: "{{trigger_scope_key}}"
    condition:
      condition_key: "{{trigger_condition_key}}"
      subject_id: null
      observed_property_key: "{{trigger_property_key}}"
      operator_key: "{{trigger_operator_key}}"
      number_value: null
      boolean_value: null
      key_value: null
      entity_id_value: null
      reference_ids: []
      description: "{{trigger_condition_description}}"
    threshold:
      value: null
      scale_key: null
      unit_key: null
    temporal_window:
      value: null
      unit_key: null
    precondition_keys: []
    observed_entity_ids: []
    repetition_key: "{{trigger_repetition_key}}"
    single_use: null
    cooldown:
      value: null
      unit_key: null
    priority: null
    delay:
      value: null
      unit_key: null
    controlled_chance: null
    random_stream_key: "{{trigger_random_stream_key}}"
    attributed_cause_keys: []
    allowed_result_keys: []
    blocking_condition_keys: []
    expiration:
      date: null
      condition_keys: []
    traceability_keys: []
evidence_profiles:
  - evidence_key: "{{evidence_key}}"
    evidence_type_key: "{{evidence_type_key}}"
    source_entity_ids: []
    location_id: null
    availability:
      starts_at: null
      duration:
        value: null
        unit_key: null
    intensity: null
    detection_condition_keys: []
    identification_requirement_keys: []
    notes: null
effect_profiles:
  - effect_key: "{{effect_key}}"
    effect_type_key: "{{effect_type_key}}"
    target_entity_ids: []
    target_category_keys: []
    magic_effect_id: null
    condition_keys: []
    notes: null
consequence_profiles:
  - consequence_key: "{{consequence_key}}"
    event_id: null
    event_type_key: "{{consequence_event_type_key}}"
    affected_entity_ids: []
    condition_keys: []
    delay:
      value: null
      unit_key: null
    notes: null
visibility:
  classification_key: "{{visibility_classification_key}}"
  public_summary_allowed: null
  restricted_field_keys: []
  disclosure_condition_keys: []
importance:
  profile_key: "{{importance_profile_key}}"
  initial_value: null
  factor_keys: []
sources:
  - source_key: "{{source_key}}"
    source_type_key: "{{source_type_key}}"
    source_entity_id: null
    source_event_id: null
    reference_path: null
    notes: null
restricted_origin:
  origin_type_key: null
  source_entity_id: null
  source_event_id: null
  visibility_key: null
  notes: null
integration_links:
  related_rumor_ids: []
  related_conflict_ids: []
  related_creature_ids: []
  related_threat_source_entity_ids: []
  memory_source_evidence_keys: []
  knowledge_source_evidence_keys: []
  belief_effect_condition_keys: []
fallback_text_template:
  template_key: "{{fallback_template_key}}"
  text: "{{fallback_template_text}}"
  required_parameter_keys: []
optional_narrative:
  text: null
  viewpoint_key: null
  source_event_ids: []
  verified: null
campaign_projection:
  campaign_event_type_key: "{{campaign_event_type_key}}"
  required_traceability_keys: []
  requires_engine_version: null
  notes: null
deferred_decisions:
  - "{{deferred_decision}}"
---

> **Aviso de template:** este arquivo não é conteúdo real. Ele segue o [contrato de eventos, rumores, história e conflitos](../../../../docs/world/schemas/EVENT_RUMOR_HISTORY_AND_CONFLICT_ENTITIES.md). Placeholders são proibidos em conteúdo `approved`. `event.*` define conteúdo estático; um evento concreto de campanha usa identidade técnica separada e permanece imutável no log.

# Visão geral

{{overview}}

## Papel editorial e cronologia

{{editorial_role_and_chronology}}

## Atores, alvos, participantes e observadores

{{actors_targets_participants_and_observers}}

## Causalidade

{{causality_lore}}

## Gatilhos

{{triggers_lore}}

## Evidências

{{evidence_lore}}

## Efeitos e consequências possíveis

{{effects_and_consequences}}

## Visibilidade e importância

{{visibility_and_importance}}

## Fontes e texto fallback

{{sources_and_fallback}}

## Memória, conhecimento, crença, rumores, conflitos e ameaças

{{memory_knowledge_belief_rumor_conflict_and_threat_integrations}}

## Narrativa opcional

{{optional_narrative_text}}

## Observações editoriais

{{editorial_notes_text}}
