---
schema_version: "1.0.0"
content_status: draft
id: "magic_effect.{{magic_effect_slug}}"
name: "{{magic_effect_name}}"
tags: []
aliases: []
summary: "{{summary}}"
references: []
art: []
notes: "{{editorial_notes}}"
effect_category_key: "{{effect_category_key}}"
valid_target_category_keys: []
accepted_parameters:
  - parameter_key: "{{parameter_key}}"
    value_type_key: "{{parameter_value_type_key}}"
    required: null
    unit_key: null
    minimum: null
    maximum: null
    allowed_key_values: []
    allowed_entity_category_keys: []
    notes: null
unit_key: null
allowed_duration_mode_keys: []
intensity_rule:
  scale_key: "{{intensity_scale_key}}"
  minimum: null
  maximum: null
  unit_key: null
  condition_keys: []
  notes: null
stacking:
  mode_key: "{{stacking_mode_key}}"
  maximum_stacks: null
  renewal_key: "{{renewal_rule_key}}"
  exclusive_group_key: null
  condition_keys: []
  notes: null
application_conditions:
  - condition_key: "{{application_condition_key}}"
    subject_key: "{{application_condition_subject_key}}"
    requirement_keys: []
    notes: null
termination_conditions:
  - condition_key: "{{termination_condition_key}}"
    trigger_keys: []
    notes: null
triggers:
  - trigger_key: "{{effect_trigger_key}}"
    event_category_keys: []
    condition_keys: []
    notes: null
modifiers:
  - modifier_key: "{{modifier_key}}"
    operation: "{{modifier_operation}}"
    value: null
    condition_keys: []
    notes: null
resistance:
  resistance_category_keys: []
  source_keys: []
  success_result_key: "{{resistance_success_result_key}}"
  partial_result_key: "{{resistance_partial_result_key}}"
  condition_keys: []
  notes: null
immunity:
  immunity_category_keys: []
  condition_keys: []
  notes: null
dissipation:
  method_keys: []
  required_magic_school_ids: []
  required_spell_ids: []
  condition_keys: []
  notes: null
countermeasures:
  - countermeasure_key: "{{countermeasure_key}}"
    category_key: "{{countermeasure_category_key}}"
    required_entity_ids: []
    condition_keys: []
    notes: null
observability:
  visibility_key: "{{effect_visibility_key}}"
  identification_requirement_keys: []
  hidden_without_requirement: null
  notes: null
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
evidence_profiles:
  - evidence_key: "{{evidence_key}}"
    evidence_type_key: "{{evidence_type_key}}"
    persistence:
      mode_key: "{{evidence_duration_mode_key}}"
      quantity:
        value: null
        unit_key: null
      end_condition_keys: []
      dispel_rule_keys: []
    detection_condition_keys: []
    identification_requirement_keys: []
    notes: null
consequences:
  - application_key: "{{consequence_application_key}}"
    magic_effect_id: "magic_effect.{{consequence_magic_effect_slug}}"
    target_binding_key: "{{consequence_target_binding_key}}"
    parameters: []
    condition_keys: []
    trigger_keys: []
regulation:
  category_keys: []
  magic_tag_keys: []
  license_requirement_keys: []
  notes: null
deferred_decisions:
  - "{{deferred_decision}}"
---

> **Aviso de template:** este arquivo não é conteúdo real. Ele segue o [contrato do sistema mágico](../../../../docs/world/schemas/MAGIC_SYSTEM_ENTITIES.md). Placeholders são proibidos em conteúdo `approved`; esta entidade define comportamento reutilizável e nunca registra uma aplicação atual.

# Visão geral

{{overview}}

## Categoria e alvos

{{category_and_targets}}

## Parâmetros, unidade e intensidade

{{parameters_unit_and_intensity}}

## Duração, empilhamento e renovação

{{duration_stacking_and_renewal}}

## Aplicação, término e gatilhos

{{application_termination_and_triggers}}

## Resistência, imunidade e dissipação

{{resistance_immunity_and_dissipation}}

## Observabilidade, sinais e evidências

{{observability_signals_and_evidence}}

## Consequências e contramedidas

{{consequences_and_countermeasures}}

## Regulação contextual

{{regulation_lore}}

## Lore editorial

{{editorial_lore}}

## Observações editoriais

{{editorial_notes_text}}
