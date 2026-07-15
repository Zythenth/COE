---
schema_version: "1.0.0"
content_status: draft
id: "disease.{{disease_slug}}"
name: "{{disease_name}}"
tags: []
aliases: []
summary: "{{summary}}"
references: []
art: []
notes: "{{editorial_notes}}"
classification:
  disease_category_key: "{{disease_category_key}}"
  nature_key: "{{disease_nature_key}}"
  origin_classification_key: "{{origin_classification_key}}"
  classification_keys: []
origin:
  description: "{{origin_description}}"
  source_entity_ids: []
  region_ids: []
  location_ids: []
  event_id: null
  phenomenon_keys: []
host_profiles:
  - host_profile_key: "{{host_profile_key}}"
    host_category_keys: []
    creature_ids: []
    life_stage_keys: []
    condition_keys: []
    susceptibility:
      value: null
      scale_key: health_0_100
    resistance_keys: []
    structural_immunity_keys: []
    possible_outcome_keys: []
    notes: null
vector_profiles:
  - vector_profile_key: "{{vector_profile_key}}"
    creature_ids: []
    resource_ids: []
    item_ids: []
    location_type_keys: []
    role_key: "{{vector_role_key}}"
    stage_keys: []
    condition_keys: []
    capacity:
      value: null
      scale_key: health_0_100
    evidence_keys: []
    notes: null
reservoir_profiles:
  - reservoir_profile_key: "{{reservoir_profile_key}}"
    creature_ids: []
    resource_ids: []
    item_ids: []
    location_type_keys: []
    role_key: "{{reservoir_role_key}}"
    stage_keys: []
    condition_keys: []
    persistence:
      value: null
      unit_key: null
    evidence_keys: []
    notes: null
exposure_profiles:
  - exposure_profile_key: "{{exposure_profile_key}}"
    exposure_route_key: "{{exposure_route_key}}"
    source_category_keys: []
    source_entity_ids: []
    target_category_keys: []
    dose:
      value: null
      unit_key: null
    intensity:
      value: null
      scale_key: health_0_100
    duration:
      value: null
      unit_key: null
    proximity:
      value: null
      unit_key: null
    protection_keys: []
    resistance_keys: []
    immunity_keys: []
    environmental_condition_keys: []
    evidence_keys: []
    notes: null
transmission_modes:
  - transmission_key: "{{transmission_key}}"
    mode_key: "{{transmission_mode_key}}"
    source_category_keys: []
    target_category_keys: []
    exposure_profile_keys: []
    transmitting_stage_keys: []
    environmental_condition_keys: []
    protection_keys: []
    resistance_keys: []
    immunity_keys: []
    base_probability: null
    modifiers:
      - modifier_key: "{{transmission_modifier_key}}"
        operation: "{{transmission_modifier_operation}}"
        value: null
        condition_keys: []
        notes: null
    random_stream_key: "{{transmission_random_stream_key}}"
    notes: null
incubation:
  minimum:
    value: null
    unit_key: null
  maximum:
    value: null
    unit_key: null
  modifier_keys: []
  notes: null
transmission_windows:
  - window_key: "{{transmission_window_key}}"
    stage_keys: []
    starts_after:
      value: null
      unit_key: null
    duration:
      value: null
      unit_key: null
    condition_keys: []
    notes: null
stages:
  - stage_key: "{{stage_key}}"
    order: null
    editorial_name: "{{stage_name}}"
    duration:
      minimum:
        value: null
        unit_key: null
      maximum:
        value: null
        unit_key: null
    transmissibility:
      value: null
      scale_key: health_0_100
    transmission_profile_keys: []
    symptom_keys: []
    severity:
      value: null
      scale_key: health_0_100
    effect_applications:
      - application_key: "{{stage_effect_application_key}}"
        magic_effect_id: "magic_effect.{{stage_magic_effect_slug}}"
        target_binding_key: "{{stage_target_binding_key}}"
        parameters: []
        condition_keys: []
        trigger_keys: []
    sign_keys: []
    risk_keys: []
    evidence_keys: []
    transitions:
      - transition_key: "{{stage_transition_key}}"
        target_stage_key: "{{target_stage_key}}"
        condition_keys: []
        base_probability: null
        random_stream_key: "{{stage_transition_random_stream_key}}"
        notes: null
    recovery_condition_keys: []
    aggravation_condition_keys: []
    death_condition_keys: []
    notes: null
symptom_definitions:
  - symptom_key: "{{symptom_key}}"
    editorial_name: "{{symptom_name}}"
    intensity:
      minimum: null
      maximum: null
      scale_key: health_0_100
    observability_key: "{{symptom_observability_key}}"
    subjective: null
    duration:
      minimum:
        value: null
        unit_key: null
      maximum:
        value: null
        unit_key: null
    functional_effect_applications:
      - application_key: "{{symptom_effect_application_key}}"
        magic_effect_id: "magic_effect.{{symptom_magic_effect_slug}}"
        target_binding_key: "{{symptom_target_binding_key}}"
        parameters: []
        condition_keys: []
        trigger_keys: []
    sign_keys: []
    evidence_keys: []
    possible_stage_keys: []
    possible_cause_keys: []
    limitation_keys: []
    notes: null
severity_profile:
  minimum: null
  maximum: null
  scale_key: health_0_100
  modifier_keys: []
  notes: null
typical_duration:
  minimum:
    value: null
    unit_key: null
  maximum:
    value: null
    unit_key: null
  modifier_keys: []
  notes: null
progression_profiles:
  - progression_key: "{{progression_key}}"
    direction_key: "{{progression_direction_key}}"
    source_stage_keys: []
    target_stage_keys: []
    interval:
      value: null
      unit_key: null
    factor_keys: []
    base_probability: null
    random_stream_key: "{{progression_random_stream_key}}"
    notes: null
relapse_profiles:
  - relapse_key: "{{relapse_key}}"
    source_outcome_keys: []
    target_stage_keys: []
    condition_keys: []
    base_probability: null
    random_stream_key: "{{relapse_random_stream_key}}"
    notes: null
recurrence_profiles:
  - recurrence_key: "{{recurrence_key}}"
    condition_keys: []
    minimum_interval:
      value: null
      unit_key: null
    base_probability: null
    random_stream_key: "{{recurrence_random_stream_key}}"
    notes: null
sequela_profiles:
  - sequela_key: "{{sequela_key}}"
    condition_category_key: "{{sequela_condition_category_key}}"
    severity:
      value: null
      scale_key: health_0_100
    duration:
      value: null
      unit_key: null
    limitation_keys: []
    effect_applications: []
    evidence_keys: []
    condition_keys: []
    notes: null
immunity_profiles:
  - immunity_key: "{{immunity_key}}"
    source_keys: []
    scope_keys: []
    host_profile_keys: []
    stage_keys: []
    duration:
      value: null
      unit_key: null
    loss_condition_keys: []
    transfer_condition_keys: []
    effect_applications: []
    notes: null
resistance_profiles:
  - resistance_key: "{{resistance_key}}"
    source_keys: []
    host_profile_keys: []
    stage_keys: []
    condition_keys: []
    result_keys: []
    notes: null
vulnerability_profiles:
  - vulnerability_key: "{{vulnerability_key}}"
    source_keys: []
    host_profile_keys: []
    stage_keys: []
    condition_keys: []
    result_keys: []
    notes: null
environmental_factors:
  - factor_key: "{{environmental_factor_key}}"
    climate_keys: []
    biome_keys: []
    region_ids: []
    settlement_ids: []
    location_ids: []
    resource_ids: []
    magic_effect_ids: []
    condition_keys: []
    affected_process_keys: []
    modifier_keys: []
    notes: null
social_factors:
  - factor_key: "{{social_factor_key}}"
    factor_type_key: "{{social_factor_type_key}}"
    settlement_ids: []
    culture_ids: []
    profession_ids: []
    faction_ids: []
    condition_keys: []
    affected_process_keys: []
    modifier_keys: []
    notes: null
evidence_profiles:
  - evidence_key: "{{disease_evidence_key}}"
    evidence_type_key: "{{disease_evidence_type_key}}"
    source_stage_keys: []
    source_symptom_keys: []
    observability_key: "{{disease_evidence_observability_key}}"
    persistence:
      value: null
      unit_key: null
    detection_condition_keys: []
    identification_requirement_keys: []
    notes: null
test_profiles:
  - test_key: "{{test_key}}"
    editorial_name: "{{test_name}}"
    required_profession_ids: []
    required_skill_keys: []
    required_resource_ids: []
    required_item_ids: []
    required_spell_ids: []
    required_ritual_ids: []
    required_artifact_ids: []
    required_location_ids: []
    duration:
      value: null
      unit_key: null
    detectable_stage_keys: []
    evidence_keys: []
    result_keys: []
    error_profile_keys: []
    risk_keys: []
    notes: null
diagnostic_profiles:
  - diagnostic_profile_key: "{{diagnostic_profile_key}}"
    required_profession_ids: []
    required_skill_keys: []
    observation_keys: []
    examination_keys: []
    symptom_keys: []
    evidence_keys: []
    test_keys: []
    required_entity_ids: []
    differential_disease_ids: []
    differential_condition_category_keys: []
    duration:
      value: null
      unit_key: null
    risk_keys: []
    possible_result_keys: []
    limitation_keys: []
    notes: null
prognosis_profiles:
  - prognosis_key: "{{prognosis_key}}"
    stage_keys: []
    severity_range:
      minimum: null
      maximum: null
      scale_key: health_0_100
    health_factor_keys: []
    treatment_option_keys: []
    resistance_keys: []
    outcome_keys: []
    duration:
      value: null
      unit_key: null
    notes: null
prevention_options:
  - prevention_key: "{{prevention_key}}"
    method_key: "{{prevention_method_key}}"
    required_entity_ids: []
    requirement_keys: []
    duration:
      value: null
      unit_key: null
    effect_applications: []
    risk_keys: []
    limitation_keys: []
    notes: null
isolation_options:
  - isolation_key: "{{isolation_key}}"
    method_key: "{{isolation_method_key}}"
    required_location_ids: []
    required_faction_ids: []
    related_law_ids: []
    requirement_keys: []
    duration:
      value: null
      unit_key: null
    capacity_requirement_keys: []
    effect_applications: []
    risk_keys: []
    limitation_keys: []
    notes: null
treatment_options:
  - treatment_key: "{{treatment_key}}"
    treatment_category_key: "{{treatment_category_key}}"
    applicable_stage_keys: []
    applicable_severity_range:
      minimum: null
      maximum: null
      scale_key: health_0_100
    required_profession_ids: []
    required_skill_keys: []
    required_resource_ids: []
    required_item_ids: []
    required_spell_ids: []
    required_ritual_ids: []
    required_artifact_ids: []
    required_location_ids: []
    required_faction_ids: []
    materials:
      - material_key: "{{treatment_material_key}}"
        resource_id: null
        item_id: null
        quantity:
          value: null
          unit_key: null
        consumed: null
        condition_keys: []
        notes: null
    costs:
      - cost_key: "{{treatment_cost_key}}"
        money:
          amount: null
          currency_key: null
        resource_id: null
        item_id: null
        quantity:
          value: null
          unit_key: null
        condition_keys: []
        notes: null
    procedure_keys: []
    rest_requirement_keys: []
    isolation_option_keys: []
    duration:
      value: null
      unit_key: null
    requirement_keys: []
    contraindication_keys: []
    expected_effect_applications:
      - application_key: "{{treatment_effect_application_key}}"
        magic_effect_id: "magic_effect.{{treatment_magic_effect_slug}}"
        target_binding_key: "{{treatment_target_binding_key}}"
        parameters: []
        condition_keys: []
        trigger_keys: []
    side_effect_applications: []
    risk_keys: []
    base_success_probability: null
    random_stream_key: "{{treatment_random_stream_key}}"
    access_factor_keys: []
    related_law_ids: []
    notes: null
mortality_profile:
  applicable_stage_keys: []
  severity_range:
    minimum: null
    maximum: null
    scale_key: health_0_100
  health_factor_keys: []
  treatment_factor_keys: []
  resistance_keys: []
  condition_keys: []
  base_probability: null
  modifier_keys: []
  mitigation_keys: []
  random_stream_key: "{{mortality_random_stream_key}}"
  notes: null
outcome_profiles:
  - outcome_key: "{{outcome_key}}"
    outcome_type_key: "{{outcome_type_key}}"
    source_stage_keys: []
    condition_keys: []
    effect_applications: []
    sequela_keys: []
    immunity_keys: []
    required_event_type_keys: []
    notes: null
fertility_impact:
  applicable: null
  abstract_effect_keys: []
  condition_keys: []
  effect_applications: []
  notes: null
deferred_decisions:
  - "{{deferred_decision}}"
---

> **Aviso de template:** este arquivo não é conteúdo real. Ele segue o [contrato de criaturas, saúde e doenças](../../../../docs/world/schemas/CREATURE_HEALTH_AND_DISEASE_ENTITIES.md). Placeholders são proibidos em conteúdo `approved`; a definição nunca registra uma instância, infecção, sintoma ativo, diagnóstico, tratamento aplicado, imunidade individual ou estado atual. Instâncias iniciais e atuais pertencem ao futuro estado da campanha, não a este arquivo.

# Visão geral

{{overview}}

## Classificação, natureza e origem

{{classification_nature_and_origin}}

## Hospedeiros, vetores e reservatórios

{{hosts_vectors_and_reservoirs}}

## Exposição e transmissão

{{exposure_and_transmission}}

## Incubação e janela de transmissão

{{incubation_and_transmission_window}}

## Estágios e progressão

{{stages_and_progression}}

## Sintomas, gravidade e duração

{{symptoms_severity_and_duration}}

## Recaída, recorrência e sequelas

{{relapse_recurrence_and_sequelae}}

## Imunidade, resistência e vulnerabilidades

{{immunity_resistance_and_vulnerabilities}}

## Fatores ambientais e sociais

{{environmental_and_social_factors}}

## Evidências, testes e diagnóstico

{{evidence_tests_and_diagnosis}}

## Prognóstico

{{prognosis}}

## Prevenção e isolamento

{{prevention_and_isolation}}

## Tratamento mundano e acesso

{{mundane_treatment_and_access}}

## Cura mágica

{{magical_healing}}

## Mortalidade e resultados possíveis

{{mortality_and_outcomes}}

## Lore editorial

{{editorial_lore}}

## Observações editoriais

{{editorial_notes_text}}
