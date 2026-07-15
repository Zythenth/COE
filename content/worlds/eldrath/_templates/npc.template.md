---
schema_version: "1.0.0"
content_status: draft
id: "npc.{{npc_slug}}"
name: "{{npc_initial_display_name}}"
tags: []
aliases: []
summary: "{{summary}}"
references: []
art: []
notes: "{{editorial_notes}}"
simulation_profile:
  origin_category_key: "{{origin_category_key}}"
  initial_simulation_category_key: "{{initial_simulation_category_key}}"
  promotion_provenance:
    aggregate_source_key: null
    origin_context_id: null
    promotion_event_id: null
    generated_at: null
    source:
      source_type_key: null
      source_entity_id: null
      source_subrecord_id: null
      source_event_id: null
      source_description: null
identity:
  primary_name: "{{primary_name}}"
  former_names:
    - name_key: "{{former_name_key}}"
      display_name: "{{former_display_name}}"
      valid_from: null
      valid_until: null
      change_reason_key: null
  nicknames:
    - nickname_key: "{{nickname_key}}"
      display_name: "{{nickname_display_name}}"
      use_context_keys: []
      visibility:
        classification_key: "{{nickname_visibility_key}}"
        self_awareness_key: "{{nickname_self_awareness_key}}"
        disclosure_condition_keys: []
  titles:
    - title_key: "{{title_key}}"
      display_title: "{{display_title}}"
      source_entity_id: null
      valid_from: null
      valid_until: null
      visibility:
        classification_key: "{{title_visibility_key}}"
        self_awareness_key: "{{title_self_awareness_key}}"
        disclosure_condition_keys: []
  pronouns:
    subject: "{{pronoun_subject}}"
    object: "{{pronoun_object}}"
    possessive: "{{pronoun_possessive}}"
    reflexive: "{{pronoun_reflexive}}"
    address: "{{pronoun_address}}"
  birth:
    calendar_id: null
    date: null
    place_id: null
    precision_key: "{{birth_precision_key}}"
    earliest_possible_date: null
    latest_possible_date: null
    source:
      source_type_key: "{{birth_source_type_key}}"
      source_entity_id: null
      source_subrecord_id: null
      source_event_id: null
      source_description: "{{birth_source_description}}"
  creature_id: null
  social_origin:
    origin_key: "{{social_origin_key}}"
    source:
      source_type_key: "{{social_origin_source_type_key}}"
      source_entity_id: null
      source_subrecord_id: null
      source_event_id: null
      source_description: "{{social_origin_source_description}}"
  geographic_origin_ids: []
  identifying_features:
    - feature_key: "{{identifying_feature_key}}"
      description: "{{identifying_feature_description}}"
      mechanical_effect_keys: []
cultural_affiliations:
  - culture_id: "culture.{{culture_slug}}"
    affiliation_key: "{{culture_affiliation_key}}"
    intensity: null
    source:
      source_type_key: "{{culture_source_type_key}}"
      source_entity_id: null
      source_subrecord_id: null
      source_event_id: null
      source_description: "{{culture_source_description}}"
    visibility:
      classification_key: "{{culture_visibility_key}}"
      self_awareness_key: "{{culture_self_awareness_key}}"
      disclosure_condition_keys: []
language_proficiencies:
  - language_id: "language.{{language_slug}}"
    speaking: null
    comprehension: null
    reading: null
    writing: null
    source:
      source_type_key: "{{language_source_type_key}}"
      source_entity_id: null
      source_subrecord_id: null
      source_event_id: null
      source_description: "{{language_source_description}}"
    visibility:
      classification_key: "{{language_visibility_key}}"
      self_awareness_key: "{{language_self_awareness_key}}"
      disclosure_condition_keys: []
religion_relations:
  - religion_id: "religion.{{religion_slug}}"
    relation_key: "{{religion_relation_key}}"
    commitment: null
    source:
      source_type_key: "{{religion_source_type_key}}"
      source_entity_id: null
      source_subrecord_id: null
      source_event_id: null
      source_description: "{{religion_source_description}}"
    visibility:
      classification_key: "{{religion_visibility_key}}"
      self_awareness_key: "{{religion_self_awareness_key}}"
      disclosure_condition_keys: []
base_appearance:
  apparent_age_key: "{{apparent_age_key}}"
  build_key: "{{build_key}}"
  face: "{{face_description}}"
  hair: "{{hair_description}}"
  eyes: "{{eyes_description}}"
  skin: "{{skin_description}}"
  marks:
    - mark_key: "{{mark_key}}"
      description: "{{mark_description}}"
  identifying_features:
    - feature_key: "{{appearance_feature_key}}"
      description: "{{appearance_feature_description}}"
  individual_variations:
    - variation_key: "{{appearance_variation_key}}"
      description: "{{appearance_variation_description}}"
      mechanical_effect_keys: []
personality:
  axes:
    boldness: null
    empathy: null
    ambition: null
    discipline: null
    sociability: null
    suspicion: null
    spirituality: null
    curiosity: null
    honesty: null
    aggression: null
  traits:
    - trait_key: "{{trait_key}}"
      intensity: null
      source:
        source_type_key: "{{trait_source_type_key}}"
        source_entity_id: null
        source_subrecord_id: null
        source_event_id: null
        source_description: "{{trait_source_description}}"
      conceptual_effects:
        - effect_key: "{{trait_effect_key}}"
          affected_factor_keys: []
          direction_key: "{{trait_effect_direction_key}}"
      relevant_condition_keys: []
      notes: null
value_profile:
  - value_key: "{{value_key}}"
    weight: null
    source:
      source_type_key: "{{value_source_type_key}}"
      source_entity_id: null
      source_subrecord_id: null
      source_event_id: null
      source_description: "{{value_source_description}}"
    condition_keys: []
need_profile:
  - need_key: "{{need_key}}"
    baseline: null
    sensitivity: null
    corrective_action_keys: []
    condition_keys: []
attributes:
  - attribute_key: "{{attribute_key}}"
    base_value: null
    source:
      source_type_key: "{{attribute_source_type_key}}"
      source_entity_id: null
      source_subrecord_id: null
      source_event_id: null
      source_description: "{{attribute_source_description}}"
competencies:
  - competency_key: "{{competency_key}}"
    base_level: null
    source:
      source_type_key: "{{competency_source_type_key}}"
      source_entity_id: null
      source_subrecord_id: null
      source_event_id: null
      source_description: "{{competency_source_description}}"
    specializations:
      - specialization_key: "{{specialization_key}}"
        level: null
    certifications:
      - certification_key: "{{certification_key}}"
        issuing_entity_id: null
        issued_at: null
    learning_evidence:
      - evidence_key: "{{learning_evidence_key}}"
        source_entity_id: null
        source_event_id: null
        description: "{{learning_evidence_description}}"
perception_profile:
  senses:
    - sense_key: "{{sense_key}}"
      acuity_base: null
      range_modifier: null
      limitation_keys: []
      detection_condition_keys: []
  attention_baseline: null
  awareness_capability_keys: []
  limitation_keys: []
  magical_perception:
    capability_keys: []
    magic_school_ids: []
    limitation_keys: []
magic_profile:
  sensitivity: null
  capacity: null
  control: null
  general_resistance: null
  corruption_tolerance: null
  affinities:
    - magic_school_id: "magic_school.{{affinity_magic_school_slug}}"
      value: null
      source:
        source_type_key: "{{affinity_source_type_key}}"
        source_entity_id: null
        source_subrecord_id: null
        source_event_id: null
        source_description: "{{affinity_source_description}}"
  learning_traditions:
    - tradition_key: "{{magic_learning_tradition_key}}"
      source_entity_ids: []
  block_keys: []
  undiscovered_potential:
    potential_keys: []
    visibility:
      classification_key: "{{undiscovered_potential_visibility_key}}"
      self_awareness_key: "{{undiscovered_potential_self_awareness_key}}"
      disclosure_condition_keys: []
  influence_resistance_profile:
    resistance_keys: []
    magical_protection_ids: []
    condition_keys: []
decision_profile:
  risk_tolerance: null
  change_resistance: null
  influence_resistance_baseline: null
  protected_value_keys: []
  conceptual_behavior_rules:
    - rule_key: "{{behavior_rule_key}}"
      affected_factor_keys: []
      condition_keys: []
      notes: null
initial_state:
  effective_date: null
  lifecycle_state:
    life_state_key: "{{initial_life_state_key}}"
    development_stage_key: "{{initial_development_stage_key}}"
    residence_start_date: null
    retirement_state_key: null
  location:
    location_id: "location.{{initial_location_slug}}"
    residence_location_id: "location.{{residence_location_slug}}"
    source:
      source_type_key: "{{location_source_type_key}}"
      source_entity_id: null
      source_subrecord_id: null
      source_event_id: null
      source_description: "{{location_source_description}}"
  appearance_state:
    clothing_inventory_seed_keys: []
    visible_injury_keys: []
    dirt_key: null
    disguise_key: null
    apparent_aging_key: null
    transformation_keys: []
    visible_magic_effect_seed_keys: []
    visible_equipment_inventory_seed_keys: []
    source:
      source_type_key: "{{appearance_state_source_type_key}}"
      source_entity_id: null
      source_subrecord_id: null
      source_event_id: null
      source_description: "{{appearance_state_source_description}}"
  perception_state:
    consciousness_key: "{{initial_consciousness_key}}"
    attention: null
    temporary_limitation_keys: []
    source:
      source_type_key: "{{perception_state_source_type_key}}"
      source_entity_id: null
      source_subrecord_id: null
      source_event_id: null
      source_description: "{{perception_state_source_description}}"
  family_affiliations:
    - family_id: "family.{{family_slug}}"
      affiliation_key: "{{family_affiliation_key}}"
      effective_date: null
      source:
        source_type_key: "{{family_source_type_key}}"
        source_entity_id: null
        source_subrecord_id: null
        source_event_id: null
        source_description: "{{family_source_description}}"
      visibility:
        classification_key: "{{family_visibility_key}}"
        self_awareness_key: "{{family_self_awareness_key}}"
        disclosure_condition_keys: []
  faction_affiliations:
    - faction_id: "faction.{{faction_slug}}"
      role_key: null
      membership_state_key: "{{membership_state_key}}"
      start_date: null
      entry_method_key: "{{entry_method_key}}"
      commitment: null
      source:
        source_type_key: "{{faction_source_type_key}}"
        source_entity_id: null
        source_subrecord_id: null
        source_event_id: null
        source_description: "{{faction_source_description}}"
      visibility:
        classification_key: "{{faction_visibility_key}}"
        self_awareness_key: "{{faction_self_awareness_key}}"
        disclosure_condition_keys: []
  occupational_state:
    primary_profession:
      profession_id: "profession.{{primary_profession_slug}}"
      rank_key: "{{primary_profession_rank_key}}"
      experience_source: "{{primary_profession_experience_source}}"
      visibility:
        classification_key: "{{primary_profession_visibility_key}}"
        self_awareness_key: "{{primary_profession_self_awareness_key}}"
        disclosure_condition_keys: []
    secondary_professions:
      - profession_id: "profession.{{secondary_profession_slug}}"
        rank_key: "{{secondary_profession_rank_key}}"
        experience_source: "{{secondary_profession_experience_source}}"
        visibility:
          classification_key: "{{secondary_profession_visibility_key}}"
          self_awareness_key: "{{secondary_profession_self_awareness_key}}"
          disclosure_condition_keys: []
    employments:
      - employment_key: "{{employment_key}}"
        profession_id: "profession.{{employment_profession_slug}}"
        employer_id: null
        workplace_location_id: null
        faction_role_key: null
        schedule_keys: []
        compensation:
          money:
            amount: null
            currency_key: null
          period_key: null
        employment_state_key: "{{employment_state_key}}"
        start_date: null
        source:
          source_type_key: "{{employment_source_type_key}}"
          source_entity_id: null
          source_subrecord_id: null
          source_event_id: null
          source_description: "{{employment_source_description}}"
  needs:
    - need_key: "{{initial_need_key}}"
      satisfaction: null
      evaluated_at: null
      source:
        source_type_key: "{{need_state_source_type_key}}"
        source_entity_id: null
        source_subrecord_id: null
        source_event_id: null
        source_description: "{{need_state_source_description}}"
      notes: null
  emotions:
    - emotion_key: "{{emotion_key}}"
      intensity: null
      trigger:
        trigger_key: "{{emotion_trigger_key}}"
        trigger_entity_ids: []
        trigger_description: "{{emotion_trigger_description}}"
      target_id: null
      origin_event_id: null
      origin_memory_id: null
      started_at: null
      decay_profile_key: "{{emotion_decay_profile_key}}"
      reinforcement_keys: []
      visibility:
        classification_key: "{{emotion_visibility_key}}"
        self_awareness_key: "{{emotion_self_awareness_key}}"
        disclosure_condition_keys: []
  attribute_modifiers:
    - modifier_key: "{{attribute_modifier_key}}"
      attribute_key: "{{modified_attribute_key}}"
      operation: "{{attribute_modifier_operation}}"
      value: null
      persistence_key: "{{attribute_modifier_persistence_key}}"
      duration:
        value: null
        unit_key: null
      source:
        source_type_key: "{{attribute_modifier_source_type_key}}"
        source_entity_id: null
        source_subrecord_id: null
        source_event_id: null
        source_description: "{{attribute_modifier_source_description}}"
      condition_keys: []
  competency_progress:
    - competency_key: "{{progress_competency_key}}"
      initial_experience: null
      last_practice_at: null
      source:
        source_type_key: "{{competency_progress_source_type_key}}"
        source_entity_id: null
        source_subrecord_id: null
        source_event_id: null
        source_description: "{{competency_progress_source_description}}"
  health:
    injuries:
      - injury_key: "{{injury_key}}"
        injury_type_key: "{{injury_type_key}}"
        body_region_key: "{{injury_body_region_key}}"
        severity: null
        pain: null
        limitation_keys: []
        started_at: null
        source:
          source_type_key: "{{injury_source_type_key}}"
          source_entity_id: null
          source_subrecord_id: null
          source_event_id: null
          source_description: "{{injury_source_description}}"
        evidence_ids: []
        visibility:
          classification_key: "{{injury_visibility_key}}"
          self_awareness_key: "{{injury_self_awareness_key}}"
          disclosure_condition_keys: []
    disease_instances:
      - disease_instance_key: "{{disease_instance_key}}"
        disease_id: "disease.{{disease_slug}}"
        exposure_source_id: null
        exposure_event_id: null
        exposed_at: null
        stage_key: "{{disease_stage_key}}"
        severity: null
        symptom_keys: []
        transmissibility: null
        true_prognosis_key: null
        evidence_ids: []
        visibility:
          classification_key: "{{disease_visibility_key}}"
          self_awareness_key: "{{disease_self_awareness_key}}"
          disclosure_condition_keys: []
    disabilities:
      - disability_key: "{{disability_key}}"
        capability_keys: []
        variation_keys: []
        adaptation_keys: []
        barrier_keys: []
        support_entity_ids: []
        source:
          source_type_key: "{{disability_source_type_key}}"
          source_entity_id: null
          source_subrecord_id: null
          source_event_id: null
          source_description: "{{disability_source_description}}"
        visibility:
          classification_key: "{{disability_visibility_key}}"
          self_awareness_key: "{{disability_self_awareness_key}}"
          disclosure_condition_keys: []
    pain:
      - pain_key: "{{pain_key}}"
        intensity: null
        body_region_key: null
        started_at: null
        duration:
          value: null
          unit_key: null
        source:
          source_type_key: "{{pain_source_type_key}}"
          source_entity_id: null
          source_subrecord_id: null
          source_event_id: null
          source_description: "{{pain_source_description}}"
    fatigue:
      - fatigue_key: "{{fatigue_key}}"
        intensity: null
        started_at: null
        duration:
          value: null
          unit_key: null
        source:
          source_type_key: "{{fatigue_source_type_key}}"
          source_entity_id: null
          source_subrecord_id: null
          source_event_id: null
          source_description: "{{fatigue_source_description}}"
    intoxications:
      - intoxication_key: "{{intoxication_key}}"
        resource_id: null
        item_id: null
        dose:
          value: null
          unit_key: null
        intensity: null
        exposure_route_key: "{{intoxication_exposure_route_key}}"
        started_at: null
        source_event_id: null
    immunities:
      - immunity_key: "{{immunity_key}}"
        disease_id: null
        scope_keys: []
        effectiveness: null
        started_at: null
        duration:
          value: null
          unit_key: null
        source:
          source_type_key: "{{immunity_source_type_key}}"
          source_entity_id: null
          source_subrecord_id: null
          source_event_id: null
          source_description: "{{immunity_source_description}}"
    active_magic_effects:
      - effect_seed_key: "{{health_magic_effect_seed_key}}"
        magic_effect_id: "magic_effect.{{health_magic_effect_slug}}"
        source_entity_id: null
        started_at: null
        duration:
          value: null
          unit_key: null
        parameters: []
    true_prognosis:
      prognosis_key: null
      source_condition_keys: []
    known_diagnoses:
      - diagnosis_key: "{{diagnosis_key}}"
        observer_npc_id: "npc.{{diagnosis_observer_slug}}"
        hypothesis_disease_id: null
        hypothesis_condition_key: null
        confidence: null
        evidence_ids: []
        source:
          source_type_key: "{{diagnosis_source_type_key}}"
          source_entity_id: null
          source_subrecord_id: null
          source_event_id: null
          source_description: "{{diagnosis_source_description}}"
        diagnosed_at: null
        visibility:
          classification_key: "{{diagnosis_visibility_key}}"
          self_awareness_key: "{{diagnosis_self_awareness_key}}"
          disclosure_condition_keys: []
    known_prognoses:
      - prognosis_record_key: "{{known_prognosis_key}}"
        observer_npc_id: "npc.{{prognosis_observer_slug}}"
        prognosis_key: "{{prognosis_hypothesis_key}}"
        confidence: null
        evidence_ids: []
        source:
          source_type_key: "{{prognosis_source_type_key}}"
          source_entity_id: null
          source_subrecord_id: null
          source_event_id: null
          source_description: "{{prognosis_source_description}}"
        assessed_at: null
        visibility:
          classification_key: "{{prognosis_visibility_key}}"
          self_awareness_key: "{{prognosis_self_awareness_key}}"
          disclosure_condition_keys: []
  material_state:
    money_balances:
      - balance_key: "{{money_balance_key}}"
        money:
          amount: null
          currency_key: null
        storage_location_id: null
        source:
          source_type_key: "{{money_source_type_key}}"
          source_entity_id: null
          source_subrecord_id: null
          source_event_id: null
          source_description: "{{money_source_description}}"
    resource_holdings:
      - resource_holding_key: "{{resource_holding_key}}"
        resource_id: "resource.{{resource_slug}}"
        quantity:
          value: null
          unit_key: null
        storage_location_id: null
        reserved_quantity:
          value: null
          unit_key: null
        source:
          source_type_key: "{{resource_holding_source_type_key}}"
          source_entity_id: null
          source_subrecord_id: null
          source_event_id: null
          source_description: "{{resource_holding_source_description}}"
    inventory_seeds:
      - inventory_seed_key: "{{inventory_seed_key}}"
        item_id: "item.{{item_slug}}"
        quantity:
          value: null
          unit_key: null
        quality_key: null
        placement_key: "{{item_placement_key}}"
        storage_location_id: null
        container_seed_key: null
        sentimental: null
        provenance:
          source:
            source_type_key: "{{item_provenance_source_type_key}}"
            source_entity_id: null
            source_subrecord_id: null
            source_event_id: null
            source_description: "{{item_provenance_source_description}}"
          previous_owner_ids: []
          origin_event_id: null
          acquisition_method_key: "{{item_acquisition_method_key}}"
          notes: null
        notes: null
    artifact_holdings:
      - artifact_holding_key: "{{artifact_holding_key}}"
        artifact_id: "artifact.{{artifact_slug}}"
        placement_key: "{{artifact_placement_key}}"
        storage_location_id: null
        recognized_ownership_key: "{{artifact_ownership_key}}"
        source:
          source_type_key: "{{artifact_holding_source_type_key}}"
          source_entity_id: null
          source_subrecord_id: null
          source_event_id: null
          source_description: "{{artifact_holding_source_description}}"
    property_interests:
      - property_interest_key: "{{property_interest_key}}"
        interest_type_key: "{{property_interest_type_key}}"
        inventory_seed_key: null
        artifact_id: null
        location_id: null
        resource_holding_key: null
        contract_key: null
        counterparty_entity_ids: []
        share: null
        effective_date: null
        source:
          source_type_key: "{{property_interest_source_type_key}}"
          source_entity_id: null
          source_subrecord_id: null
          source_event_id: null
          source_description: "{{property_interest_source_description}}"
        visibility:
          classification_key: "{{property_interest_visibility_key}}"
          self_awareness_key: "{{property_interest_self_awareness_key}}"
          disclosure_condition_keys: []
    debts:
      - debt_key: "{{debt_key}}"
        creditor_entity_id: null
        debtor_entity_id: null
        money:
          amount: null
          currency_key: null
        resource_id: null
        quantity:
          value: null
          unit_key: null
        due_at: null
        source:
          source_type_key: "{{debt_source_type_key}}"
          source_entity_id: null
          source_subrecord_id: null
          source_event_id: null
          source_description: "{{debt_source_description}}"
        visibility:
          classification_key: "{{debt_visibility_key}}"
          self_awareness_key: "{{debt_self_awareness_key}}"
          disclosure_condition_keys: []
    contracts:
      - contract_key: "{{contract_key}}"
        contract_type_key: "{{contract_type_key}}"
        party_entity_ids: []
        obligation_keys: []
        effective_date: null
        end_date: null
        source_event_id: null
        visibility:
          classification_key: "{{contract_visibility_key}}"
          self_awareness_key: "{{contract_self_awareness_key}}"
          disclosure_condition_keys: []
    income_sources:
      - income_key: "{{income_key}}"
        source_entity_id: null
        money:
          amount: null
          currency_key: null
        period_key: null
        condition_keys: []
    expense_commitments:
      - expense_key: "{{expense_key}}"
        target_entity_id: null
        money:
          amount: null
          currency_key: null
        period_key: null
        condition_keys: []
  magic_mastery:
    - mastery_key: "{{magic_mastery_key}}"
      spell_id: null
      ritual_id: null
      stage_key: "{{magic_mastery_stage_key}}"
      progress: null
      mastery: null
      stability: null
      source:
        source_type_key: "{{magic_mastery_source_type_key}}"
        source_entity_id: null
        source_subrecord_id: null
        source_event_id: null
        source_description: "{{magic_mastery_source_description}}"
      teacher_npc_id: null
      started_at: null
      last_practice_at: null
      known_risk_keys: []
      personal_variants:
        - variant_key: "{{personal_magic_variant_key}}"
          difference_keys: []
          source_event_id: null
      perceived_legality:
        jurisdiction_id: null
        belief_key: "{{perceived_legality_belief_key}}"
        confidence: null
        source:
          source_type_key: "{{perceived_legality_source_type_key}}"
          source_entity_id: null
          source_subrecord_id: null
          source_event_id: null
          source_description: "{{perceived_legality_source_description}}"
      visibility:
        classification_key: "{{magic_mastery_visibility_key}}"
        self_awareness_key: "{{magic_mastery_self_awareness_key}}"
        disclosure_condition_keys: []
  goals:
    - id: "goal.{{npc_slug}}.{{goal_slug}}"
      owner_npc_id: "npc.{{npc_slug}}"
      goal_type_key: "{{goal_type_key}}"
      structured_description:
        action_key: "{{goal_action_key}}"
        subject_id: "npc.{{npc_slug}}"
        target_entity_ids: []
        outcome_key: "{{goal_outcome_key}}"
        editorial_summary: "{{goal_editorial_summary}}"
      priority: null
      source:
        source_type_key: "{{goal_source_type_key}}"
        source_entity_id: null
        source_subrecord_id: null
        source_event_id: null
        source_description: "{{goal_source_description}}"
      state_key: "{{goal_state_key}}"
      deadline: null
      success_conditions:
        - condition_key: "{{goal_success_condition_key}}"
          condition_type_key: "{{goal_success_condition_type_key}}"
          subject_id: null
          observed_property_key: "{{goal_success_property_key}}"
          operator_key: "{{goal_success_operator_key}}"
          number_value: null
          boolean_value: null
          key_value: null
          entity_id_value: null
          quantity_value: null
          reference_ids: []
          description: "{{goal_success_condition_description}}"
      failure_conditions:
        - condition_key: "{{goal_failure_condition_key}}"
          condition_type_key: "{{goal_failure_condition_type_key}}"
          subject_id: null
          observed_property_key: "{{goal_failure_property_key}}"
          operator_key: "{{goal_failure_operator_key}}"
          number_value: null
          boolean_value: null
          key_value: null
          entity_id_value: null
          quantity_value: null
          reference_ids: []
          description: "{{goal_failure_condition_description}}"
      steps:
        - step_key: "{{goal_step_key}}"
          order: null
          action_key: "{{goal_step_action_key}}"
          target_entity_ids: []
          condition_keys: []
      required_resources:
        - resource_id: null
          item_id: null
          quantity:
            value: null
            unit_key: null
      ally_npc_ids: []
      obstacle_entity_ids: []
      related_secret_id: null
      initial_progress: null
      related_event_ids: []
      visibility:
        classification_key: "{{goal_visibility_key}}"
        self_awareness_key: "{{goal_self_awareness_key}}"
        disclosure_condition_keys: []
  fears:
    - id: "fear.{{npc_slug}}.{{fear_slug}}"
      owner_npc_id: "npc.{{npc_slug}}"
      category_key: "{{fear_category_key}}"
      target_entity_ids: []
      theme_key: "{{fear_theme_key}}"
      intensity: null
      source:
        source_type_key: "{{fear_source_type_key}}"
        source_entity_id: null
        source_subrecord_id: null
        source_event_id: null
        source_description: "{{fear_source_description}}"
      trigger_keys: []
      evidence_ids: []
      preferred_response_keys: []
      coping_strategy_keys: []
      related_memory_ids: []
      visibility:
        classification_key: "{{fear_visibility_key}}"
        self_awareness_key: "{{fear_self_awareness_key}}"
        disclosure_condition_keys: []
  secrets:
    - id: "secret.{{npc_slug}}.{{secret_slug}}"
      owner_npc_id: "npc.{{npc_slug}}"
      structured_truth:
        subject_id: null
        property_key: "{{secret_property_key}}"
        number_value: null
        boolean_value: null
        key_value: null
        entity_id_value: null
        reference_ids: []
        editorial_summary: "{{secret_truth_summary}}"
      involved_entity_ids: []
      origin_event_id: null
      evidence_ids: []
      severity: null
      exposure_risk: null
      expected_consequences:
        - consequence_key: "{{secret_consequence_key}}"
          affected_entity_ids: []
          description: "{{secret_consequence_description}}"
      initial_state_key: "{{secret_initial_state_key}}"
      visibility:
        classification_key: "{{secret_visibility_key}}"
        self_awareness_key: "{{secret_self_awareness_key}}"
        disclosure_condition_keys: []
  knowledge_records:
    - id: "knowledge.{{npc_slug}}.{{knowledge_slug}}"
      owner_npc_id: "npc.{{npc_slug}}"
      statement:
        subject_id: null
        property_key: "{{knowledge_property_key}}"
        number_value: null
        boolean_value: null
        key_value: null
        entity_id_value: null
        quantity:
          value: null
          unit_key: null
        reference_ids: []
      known_content: "{{known_content_summary}}"
      source:
        source_type_key: "{{knowledge_source_type_key}}"
        source_entity_id: null
        source_subrecord_id: null
        source_event_id: null
        source_description: "{{knowledge_source_description}}"
      acquired_at: null
      evidence_ids: []
      confidence: null
      last_confirmed_at: null
      contradictions:
        - contradiction_key: "{{knowledge_contradiction_key}}"
          reference_ids: []
          description: "{{knowledge_contradiction_description}}"
      perceptual_or_communicated_origin:
        origin_type_key: "{{knowledge_origin_type_key}}"
        perception_record_id: null
        communicator_npc_id: null
      visibility:
        classification_key: "{{knowledge_visibility_key}}"
        self_awareness_key: "{{knowledge_self_awareness_key}}"
        disclosure_condition_keys: []
  belief_records:
    - id: "belief.{{npc_slug}}.{{belief_slug}}"
      owner_npc_id: "npc.{{npc_slug}}"
      epistemic_state_key: "{{belief_or_suspicion_key}}"
      subject:
        subject_id: null
        property_key: "{{belief_property_key}}"
      believed_value:
        number_value: null
        boolean_value: null
        key_value: null
        entity_id_value: null
        reference_ids: []
        editorial_summary: "{{believed_value_summary}}"
      confidence: null
      source:
        source_type_key: "{{belief_source_type_key}}"
        source_entity_id: null
        source_subrecord_id: null
        source_event_id: null
        source_description: "{{belief_source_description}}"
      evidence_ids: []
      acquired_at: null
      reinforcement_ids: []
      contradiction_ids: []
      visibility:
        classification_key: "{{belief_visibility_key}}"
        self_awareness_key: "{{belief_self_awareness_key}}"
        disclosure_condition_keys: []
  memories:
    - id: "memory.{{npc_slug}}.{{memory_slug}}"
      owner_npc_id: "npc.{{npc_slug}}"
      event_id: null
      situation_key: "{{memory_situation_key}}"
      perceived_version: "{{memory_perceived_version}}"
      origin_type_key: "{{memory_origin_type_key}}"
      source:
        source_type_key: "{{memory_source_type_key}}"
        source_entity_id: null
        source_subrecord_id: null
        source_event_id: null
        source_description: "{{memory_source_description}}"
      participant_ids: []
      location_id: null
      occurred_at: null
      emotion_records:
        - emotion_key: "{{memory_emotion_key}}"
          intensity: null
      valence: null
      salience: null
      certainty: null
      tags: []
      related_secret_id: null
      last_recalled_at: null
      relationship_effects:
        - target_npc_id: null
          affected_dimension_keys: []
          direction_keys: []
      forgetting_rate:
        quantity:
          value: null
          unit_key: null
        period_key: null
      visibility:
        classification_key: "{{memory_visibility_key}}"
        self_awareness_key: "{{memory_self_awareness_key}}"
        disclosure_condition_keys: []
  relationship_records:
    - id: "relationship.{{npc_slug}}.{{target_npc_slug}}"
      source_npc_id: "npc.{{npc_slug}}"
      target_npc_id: "npc.{{target_npc_slug}}"
      familiarity: null
      trust: null
      affection: null
      respect: null
      fear: null
      attraction: null
      resentment: null
      debt:
        signed_money:
          amount: null
          currency_key: null
        signed_quantity:
          value: null
          unit_key: null
      loyalty: null
      dependency: null
      derived_type_keys: []
      kinship_facts:
        - fact_key: "{{kinship_fact_key}}"
          kinship_type_key: "{{kinship_type_key}}"
          reciprocal_type_key: "{{reciprocal_kinship_type_key}}"
          source_event_id: null
      origin_event_ids: []
      relevant_memory_ids: []
      last_initial_interaction_at: null
      visibility:
        classification_key: "{{relationship_visibility_key}}"
        self_awareness_key: "{{relationship_self_awareness_key}}"
        disclosure_condition_keys: []
  prestige:
    value: null
    causes:
      - cause_key: "{{prestige_cause_key}}"
        source_entity_ids: []
        source_event_ids: []
        description: "{{prestige_cause_description}}"
    effective_date: null
    visibility:
      classification_key: "{{prestige_visibility_key}}"
      self_awareness_key: "{{prestige_self_awareness_key}}"
      disclosure_condition_keys: []
  reputations:
    - reputation_key: "{{reputation_key}}"
      audience_type_key: "{{reputation_audience_type_key}}"
      audience_entity_id: null
      context_key: "{{reputation_context_key}}"
      value: null
      scale_key: "{{reputation_scale_key}}"
      confidence: null
      source:
        source_type_key: "{{reputation_source_type_key}}"
        source_entity_id: null
        source_subrecord_id: null
        source_event_id: null
        source_description: "{{reputation_source_description}}"
      cause_event_ids: []
      effective_date: null
      visibility:
        classification_key: "{{reputation_visibility_key}}"
        self_awareness_key: "{{reputation_self_awareness_key}}"
        disclosure_condition_keys: []
  routine_blocks:
    - routine_key: "{{routine_key}}"
      period_key: "{{routine_period_key}}"
      time_window:
        starts_at: null
        ends_at: null
      intended_action_key: "{{routine_action_key}}"
      location_id: null
      priority: null
      frequency:
        frequency_key: "{{routine_frequency_key}}"
        interval:
          value: null
          unit_key: null
      conditions:
        - condition_key: "{{routine_condition_key}}"
          condition_type_key: "{{routine_condition_type_key}}"
          subject_id: null
          observed_property_key: "{{routine_condition_property_key}}"
          operator_key: "{{routine_condition_operator_key}}"
          number_value: null
          boolean_value: null
          key_value: null
          entity_id_value: null
          quantity_value: null
          reference_ids: []
          description: "{{routine_condition_description}}"
      flexibility: null
      interruptible: null
      related_goal_id: null
  commitments:
    - commitment_key: "{{commitment_key}}"
      commitment_type_key: "{{commitment_type_key}}"
      involved_entity_ids: []
      source:
        source_type_key: "{{commitment_source_type_key}}"
        source_entity_id: null
        source_subrecord_id: null
        source_event_id: null
        source_description: "{{commitment_source_description}}"
      effective_date: null
      deadline: null
      obligation_keys: []
      consequence_keys: []
      related_goal_ids: []
      visibility:
        classification_key: "{{commitment_visibility_key}}"
        self_awareness_key: "{{commitment_self_awareness_key}}"
        disclosure_condition_keys: []
---

> **Aviso de template:** este arquivo não é conteúdo real. Ele segue o [contrato editorial de NPCs](../../../../docs/world/schemas/NPC_SYSTEM_ENTITIES.md). Placeholders são exclusivos de _templates e proibidos em conteúdo approved. Todo valor mutável está sob initial_state; valores atuais e mudanças posteriores pertencem ao save.

# Biografia

{{biography}}

## Aparência narrativa

{{appearance_narrative}}

## Origem e contexto

{{origin_and_context}}

## Personalidade, valores e conflitos internos

{{personality_values_and_internal_conflicts}}

## Voz e comportamento observável

{{voice_and_observable_behavior}}

## Família, instituições e trabalho

{{family_institutions_and_work}}

## Saúde e capacidades

{{health_and_capabilities_context}}

## Magia

{{magic_context}}

## Relações e posição social

{{relationships_and_social_position}}

## Sementes narrativas

{{narrative_seeds}}

## Observações editoriais

{{editorial_notes_text}}
