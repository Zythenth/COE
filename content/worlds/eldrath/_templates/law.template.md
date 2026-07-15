---
schema_version: "1.0.0"
id: "law.{{law_slug}}"
name: "{{law_name}}"
content_status: draft
tags: []
aliases: []
summary: "{{summary}}"
references: []
art: []
notes: "{{editorial_notes}}"
formal_title: "{{formal_title}}"
law_category_key: "{{law_category_key}}"
jurisdiction:
  level_key: "{{jurisdiction_level_key}}"
  entity_id: "{{jurisdiction_entity_id}}"
legislative_authority_id: "faction.{{legislative_authority_slug}}"
enforcement_authority_ids:
  - "faction.{{enforcement_authority_slug}}"
adjudication_authority_ids:
  - "faction.{{adjudication_authority_slug}}"
promulgation_date: null
effective_date: null
end_date: null
initial_legal_status: "{{initial_legal_status_key}}"
regulated_behavior:
  subject_keys:
    - "{{regulated_subject_key}}"
  action_key: "{{regulated_action_key}}"
  object_keys:
    - "{{regulated_object_key}}"
  object_entity_ids: []
  magic_tag_keys: []
  context_keys: []
subject_rules:
  - subject_key: "{{subject_rule_key}}"
    entity_category_keys: []
    condition_keys: []
object_rules:
  - object_key: "{{object_rule_key}}"
    entity_category_keys: []
    entity_ids: []
    magic_tag_keys: []
    condition_keys: []
conditions:
  - condition_key: "{{legal_condition_key}}"
    subject_key: "{{condition_subject_key}}"
    action_key: "{{condition_action_key}}"
    object_key: "{{condition_object_key}}"
    context_keys: []
    condition_text: "{{condition_text}}"
    exception_keys: []
    consequence_rule_keys: []
normative_rules:
  - rule_key: "{{normative_rule_key}}"
    normative_type_key: "{{normative_type_key}}"
    subject_keys: []
    action_key: "{{normative_action_key}}"
    object_keys: []
    context_keys: []
    condition_keys: []
    exception_keys: []
    sanction_keys: []
    editorial_text: "{{normative_editorial_text}}"
exceptions:
  - exception_key: "{{legal_exception_key}}"
    scope_rule_keys: []
    subject_keys: []
    condition_keys: []
    authority_id: null
    summary: "{{legal_exception_summary}}"
licenses:
  - license_key: "{{license_key}}"
    editorial_name: "{{license_name}}"
    issuing_authority_id: "faction.{{license_issuing_authority_slug}}"
    scope_rule_keys: []
    eligibility_condition_keys: []
    validity_rule_keys: []
    suspension_condition_keys: []
sanctions:
  - sanction_key: "{{sanction_key}}"
    category_key: "{{sanction_category_key}}"
    trigger_rule_keys: []
    condition_keys: []
    fine:
      money:
        amount: null
        currency_key: null
    restitution:
      restitution_type_key: null
      money:
        amount: null
        currency_key: null
      quantity:
        value: null
        unit_key: null
      obligation_key: null
    confiscation:
      target_category_keys: []
      target_entity_ids: []
    duration:
      value: null
      unit_key: null
    notes: null
precedence:
  - target_law_id: "{{precedence_target_law_id}}"
    relation_key: "{{precedence_relation_key}}"
    scope_keys: []
    foundation: "{{precedence_foundation}}"
replaced_law_ids: []
basis:
  basis_keys:
    - "{{legal_basis_key}}"
  event_ids: []
  summary: "{{legal_basis_summary}}"
initial_state:
  institutional_positions:
    - faction_id: "faction.{{institutional_position_faction_slug}}"
      position_key: "{{institutional_position_key}}"
      foundation: "{{institutional_position_foundation}}"
      visibility_key: "{{institutional_position_visibility_key}}"
      initial_date: null
public_visibility_key: "{{public_visibility_key}}"
publication_methods:
  - method_key: "{{publication_method_key}}"
    authority_id: null
    location_ids: []
    summary: "{{publication_method_summary}}"
deferred_decisions:
  - "{{deferred_decision}}"
---

> **Aviso de template:** este arquivo não é conteúdo real. Ele segue o [contrato de sociedade, instituições e lei](../../../../docs/world/schemas/SOCIETY_INSTITUTIONS_AND_LAW_ENTITIES.md). Placeholders são proibidos em conteúdo `approved`; `content_status` e `initial_legal_status` são estados diferentes.

# Visão geral

{{overview}}

## Título, promulgação e vigência

{{title_promulgation_and_effectiveness}}

## Jurisdição e autoridades

{{jurisdiction_and_authorities}}

## Comportamento regulado

{{regulated_behavior_lore}}

## Obrigações, permissões, proibições e restrições

{{normative_rules_lore}}

## Condições, exceções e licenças

{{conditions_exceptions_and_licenses}}

## Sanções

{{sanctions_lore}}

## Precedência, substituição e revogação

{{precedence_replacement_and_repeal}}

## Apoio e oposição institucionais iniciais

{{initial_institutional_positions}}

## Publicação e visibilidade

{{publication_and_visibility}}

## Fundamento e história

{{basis_and_history}}

## Observações editoriais

{{editorial_notes_text}}
