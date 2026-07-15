---
schema_version: "1.0.0"
id: "faction.{{faction_slug}}"
name: "{{faction_name}}"
content_status: draft
tags: []
aliases: []
summary: "{{summary}}"
references: []
art: []
notes: "{{editorial_notes}}"
faction_type_key: "{{faction_type_key}}"
scope_classification:
  counts_as_main_faction: null
  counts_as_magic_institution: null
symbol:
  symbol_key: "{{faction_symbol_key}}"
  description: "{{faction_symbol_description}}"
motto: null
foundation:
  date: null
  period_key: null
  event_id: null
  summary: "{{foundation_summary}}"
purpose:
  purpose_key: "{{purpose_key}}"
  summary: "{{purpose_summary}}"
ideology:
  ideology_keys:
    - "{{ideology_key}}"
  summary: "{{ideology_summary}}"
values:
  - value_key: "{{value_key}}"
    editorial_name: "{{value_name}}"
    summary: "{{value_summary}}"
taboos:
  - taboo_key: "{{taboo_key}}"
    editorial_name: "{{taboo_name}}"
    summary: "{{taboo_summary}}"
founding_objectives:
  - objective_key: "{{founding_objective_key}}"
    summary: "{{founding_objective_summary}}"
membership_criteria:
  - criterion_key: "{{membership_criterion_key}}"
    subject_key: "{{membership_subject_key}}"
    condition_keys: []
recruitment_policy:
  policy_key: "{{recruitment_policy_key}}"
  method_keys: []
  condition_keys: []
exit_policy:
  policy_key: "{{exit_policy_key}}"
  condition_keys: []
  consequence_keys: []
expulsion_policy:
  policy_key: "{{expulsion_policy_key}}"
  condition_keys: []
  decision_process_key: null
  consequence_keys: []
internal_structure:
  - unit_key: "{{internal_unit_key}}"
    editorial_name: "{{internal_unit_name}}"
    purpose: "{{internal_unit_purpose}}"
    parent_unit_key: null
    authority_keys: []
roles:
  - role_key: "{{role_key}}"
    editorial_name: "{{role_name}}"
    purpose: "{{role_purpose}}"
    authority:
      authority_keys: []
      scope_keys: []
      limitation_keys: []
    requirements:
      profession_ids: []
      criterion_keys: []
      condition_keys: []
    allowed_quantity:
      minimum: null
      maximum: null
    occupancy_rule:
      rule_key: "{{occupancy_rule_key}}"
      condition_keys: []
    succession_rule:
      rule_key: "{{role_succession_rule_key}}"
      condition_keys: []
    decision_process_keys: []
decision_processes:
  - process_key: "{{decision_process_key}}"
    editorial_name: "{{decision_process_name}}"
    purpose: "{{decision_process_purpose}}"
    scope_keys: []
    eligible_role_keys: []
    method_key: "{{decision_method_key}}"
    quorum_rule:
      rule_key: "{{quorum_rule_key}}"
      value: null
    tiebreak_rule:
      rule_key: "{{tiebreak_rule_key}}"
      role_key: null
    record_rule_key: "{{decision_record_rule_key}}"
succession_rules:
  - succession_rule_key: "{{institutional_succession_rule_key}}"
    scope_role_keys: []
    method_key: "{{institutional_succession_method_key}}"
    condition_keys: []
internal_authority:
  authority_keys:
    - "{{internal_authority_key}}"
  limitation_keys: []
policies:
  - policy_key: "{{institutional_policy_key}}"
    editorial_name: "{{institutional_policy_name}}"
    scope_keys: []
    rule_keys: []
culture_ids: []
religion_ids: []
dynastic_family_id: null
profession_ids: []
magic_program:
  school_relations:
    - magic_school_id: "magic_school.{{magic_school_slug}}"
      focus_keys: []
      teaching_authorization_key: null
      specialization_keys: []
      research_keys: []
      internal_prohibition_keys: []
      notes: null
  teaching_policy:
    policy_key: "{{magic_teaching_policy_key}}"
    access_condition_keys: []
    authorization_keys: []
    restriction_keys: []
    notes: null
  research_policy:
    policy_key: "{{magic_research_policy_key}}"
    priority_keys: []
    authorization_keys: []
    restriction_keys: []
    notes: null
  secrecy_policy:
    policy_key: "{{magic_secrecy_policy_key}}"
    classification_keys: []
    disclosure_condition_keys: []
    notes: null
  access_requirements:
    - requirement_key: "{{magic_access_requirement_key}}"
      condition_keys: []
      required_profession_ids: []
      required_religion_ids: []
      required_law_ids: []
      notes: null
  licensing_capacity:
    enabled: null
    license_category_keys: []
    jurisdiction_ids: []
    authorization_law_ids: []
    limitation_keys: []
    notes: null
  controlled_magic_category_keys: []
  controlled_magic_tag_keys: []
power_sources:
  - source_key: "{{power_source_key}}"
    category_key: "{{power_source_category_key}}"
    summary: "{{power_source_summary}}"
capabilities:
  - capability_key: "{{capability_key}}"
    category_key: "{{capability_category_key}}"
    summary: "{{capability_summary}}"
restrictions:
  - restriction_key: "{{faction_restriction_key}}"
    category_key: "{{faction_restriction_category_key}}"
    law_id: null
    summary: "{{faction_restriction_summary}}"
content_secret_ids: []
initial_state:
  effective_date: null
  headquarters_location_id: null
  territorial_presence:
    - kingdom_id: null
      region_id: null
      settlement_id: null
      location_id: null
      route_id: null
      presence_type_key: "{{territorial_presence_type_key}}"
      intensity: null
      visibility_key: "{{territorial_presence_visibility_key}}"
      foundation: "{{territorial_presence_foundation}}"
  institutional_relations:
    - relation_key: "{{institutional_relation_key}}"
      target_faction_id: "{{target_faction_id}}"
      relation_type_key: "{{institutional_relation_type_key}}"
      stance_key: "{{institutional_stance_key}}"
      trust: null
      hostility: null
      obligation: "{{institutional_obligation}}"
      foundation: "{{institutional_relation_foundation}}"
      origin_event_id: null
      visibility_key: "{{institutional_relation_visibility_key}}"
      initial_date: null
      symmetric: null
  institutional_metrics:
    influence: null
    cohesion: null
    legitimacy: null
  treasury:
    money:
      amount: null
      currency_key: null
deferred_decisions:
  - "{{deferred_decision}}"
---

> **Aviso de template:** este arquivo não é conteúdo real. Ele segue o [contrato de sociedade, instituições e lei](../../../../docs/world/schemas/SOCIETY_INSTITUTIONS_AND_LAW_ENTITIES.md). Placeholders são proibidos em conteúdo `approved`; membros, ocupantes, professores e alunos atuais não pertencem a este arquivo, e escolas mágicas são entidades `magic_school.*` separadas.

# Visão geral

{{overview}}

## Fundação, finalidade e ideologia

{{foundation_purpose_and_ideology}}

## Pertencimento

{{membership_lore}}

## Estrutura e cargos

{{structure_and_roles}}

## Autoridade e decisões

{{authority_and_decisions}}

## Políticas e sucessão

{{policies_and_succession}}

## Sede e presença inicial

{{headquarters_and_initial_presence}}

## Capacidades, poder e restrições

{{capabilities_power_and_restrictions}}

## Relações institucionais

{{institutional_relations_lore}}

## Religião, cultura, família e profissões

{{cross_domain_relations}}

## Magia

{{magic_relations}}

## Segredos institucionais

{{institutional_secrets}}

## História

{{history}}

## Observações editoriais

{{editorial_notes_text}}
