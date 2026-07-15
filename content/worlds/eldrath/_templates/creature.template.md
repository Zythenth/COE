---
schema_version: "1.0.0"
content_status: draft
id: "creature.{{creature_slug}}"
name: "{{creature_name}}"
tags: []
aliases: []
summary: "{{summary}}"
references: []
art: []
notes: "{{editorial_notes}}"
classification:
  creature_type_key: "{{creature_type_key}}"
  taxonomic_group_key: "{{taxonomic_group_key}}"
  origin_classification_key: "{{origin_classification_key}}"
  classification_keys: []
origin:
  description: "{{origin_description}}"
  region_ids: []
  location_ids: []
  event_id: null
  magic_school_ids: []
  magic_effect_ids: []
alternative_form_ids: []
anatomy:
  body_plan_key: "{{body_plan_key}}"
  body_regions:
    - body_region_key: "{{body_region_key}}"
      editorial_name: "{{body_region_name}}"
      function_keys: []
      vulnerability_keys: []
      structural_immunity_keys: []
      notes: null
  relevant_system_keys: []
  sensory_capabilities:
    - sense_key: "{{sense_key}}"
      capability_key: "{{sensory_capability_key}}"
      range:
        value: null
        unit_key: null
      limitation_keys: []
      notes: null
  locomotion_modes:
    - locomotion_key: "{{locomotion_key}}"
      environment_keys: []
      limitation_keys: []
      notes: null
  respiration_modes:
    - respiration_key: "{{respiration_key}}"
      environment_keys: []
      limitation_keys: []
      notes: null
  anatomical_vulnerability_keys: []
  structural_immunity_keys: []
size_profile:
  size_class_key: "{{size_class_key}}"
  measurements:
    - measurement_key: "{{size_measurement_key}}"
      minimum:
        value: null
        unit_key: null
      maximum:
        value: null
        unit_key: null
      notes: null
life_cycle:
  life_stages:
    - life_stage_key: "{{life_stage_key}}"
      editorial_name: "{{life_stage_name}}"
      order: null
      typical_duration:
        minimum:
          value: null
          unit_key: null
        maximum:
          value: null
          unit_key: null
      development_keys: []
      capability_keys: []
      notes: null
  longevity:
    minimum:
      value: null
      unit_key: null
    maximum:
      value: null
      unit_key: null
  development_keys: []
reproduction_profile:
  reproduction_mode_key: "{{reproduction_mode_key}}"
  requirement_keys: []
  seasonality_keys: []
  care_keys: []
  development_keys: []
  notes: null
cognition_profile:
  intelligence_key: "{{intelligence_key}}"
  learning_capability_keys: []
  planning_capability_keys: []
  memory_capability_keys: []
  limitation_keys: []
sentience_profile:
  sentience_key: "{{sentience_key}}"
  awareness_keys: []
  subjective_experience_keys: []
  limitation_keys: []
communication_profile:
  modality_keys: []
  complexity_key: "{{communication_complexity_key}}"
  language_capability_keys: []
  interpretation_requirement_keys: []
  limitation_keys: []
social_profile:
  sociability_key: "{{sociability_key}}"
  group_structure_keys: []
  cooperation_keys: []
  conflict_keys: []
  variation_keys: []
political_agency_profile:
  capability_keys: []
  limitation_keys: []
  eligibility_condition_keys: []
behavior_profile:
  activity_period_keys: []
  seasonal_behavior_keys: []
  behaviors:
    - behavior_key: "{{behavior_key}}"
      trigger_keys: []
      life_stage_keys: []
      environment_keys: []
      response_keys: []
      learned: null
      trainable: null
      notes: null
  threat_response_keys: []
  care_behavior_keys: []
  variation_keys: []
diet_profile:
  diet_category_keys: []
  required_resource_ids: []
  preferred_resource_ids: []
  prohibited_resource_ids: []
  feeding_condition_keys: []
  notes: null
ecological_relations:
  - relation_key: "{{ecological_relation_key}}"
    relation_type_key: "{{ecological_relation_type_key}}"
    target_creature_id: "creature.{{target_creature_slug}}"
    condition_keys: []
    relevance: null
    notes: null
habitat_compatibility:
  region_ids: []
  location_ids: []
  biome_keys: []
  climate_keys: []
  altitude:
    minimum:
      value: null
      unit_key: null
    maximum:
      value: null
      unit_key: null
  water_requirement_keys: []
  shelter_requirement_keys: []
  food_availability_keys: []
  magical_presence_keys: []
  settlement_condition_keys: []
  limiting_factor_keys: []
migration_profile:
  capable: null
  pattern_keys: []
  trigger_keys: []
  route_requirement_keys: []
  timing_keys: []
  limitation_keys: []
territoriality_profile:
  territoriality_key: "{{territoriality_key}}"
  territory_requirement_keys: []
  defense_behavior_keys: []
  coexistence_condition_keys: []
ecological_pressures:
  - pressure_key: "{{ecological_pressure_key}}"
    pressure_type_key: "{{ecological_pressure_type_key}}"
    source_entity_ids: []
    condition_keys: []
    effect_direction_key: "{{ecological_effect_direction_key}}"
    relevance: null
    notes: null
magic_relation:
  affinity_magic_school_ids: []
  resistance_magic_school_ids: []
  vulnerability_magic_school_ids: []
  related_magic_effect_ids: []
  dependency_keys: []
  manifestation_keys: []
  evidence_keys: []
  notes: null
species_health_profile:
  baseline_resistance_keys: []
  structural_immunity_keys: []
  vulnerability_keys: []
  susceptibility_factor_keys: []
  care_need_keys: []
  environmental_tolerance_keys: []
  pain_response_keys: []
  fatigue_response_keys: []
  toxin_response_keys: []
  magical_health_interaction_keys: []
danger_profile:
  danger_keys: []
  trigger_keys: []
  target_category_keys: []
  severity:
    value: null
    scale_key: health_0_100
  evidence_keys: []
defense_profile:
  defense_keys: []
  resistance_keys: []
  evasion_keys: []
  effect_applications:
    - application_key: "{{defense_effect_application_key}}"
      magic_effect_id: "magic_effect.{{defense_magic_effect_slug}}"
      target_binding_key: "{{defense_target_binding_key}}"
      parameters: []
      condition_keys: []
      trigger_keys: []
domestication_profile:
  possible: null
  requirement_keys: []
  welfare_requirement_keys: []
  risk_keys: []
  limitation_keys: []
  required_profession_ids: []
  required_item_ids: []
training_profile:
  possible: null
  trainable_capability_keys: []
  requirement_keys: []
  required_profession_ids: []
  required_item_ids: []
  risk_keys: []
  limitation_keys: []
yield_profiles:
  - yield_key: "{{yield_key}}"
    acquisition_method_key: "{{acquisition_method_key}}"
    resource_id: null
    item_id: null
    nonlethal: null
    condition_keys: []
    required_profession_ids: []
    required_item_ids: []
    quantity:
      value: null
      unit_key: null
    risk_keys: []
    ecological_consequence_keys: []
    regulated_activity_keys: []
    related_law_ids: []
    notes: null
profession_interactions:
  - profession_id: "profession.{{profession_slug}}"
    interaction_key: "{{profession_interaction_key}}"
    capability_keys: []
    risk_keys: []
    condition_keys: []
    notes: null
cultural_perceptions:
  - perception_key: "{{cultural_perception_key}}"
    culture_id: null
    religion_id: null
    faction_id: null
    region_id: null
    profession_id: null
    attitude_keys: []
    foundation_keys: []
    source_entity_ids: []
    initial_confidence: null
    notes: null
presence_signals:
  - signal_key: "{{presence_signal_key}}"
    modality_key: "{{presence_signal_modality_key}}"
    intensity:
      value: null
      scale_key: health_0_100
    persistence:
      value: null
      unit_key: null
    detection_condition_keys: []
    notes: null
evidence_profiles:
  - evidence_key: "{{presence_evidence_key}}"
    evidence_type_key: "{{presence_evidence_type_key}}"
    persistence:
      value: null
      unit_key: null
    detection_condition_keys: []
    identification_requirement_keys: []
    notes: null
initial_state:
  effective_date: null
  population_distribution:
    - region_id: null
      settlement_id: null
      location_id: null
      quantity:
        value: null
        unit_key: null
      environmental_capacity:
        value: null
        unit_key: null
      trend_key: "{{initial_population_trend_key}}"
      foundation: "{{initial_population_foundation}}"
      notes: null
deferred_decisions:
  - "{{deferred_decision}}"
---

> **Aviso de template:** este arquivo não é conteúdo real. Ele segue o [contrato de criaturas, saúde e doenças](../../../../docs/world/schemas/CREATURE_HEALTH_AND_DISEASE_ENTITIES.md). Placeholders são proibidos em conteúdo `approved`; a entidade representa espécie ou tipo, nunca um indivíduo persistente. População e distribuição atuais pertencem ao save, e relações específicas de hospedeiro, vetor e reservatório são derivadas de `disease.*`.

# Visão geral

{{overview}}

## Classificação e origem

{{classification_and_origin}}

## Anatomia abstrata e tamanho

{{anatomy_and_size}}

## Ciclo de vida e desenvolvimento

{{life_cycle_and_development}}

## Cognição, sensibilidade e comunicação

{{cognition_sentience_and_communication}}

## Sociabilidade e agência

{{sociality_and_agency}}

## Comportamento e atividade

{{behavior_and_activity}}

## Dieta e relações ecológicas

{{diet_and_ecological_relations}}

## Habitat, migração e territorialidade

{{habitat_migration_and_territoriality}}

## População inicial e pressões ecológicas

{{initial_population_and_ecological_pressures}}

## Relação com magia e saúde estrutural

{{magic_and_species_health}}

## Perigo e defesa

{{danger_and_defense}}

## Domesticação e treinamento

{{domestication_and_training}}

## Recursos e itens potencialmente obtidos

{{potential_yields}}

## Profissões e percepção cultural

{{professions_and_cultural_perceptions}}

## Sinais, rastros e evidências

{{signals_tracks_and_evidence}}

## Lore editorial

{{editorial_lore}}

## Observações editoriais

{{editorial_notes_text}}
