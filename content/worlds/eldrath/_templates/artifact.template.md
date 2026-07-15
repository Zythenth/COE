---
schema_version: "1.0.0"
content_status: draft
id: "artifact.{{artifact_slug}}"
name: "{{artifact_name}}"
tags: []
aliases: []
summary: "{{summary}}"
references: []
art: []
notes: "{{editorial_notes}}"
material_form:
  form_key: "{{material_form_key}}"
  description: "{{material_form_description}}"
  resource_composition:
    - resource_id: "resource.{{resource_slug}}"
      quantity:
        value: null
        unit_key: null
      notes: null
base_item_id: null
origin:
  description: "{{origin_description}}"
  creator_id: null
  creation_event_id: null
  date: null
  period_key: null
magic_school_ids:
  - "magic_school.{{magic_school_slug}}"
powers:
  - power_key: "{{power_key}}"
    editorial_name: "{{power_name}}"
    passive: null
    effect_applications:
      - application_key: "{{power_effect_application_key}}"
        magic_effect_id: "magic_effect.{{power_magic_effect_slug}}"
        target_binding_key: "{{power_effect_target_binding_key}}"
        parameters:
          - parameter_key: "{{power_effect_parameter_key}}"
            number_value: null
            boolean_value: null
            key_value: null
            entity_id: null
            quantity:
              value: null
              unit_key: null
        condition_keys: []
        trigger_keys: []
    notes: null
activations:
  - activation_key: "{{activation_key}}"
    editorial_name: "{{activation_name}}"
    trigger_keys: []
    requirement_keys: []
    range:
      mode_key: "{{activation_range_mode_key}}"
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
      selection_rule_key: "{{activation_target_selection_rule_key}}"
      condition_keys: []
      area:
        shape_key: null
        origin_key: null
        dimensions: []
        propagation_key: null
        exclusion_keys: []
        condition_keys: []
    duration:
      mode_key: "{{activation_duration_mode_key}}"
      quantity:
        value: null
        unit_key: null
      end_condition_keys: []
      dispel_rule_keys: []
    costs:
      - cost_key: "{{activation_cost_key}}"
        category_key: "{{activation_cost_category_key}}"
        bearer_key: "{{activation_cost_bearer_key}}"
        timing_key: "{{activation_cost_timing_key}}"
        resource_id: null
        item_id: null
        quantity:
          value: null
          unit_key: null
        condition_key: null
        mechanical_state_key: null
        consumption_mode_key: "{{activation_cost_consumption_mode_key}}"
        deferred_trigger_key: null
        condition_keys: []
        notes: null
    effect_applications:
      - application_key: "{{activation_effect_application_key}}"
        magic_effect_id: "magic_effect.{{activation_magic_effect_slug}}"
        target_binding_key: "{{activation_effect_target_binding_key}}"
        parameters: []
        condition_keys: []
        trigger_keys: []
    risk_keys: []
    charge_cost: null
    notes: null
charge_model:
  enabled: null
  minimum: null
  maximum: null
  unit_key: null
  overcharge_allowed: null
  notes: null
charge_regeneration:
  mode_key: "{{charge_regeneration_mode_key}}"
  rate:
    quantity:
      value: null
      unit_key: null
    period_key: null
  trigger_keys: []
  environmental_condition_keys: []
  maximum_regenerated: null
  notes: null
conditions:
  - condition_key: "{{artifact_condition_key}}"
    category_key: "{{artifact_condition_category_key}}"
    effect_applications: []
    activation_keys: []
    notes: null
requirements:
  wielder_condition_keys: []
  required_skill_keys: []
  required_affinity_magic_school_ids: []
  required_spell_ids: []
  required_profession_ids: []
  required_entity_ids: []
  notes: null
bond:
  supported: null
  bond_type_keys: []
  formation_condition_keys: []
  break_condition_keys: []
  effect_applications: []
  notes: null
consciousness:
  present: null
  consciousness_type_key: null
  capability_keys: []
  communication_keys: []
  autonomy_keys: []
  limitation_keys: []
  notes: null
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
destruction:
  possible: null
  condition_keys: []
  required_entity_ids: []
  effect_applications: []
  evidence_keys: []
  notes: null
repair:
  possible: null
  required_profession_ids: []
  required_resource_ids: []
  required_item_ids: []
  required_magic_school_ids: []
  required_spell_ids: []
  condition_keys: []
  effect_applications: []
  notes: null
learning:
  discoverable_power_keys: []
  form_keys: []
  initial_sources:
    - source_key: "{{learning_source_key}}"
      source_type_key: "{{learning_source_type_key}}"
      source_entity_id: null
      access_condition_keys: []
      provenance: "{{learning_source_provenance}}"
content_secret_ids: []
regulation:
  category_keys: []
  magic_tag_keys: []
  license_requirement_keys: []
  notes: null
initial_state:
  effective_date: null
  location_id: null
  bearer_id: null
  recognized_owner_id: null
  condition_key: null
  charges: null
  bond_state_key: null
  public_knowledge_key: null
  discovered_secret_ids: []
  notes: null
deferred_decisions:
  - "{{deferred_decision}}"
---

> **Aviso de template:** este arquivo não é conteúdo real. Ele segue o [contrato do sistema mágico](../../../../docs/world/schemas/MAGIC_SYSTEM_ENTITIES.md). Placeholders são proibidos em conteúdo `approved`; o artefato tem uma identidade persistente própria e não recebe uma `item_instance` concorrente.

# Visão geral

{{overview}}

## Forma material e item-base

{{material_form_and_base_item}}

## Origem, criação e escolas

{{origin_creation_and_schools}}

## Poderes e ativações

{{powers_and_activations}}

## Custos, cargas e regeneração

{{costs_charges_and_regeneration}}

## Condições, requisitos e vínculo

{{conditions_requirements_and_bond}}

## Consciência

{{consciousness_lore}}

## Riscos, falhas e corrupção

{{risks_failures_and_corruption}}

## Sinais, resíduos e evidências

{{signals_residues_and_evidence}}

## Contramedidas, destruição e reparo

{{countermeasures_destruction_and_repair}}

## Aprendizado e segredos

{{learning_and_secrets}}

## Estado inicial

{{initial_state_lore}}

## Regulação contextual

{{regulation_lore}}

## Lore editorial

{{editorial_lore}}

## Observações editoriais

{{editorial_notes_text}}
