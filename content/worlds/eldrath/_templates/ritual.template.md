---
schema_version: "1.0.0"
content_status: draft
id: "ritual.{{ritual_slug}}"
name: "{{ritual_name}}"
tags: []
aliases: []
summary: "{{summary}}"
references: []
art: []
notes: "{{editorial_notes}}"
magic_school_ids:
  - "magic_school.{{magic_school_slug}}"
origin:
  description: "{{origin_description}}"
  creator_id: null
  discovery_event_id: null
  date: null
  period_key: null
purpose:
  purpose_key: "{{ritual_purpose_key}}"
  summary: "{{ritual_purpose_summary}}"
difficulty:
  scale_key: "{{difficulty_scale_key}}"
  value: null
  condition_keys: []
preparation:
  duration:
    value: null
    unit_key: null
  action_keys: []
  required_state_keys: []
  verification_keys: []
  notes: null
estimated_duration:
  value: null
  unit_key: null
required_location:
  location_ids: []
  location_type_keys: []
  property_keys: []
  access_condition_keys: []
  notes: null
environmental_conditions:
  - condition_key: "{{environmental_condition_key}}"
    location_type_keys: []
    climate_keys: []
    phenomenon_keys: []
    notes: null
temporal_conditions:
  - condition_key: "{{temporal_condition_key}}"
    calendar_marker_keys: []
    period_keys: []
    timing_keys: []
    notes: null
participants:
  minimum: null
  maximum: null
  condition_keys: []
roles:
  - role_key: "{{ritual_role_key}}"
    editorial_name: "{{ritual_role_name}}"
    purpose: "{{ritual_role_purpose}}"
    minimum_participants: null
    maximum_participants: null
    requirements:
      profession_ids: []
      skill_keys: []
      attribute_keys: []
      affinity_magic_school_ids: []
      spell_ids: []
      condition_keys: []
    notes: null
required_spell_ids: []
required_skill_keys: []
required_tools:
  - item_id: "item.{{required_tool_slug}}"
    quantity:
      value: null
      unit_key: null
    assigned_role_key: null
    condition_keys: []
    notes: null
materials:
  - material_key: "{{material_key}}"
    resource_id: null
    item_id: null
    quantity:
      value: null
      unit_key: null
    consumed: true
    assigned_role_key: null
    stage_step_keys: []
    condition_keys: []
    notes: null
catalysts:
  - catalyst_key: "{{catalyst_key}}"
    resource_id: null
    item_id: null
    quantity:
      value: null
      unit_key: null
    consumed: false
    assigned_role_key: null
    stage_step_keys: []
    condition_keys: []
    notes: null
required_artifact_ids: []
costs:
  - cost_key: "{{cost_key}}"
    category_key: "{{cost_category_key}}"
    bearer_key: "{{cost_bearer_key}}"
    assigned_role_key: null
    timing_key: "{{cost_timing_key}}"
    resource_id: null
    item_id: null
    quantity:
      value: null
      unit_key: null
    condition_key: null
    mechanical_state_key: null
    consumption_mode_key: "{{cost_consumption_mode_key}}"
    deferred_trigger_key: null
    condition_keys: []
    notes: null
steps:
  - step_key: "{{step_key}}"
    order: null
    editorial_name: "{{step_name}}"
    responsible_role_key: "{{responsible_role_key}}"
    required_action: "{{required_action}}"
    duration:
      value: null
      unit_key: null
    requirement_keys: []
    required_material_keys: []
    required_catalyst_keys: []
    required_tool_item_ids: []
    cost_keys: []
    success_condition_keys: []
    failure_condition_keys: []
    partial_effect_applications:
      - application_key: "{{partial_effect_application_key}}"
        magic_effect_id: "magic_effect.{{partial_magic_effect_slug}}"
        target_binding_key: "{{partial_effect_target_binding_key}}"
        parameters: []
        condition_keys: []
        trigger_keys: []
    interruptible: null
    resumable: null
    resumption_rule_keys: []
    notes: null
advance_conditions:
  - advance_key: "{{advance_condition_key}}"
    from_step_key: "{{from_step_key}}"
    to_step_key: "{{to_step_key}}"
    condition_keys: []
    notes: null
interruptions:
  - interruption_key: "{{interruption_key}}"
    trigger_keys: []
    affected_step_keys: []
    effect_applications: []
    evidence_keys: []
    resumable: null
    notes: null
resumption:
  allowed: null
  requirement_keys: []
  preserved_state_keys: []
  reset_state_keys: []
  maximum_pause_duration:
    value: null
    unit_key: null
  notes: null
partial_results:
  - result_key: "{{partial_result_key}}"
    source_step_keys: []
    condition_keys: []
    effect_applications: []
    cost_keys: []
    evidence_keys: []
    notes: null
success_result:
  condition_keys: []
  effect_applications:
    - application_key: "{{success_effect_application_key}}"
      magic_effect_id: "magic_effect.{{success_magic_effect_slug}}"
      target_binding_key: "{{success_effect_target_binding_key}}"
      parameters:
        - parameter_key: "{{success_effect_parameter_key}}"
          number_value: null
          boolean_value: null
          key_value: null
          entity_id: null
          quantity:
            value: null
            unit_key: null
      condition_keys: []
      trigger_keys: []
  evidence_keys: []
  notes: null
targeting:
  allowed_category_keys: []
  minimum_targets: null
  maximum_targets: null
  selection_rule_key: "{{target_selection_rule_key}}"
  condition_keys: []
  area:
    shape_key: null
    origin_key: null
    dimensions: []
    propagation_key: null
    exclusion_keys: []
    condition_keys: []
effect_applications:
  - application_key: "{{ritual_effect_application_key}}"
    magic_effect_id: "magic_effect.{{ritual_magic_effect_slug}}"
    target_binding_key: "{{ritual_effect_target_binding_key}}"
    parameters: []
    condition_keys: []
    trigger_keys: []
risks:
  - risk_key: "{{risk_key}}"
    condition_keys: []
    base_probability: null
    modifiers:
      - modifier_key: "{{risk_modifier_key}}"
        operation: "{{risk_modifier_operation}}"
        value: null
        condition_keys: []
        notes: null
    severity_key: "{{risk_severity_key}}"
    effect_applications: []
    evidence_keys: []
    exposure_keys: []
    corruption:
      magnitude:
        value: null
        unit_key: null
      effect_applications: []
      evidence_keys: []
    alternate_target_rule_key: null
    affected_area:
      shape_key: null
      origin_key: null
      dimensions: []
      propagation_key: null
      exclusion_keys: []
      condition_keys: []
    mitigation_keys: []
    random_stream_key: "{{risk_random_stream_key}}"
    notes: null
failures:
  - failure_key: "{{failure_key}}"
    condition_keys: []
    base_probability: null
    modifiers: []
    severity_key: "{{failure_severity_key}}"
    effect_applications: []
    evidence_keys: []
    exposure_keys: []
    corruption:
      magnitude:
        value: null
        unit_key: null
      effect_applications: []
      evidence_keys: []
    alternate_target_rule_key: null
    affected_area:
      shape_key: null
      origin_key: null
      dimensions: []
      propagation_key: null
      exclusion_keys: []
      condition_keys: []
    mitigation_keys: []
    random_stream_key: "{{failure_random_stream_key}}"
    notes: null
corruption:
  source_keys: []
  possible_magnitude:
    minimum: null
    maximum: null
    unit_key: null
  symptom_keys: []
  conceptual_threshold_keys: []
  effect_applications: []
  resistance_keys: []
  treatment_keys: []
  evidence_keys: []
sensory_signals:
  - signal_key: "{{sensory_signal_key}}"
    modality_key: "{{signal_modality_key}}"
    intensity_key: null
    detection_condition_keys: []
    notes: null
residues:
  - residue_key: "{{residue_key}}"
    magic_effect_id: null
    persistence:
      mode_key: "{{residue_duration_mode_key}}"
      quantity:
        value: null
        unit_key: null
      end_condition_keys: []
      dispel_rule_keys: []
    detection_condition_keys: []
    notes: null
evidence_profiles:
  - evidence_key: "{{evidence_key}}"
    evidence_type_key: "{{evidence_type_key}}"
    persistence_key: null
    detection_condition_keys: []
    identification_requirement_keys: []
    notes: null
countermeasures:
  - countermeasure_key: "{{countermeasure_key}}"
    category_key: "{{countermeasure_category_key}}"
    required_entity_ids: []
    condition_keys: []
    notes: null
learning:
  form_keys: []
  prerequisite_keys: []
  factor_keys: []
  initial_sources:
    - source_key: "{{learning_source_key}}"
      source_type_key: "{{learning_source_type_key}}"
      source_entity_id: null
      access_condition_keys: []
      provenance: "{{learning_source_provenance}}"
regulation:
  category_keys: []
  magic_tag_keys: []
  license_requirement_keys: []
  notes: null
deferred_decisions:
  - "{{deferred_decision}}"
---

> **Aviso de template:** este arquivo não é conteúdo real. Ele segue o [contrato do sistema mágico](../../../../docs/world/schemas/MAGIC_SYSTEM_ENTITIES.md). Placeholders são proibidos em conteúdo `approved`; papéis são chaves internas, etapas não formam uma linguagem executável e rituais em andamento pertencem ao save.

# Visão geral

{{overview}}

## Origem e propósito

{{origin_and_purpose}}

## Preparação, local e momento

{{preparation_location_and_time}}

## Participantes e papéis

{{participants_and_roles}}

## Magias, competências, materiais e artefatos

{{requirements_materials_and_artifacts}}

## Etapas, avanço e interrupções

{{steps_advance_and_interruptions}}

## Retomada, efeitos parciais e conclusão

{{resumption_partial_results_and_completion}}

## Efeitos, custos, riscos e falhas

{{effects_costs_risks_and_failures}}

## Corrupção, sinais e evidências

{{corruption_signals_and_evidence}}

## Contramedidas

{{countermeasures_lore}}

## Aprendizado

{{learning_lore}}

## Regulação contextual

{{regulation_lore}}

## Lore editorial

{{editorial_lore}}

## Observações editoriais

{{editorial_notes_text}}
