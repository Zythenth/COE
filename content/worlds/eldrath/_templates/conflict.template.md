---
schema_version: "1.0.0"
content_status: draft
id: "conflict.{{conflict_slug}}"
name: "{{conflict_name}}"
tags: []
aliases: []
summary: "{{summary}}"
references: []
art: []
notes: "{{editorial_notes}}"
conflict_type_key: "{{conflict_type_key}}"
subject:
  subject_key: "{{conflict_subject_key}}"
  subject_entity_ids: []
  subject_category_keys: []
  editorial_summary: "{{conflict_subject_summary}}"
origin:
  origin_event_id: null
  origin_condition_keys: []
  source_entity_ids: []
  occurred_at: null
  foundation: "{{conflict_origin_foundation}}"
sides:
  - side_key: "{{side_key}}"
    editorial_name: "{{side_name}}"
    side_type_key: "{{side_type_key}}"
    entity_ids: []
    creature_ids: []
    group_descriptor_keys: []
    participant_role_keys: []
    notes: null
participant_entity_ids: []
interests:
  - interest_key: "{{interest_key}}"
    side_key: "{{interest_side_key}}"
    interest_type_key: "{{interest_type_key}}"
    target_entity_ids: []
    editorial_summary: "{{interest_summary}}"
incompatible_objectives:
  - objective_key: "{{conflict_objective_key}}"
    side_key: "{{objective_side_key}}"
    action_key: "{{objective_action_key}}"
    target_entity_ids: []
    desired_outcome_key: "{{objective_outcome_key}}"
    incompatible_with_objective_keys: []
    editorial_summary: "{{objective_summary}}"
grievances:
  - grievance_key: "{{grievance_key}}"
    side_key: "{{grievance_side_key}}"
    target_side_keys: []
    source_event_ids: []
    source_rumor_ids: []
    evidence_keys: []
    editorial_summary: "{{grievance_summary}}"
risks:
  - risk_key: "{{conflict_risk_key}}"
    affected_entity_ids: []
    affected_category_keys: []
    severity: null
    condition_keys: []
    notes: null
resources:
  - resource_key: "{{conflict_resource_key}}"
    side_key: "{{resource_side_key}}"
    resource_id: null
    item_id: null
    source_entity_ids: []
    availability_key: "{{resource_availability_key}}"
    notes: null
capabilities:
  - capability_key: "{{conflict_capability_key}}"
    side_key: "{{capability_side_key}}"
    capability_type_key: "{{capability_type_key}}"
    source_entity_ids: []
    condition_keys: []
    limitation_keys: []
    notes: null
relations:
  - relation_key: "{{conflict_relation_key}}"
    source_side_key: "{{relation_source_side_key}}"
    target_side_key: "{{relation_target_side_key}}"
    relation_type_key: "{{relation_type_key}}"
    source_entity_ids: []
    notes: null
territory:
  kingdom_ids: []
  region_ids: []
  settlement_ids: []
  location_ids: []
  route_ids: []
  scope_key: "{{territorial_scope_key}}"
visibility:
  classification_key: "{{conflict_visibility_key}}"
  public_summary_allowed: null
  restricted_field_keys: []
  disclosure_condition_keys: []
initial_state:
  effective_date: null
  state_key: "{{initial_conflict_state_key}}"
  tension:
    value: null
    scale_key: "{{tension_scale_key}}"
  mobilization_keys: []
  known_incident_event_ids: []
  known_by_entity_ids: []
  notes: null
thresholds:
  - threshold_key: "{{threshold_key}}"
    threshold_type_key: "{{threshold_type_key}}"
    value: null
    scale_key: null
    condition_keys: []
    allowed_transition_keys: []
escalation_triggers:
  - trigger_key: "{{escalation_trigger_key}}"
    trigger_type_key: "{{escalation_trigger_type_key}}"
    scope_key: "{{escalation_scope_key}}"
    condition:
      condition_key: "{{escalation_condition_key}}"
      subject_id: null
      observed_property_key: "{{escalation_property_key}}"
      operator_key: "{{escalation_operator_key}}"
      number_value: null
      boolean_value: null
      key_value: null
      entity_id_value: null
      reference_ids: []
      description: "{{escalation_condition_description}}"
    threshold:
      threshold_key: null
      value: null
      scale_key: null
      unit_key: null
    temporal_window:
      value: null
      unit_key: null
    precondition_keys: []
    observed_entity_ids: []
    repetition_key: "{{escalation_repetition_key}}"
    single_use: null
    cooldown:
      value: null
      unit_key: null
    priority: null
    delay:
      value: null
      unit_key: null
    controlled_chance: null
    random_stream_key: "{{escalation_random_stream_key}}"
    attributed_cause_keys: []
    allowed_result_keys: []
    blocking_condition_keys: []
    expiration:
      date: null
      condition_keys: []
    traceability_keys: []
reduction_triggers:
  - trigger_key: "{{reduction_trigger_key}}"
    trigger_type_key: "{{reduction_trigger_type_key}}"
    scope_key: "{{reduction_scope_key}}"
    condition:
      condition_key: "{{reduction_condition_key}}"
      subject_id: null
      observed_property_key: "{{reduction_property_key}}"
      operator_key: "{{reduction_operator_key}}"
      number_value: null
      boolean_value: null
      key_value: null
      entity_id_value: null
      reference_ids: []
      description: "{{reduction_condition_description}}"
    threshold:
      threshold_key: null
      value: null
      scale_key: null
      unit_key: null
    temporal_window:
      value: null
      unit_key: null
    precondition_keys: []
    observed_entity_ids: []
    repetition_key: "{{reduction_repetition_key}}"
    single_use: null
    cooldown:
      value: null
      unit_key: null
    priority: null
    delay:
      value: null
      unit_key: null
    controlled_chance: null
    random_stream_key: "{{reduction_random_stream_key}}"
    attributed_cause_keys: []
    allowed_result_keys: []
    blocking_condition_keys: []
    expiration:
      date: null
      condition_keys: []
    traceability_keys: []
possible_incidents:
  - incident_key: "{{incident_key}}"
    event_type_key: "{{incident_event_type_key}}"
    actor_side_keys: []
    target_side_keys: []
    condition_keys: []
    consequence_keys: []
    notes: null
possible_milestones:
  - milestone_key: "{{milestone_key}}"
    milestone_type_key: "{{milestone_type_key}}"
    condition_keys: []
    related_event_type_keys: []
    notes: null
possible_resolutions:
  - resolution_key: "{{resolution_key}}"
    resolution_type_key: "{{resolution_type_key}}"
    eligible_side_keys: []
    condition_keys: []
    required_event_type_keys: []
    consequence_keys: []
    notes: null
closure_conditions:
  - closure_key: "{{closure_key}}"
    condition_keys: []
    required_event_type_keys: []
    resulting_state_key: "{{closure_resulting_state_key}}"
potential_consequences:
  - consequence_key: "{{conflict_consequence_key}}"
    consequence_type_key: "{{conflict_consequence_type_key}}"
    affected_entity_ids: []
    affected_category_keys: []
    event_type_key: "{{conflict_consequence_event_type_key}}"
    condition_keys: []
    notes: null
historical_event_ids: []
related_rumor_ids: []
related_secret_ids: []
related_creature_ids: []
related_threat_source_entity_ids: []
deferred_decisions:
  - "{{deferred_decision}}"
---

> **Aviso de template:** este arquivo não é conteúdo real. Ele segue o [contrato de eventos, rumores, história e conflitos](../../../../docs/world/schemas/EVENT_RUMOR_HISTORY_AND_CONFLICT_ENTITIES.md). Placeholders são proibidos em conteúdo `approved`. O arquivo define tensão e possibilidades iniciais; estado atual, eventos produzidos, resultado efetivo e vencedor pertencem à campanha.

# Visão geral

{{overview}}

## Assunto e origem

{{subject_and_origin}}

## Lados e participantes

{{sides_and_participants}}

## Interesses, objetivos incompatíveis e queixas

{{interests_objectives_and_grievances}}

## Recursos, capacidades e riscos

{{resources_capabilities_and_risks}}

## Relações e território

{{relations_and_territory}}

## Estado inicial e visibilidade

{{initial_state_and_visibility}}

## Escalada e redução

{{escalation_and_reduction}}

## Incidentes e marcos possíveis

{{possible_incidents_and_milestones}}

## Resoluções e encerramento possíveis

{{possible_resolutions_and_closure}}

## Consequências possíveis

{{potential_consequences_text}}

## História, rumores, segredos e ameaças relacionados

{{related_history_rumors_secrets_and_threats}}

## Observações editoriais

{{editorial_notes_text}}
