---
schema_version: "1.0.0"
content_status: draft
id: "spell.{{spell_slug}}"
name: "{{spell_name}}"
tags: []
aliases: []
summary: "{{summary}}"
references: []
art: []
notes: "{{editorial_notes}}"
primary_school_id: "magic_school.{{primary_magic_school_slug}}"
secondary_school_ids: []
subschool_ids: []
parent_spell_id: null
origin:
  description: "{{origin_description}}"
  creator_id: null
  discovery_event_id: null
  date: null
  period_key: null
rarity_key: "{{rarity_key}}"
difficulty:
  scale_key: "{{difficulty_scale_key}}"
  value: null
  condition_keys: []
requirements:
  prerequisite_spell_ids: []
  required_skill_keys: []
  required_attribute_keys: []
  required_affinities:
    - magic_school_id: "magic_school.{{required_affinity_school_slug}}"
      minimum: null
      condition_keys: []
  required_condition_keys: []
  forbidden_condition_keys: []
  required_entity_ids: []
  notes: null
accepted_parameters:
  - parameter_key: "{{spell_parameter_key}}"
    value_type_key: "{{spell_parameter_type_key}}"
    required: null
    unit_key: null
    minimum: null
    maximum: null
    allowed_key_values: []
    allowed_entity_category_keys: []
    notes: null
costs:
  - cost_key: "{{cost_key}}"
    category_key: "{{cost_category_key}}"
    bearer_key: "{{cost_bearer_key}}"
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
materials:
  - material_key: "{{material_key}}"
    resource_id: null
    item_id: null
    quantity:
      value: null
      unit_key: null
    consumed: true
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
    condition_keys: []
    notes: null
required_tools:
  - item_id: "item.{{required_tool_slug}}"
    quantity:
      value: null
      unit_key: null
    condition_keys: []
    notes: null
environmental_conditions:
  - condition_key: "{{environmental_condition_key}}"
    location_type_keys: []
    climate_keys: []
    temporal_keys: []
    phenomenon_keys: []
    notes: null
cast_time:
  value: null
  unit_key: null
range:
  mode_key: "{{range_mode_key}}"
  distance:
    value: null
    unit_key: null
  connection_key: null
  global_permission_key: null
  condition_keys: []
targeting:
  allowed_category_keys: []
  minimum_targets: null
  maximum_targets: null
  selection_rule_key: "{{target_selection_rule_key}}"
  condition_keys: []
  area:
    shape_key: null
    origin_key: null
    dimensions:
      - dimension_key: "{{area_dimension_key}}"
        quantity:
          value: null
          unit_key: null
    propagation_key: null
    exclusion_keys: []
    condition_keys: []
duration:
  mode_key: "{{duration_mode_key}}"
  quantity:
    value: null
    unit_key: null
  end_condition_keys: []
  dispel_rule_keys: []
concentration:
  required: null
  maximum_simultaneous_links: null
  maintenance_condition_keys: []
  break_condition_keys: []
  break_effect_applications: []
effect_applications:
  - application_key: "{{effect_application_key}}"
    magic_effect_id: "magic_effect.{{magic_effect_slug}}"
    target_binding_key: "{{effect_target_binding_key}}"
    parameters:
      - parameter_key: "{{effect_parameter_key}}"
        number_value: null
        boolean_value: null
        key_value: null
        entity_id: null
        quantity:
          value: null
          unit_key: null
    condition_keys: []
    trigger_keys: []
intensity:
  scale_key: "{{spell_intensity_scale_key}}"
  base_value: null
  minimum: null
  maximum: null
  unit_key: null
  modifier_keys: []
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
    range:
      mode_key: "{{signal_range_mode_key}}"
      distance:
        value: null
        unit_key: null
      connection_key: null
      global_permission_key: null
      condition_keys: []
    duration:
      mode_key: "{{signal_duration_mode_key}}"
      quantity:
        value: null
        unit_key: null
      end_condition_keys: []
      dispel_rule_keys: []
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
  mastery_progression:
    stage_keys:
      - unknown
      - theoretical
      - studying
      - unstable
      - usable
      - mastered
      - magisterial
      - personal_variant
    progression_factor_keys: []
    instability_effect_applications: []
ancestral_magic:
  is_ancestral: null
  tradition_keys: []
  origin_entity_ids: []
  notes: null
regulation:
  category_keys: []
  magic_tag_keys: []
  license_requirement_keys: []
  notes: null
deferred_decisions:
  - "{{deferred_decision}}"
---

> **Aviso de template:** este arquivo não é conteúdo real. Ele segue o [contrato do sistema mágico](../../../../docs/world/schemas/MAGIC_SYSTEM_ENTITIES.md). Placeholders são proibidos em conteúdo `approved`; conhecedores, professores, domínio, conjurações e efeitos atuais pertencem aos futuros NPCs e ao save.

# Visão geral

{{overview}}

## Origem e descoberta

{{origin_and_discovery}}

## Escolas e princípios

{{schools_and_principles}}

## Técnica, requisitos e parâmetros

{{technique_requirements_and_parameters}}

## Custos, materiais e condições

{{costs_materials_and_conditions}}

## Conjuração, alcance, alvos e duração

{{casting_range_targets_and_duration}}

## Efeitos e intensidade

{{effects_and_intensity}}

## Riscos, falhas e corrupção

{{risks_failures_and_corruption}}

## Sinais, resíduos e evidências

{{signals_residues_and_evidence}}

## Contramedidas

{{countermeasures_lore}}

## Aprendizado e domínio possível

{{learning_and_mastery}}

## Variantes e magia ancestral

{{variants_and_ancestral_magic}}

## Regulação contextual

{{regulation_lore}}

## Lore editorial

{{editorial_lore}}

## Observações editoriais

{{editorial_notes_text}}
