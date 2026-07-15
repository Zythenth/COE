# NPCs persistentes — contrato editorial

**Versão do contrato especializado:** 1.0.0

**Contrato comum:** [CONTENT_SCHEMA.md](../CONTENT_SCHEMA.md), versão 1.0.0

**Estado:** contrato de NPC concluído; template disponível; NPCs reais não iniciados.

Este documento especializa o contrato editorial comum para NPCs persistentes. Ele define representação autoral, propriedade canônica, estruturas incorporadas, estado inicial, limites de percepção e validação manual. Não é schema executável, JSON Schema, DSL, código, save, entidade real ou lore de Eldrath.

Em caso de conflito, [Base/GDD.md](../../../Base/GDD.md), versão 1.3, permanece a fonte canônica.

## 1. Objetivo

Representar cada pessoa persistente como uma identidade estável, localizada, relacionável, capaz de perceber, conhecer, acreditar, lembrar, formar objetivos, decidir, mudar e permanecer consultável na história.

O contrato integra:

- identidade, origem, cultura, idioma, religião e aparência;
- personalidade, valores, necessidades, emoções, atributos e competências;
- saúde, inventário, dinheiro, patrimônio, propriedade e proveniência;
- família, facções, cargos, profissão, emprego e compromissos;
- afinidade, capacidade, aprendizagem e domínio mágico;
- objetivos, medos, segredos, conhecimento, crenças, suspeitas e memórias;
- relações direcionais, prestígio, reputação e rotina;
- ciclo de vida, promoção de agregado, Utility AI e resistência à influência;
- percepção limitada, visibilidade, estado inicial e estado da campanha.

## 2. Escopo, limites e dependências

O arquivo de NPC descreve perfil autoral e sementes estruturadas do estado inicial. Ele não é reescrito a cada tick e não armazena o estado atual de uma campanha.

Dependências editoriais:

1. [contrato editorial comum](../CONTENT_SCHEMA.md);
2. [entidades fundamentais](FOUNDATIONAL_ENTITIES.md), para calendário, cultura, idioma, reino, unidades e moedas;
3. [geografia](GEOGRAPHY_ENTITIES.md), para nascimento, residência, localização, trabalho e rotina;
4. [economia material](MATERIAL_ECONOMY_ENTITIES.md), para profissão, dinheiro, quantidade, recurso, item e instância futura;
5. [intervenção, percepção e conhecimento](INTERVENTION_PERCEPTION_AND_KNOWLEDGE.md), para causalidade e metaconhecimento;
6. [sociedade, instituições e lei](SOCIETY_INSTITUTIONS_AND_LAW_ENTITIES.md), para religião, família, facção, cargo e legalidade;
7. [sistema mágico](MAGIC_SYSTEM_ENTITIES.md), para afinidade, aprendizagem, magia, ritual, efeito e artefato;
8. [criaturas, saúde e doenças](CREATURE_HEALTH_AND_DISEASE_ENTITIES.md), para espécie, anatomia, doença, condição e diagnóstico.

Este contrato não cria NPCs, famílias, relações reais, objetivos reais, eventos, rumores, assets, pastas adicionais, fórmulas de decisão, validação automatizada ou implementação.

## 3. Termos

- **Perfil estático:** identidade, origem, capacidades-base e demais fatos autorais que não representam o valor atual da campanha.
- **Estado inicial:** sementes mutáveis copiadas ao save quando a campanha é criada.
- **Estado da campanha:** valores atuais e mudanças posteriores, pertencentes ao save.
- **Subregistro incorporado:** registro identificável dentro do NPC ou do save, sem arquivo próprio.
- **NPC-semente:** NPC escrito manualmente com perfil e vínculos iniciais.
- **NPC persistente:** pessoa gerada ou promovida com identidade e histórico próprios.
- **População agregada:** pessoas sem simulação individual contínua.
- **NPC histórico:** pessoa morta, desaparecida ou retirada, ainda consultável.
- **NPC lendário:** estado derivado de influência histórica, não classificação arbitrária de autoria.
- **Biografia:** prosa editorial de apresentação.
- **Memória:** dado subjetivo com origem, usado pelo NPC.
- **Conhecimento:** fato corretamente conhecido por uma via válida.
- **Crença:** afirmação aceita como verdadeira, correta ou incorreta.
- **Suspeita:** possibilidade considerada sem aceitação plena.
- **Influência:** modificador temporário de pesos da decisão que preserva escolha.

## 4. Identidade, arquivo e IDs

| Aspecto | Regra |
|---|---|
| Formato | Markdown com front matter YAML |
| Diretório futuro | content/worlds/eldrath/npcs/{slug}.md |
| Prefixo principal | npc. |
| Nome de arquivo | {slug}.md, sem repetir o prefixo |
| Versão | schema_version: "1.0.0" |
| Estado ao iniciar | content_status: draft |

O ID do NPC é permanente. Mudança de nome, título, casamento, família, profissão, residência, condição histórica ou condição lendária não muda o ID nem o arquivo.

Subregistros incorporados e registros futuros do save podem usar:

| Registro | Forma previsível |
|---|---|
| objetivo | goal.{npc_slug}.{stable_goal} |
| medo | fear.{npc_slug}.{stable_fear} |
| segredo pessoal | secret.{npc_slug}.{stable_secret} |
| memória | memory.{npc_slug}.{stable_memory} |
| crença ou suspeita | belief.{npc_slug}.{stable_belief} |
| conhecimento | knowledge.{npc_slug}.{stable_knowledge} |
| relação direcionada | relationship.{source_slug}.{target_slug} |

Esses prefixos não criam arquivos nem pastas. Não existem pastas de objetivos, medos, segredos, memórias, crenças, conhecimento, relações, reputações, emoções ou necessidades.

## 5. Propriedade canônica

| Informação | Proprietário canônico | Não deve ser duplicada em |
|---|---|---|
| identidade da pessoa e capacidades individuais | npc.* | creature.* |
| anatomia-base, longevidade e capacidades da espécie | creature.* | NPC como cópia integral |
| identidade e tradição familiar | family.* | NPC |
| pertencimento familiar e parentesco concreto | NPC e relações direcionais | family.member_ids |
| estrutura, cargos e autoridade institucional | faction.* | NPC |
| afiliação e cargo inicial de uma pessoa | npc.initial_state.faction_affiliations | faction.member_ids ou faction.roles |
| definição de profissão | profession.* | cargo, competência ou emprego |
| profissão e emprego iniciais | npc.initial_state.occupational_state | profession.* |
| definição de item | item.* | inventário do NPC |
| cópia material de item | item_instance no save | item.* ou arquivo do NPC |
| definição e identidade de artefato | artifact.* | item comum |
| definição de magia ou ritual | spell.* ou ritual.* | NPC |
| domínio individual | NPC e save | definição da magia |
| definição de doença | disease.* | NPC |
| instância de doença e condição atual | initial_state e depois save | disease.* |
| verdade global | entidades e estado verdadeiro | crença |
| conhecimento, crença, suspeita e memória individuais | NPC e save | biografia ou segredo |
| membros de família ou facção | consulta dos NPCs | listas inversas manuais |
| causa real da Intervenção do Arquiteto | metadado restrito do save | qualquer dado diegético do NPC |

## 6. Perfil, estado inicial, campanha e derivados

### 6.1 Perfil estático

Pode definir:

- autoria e categoria de origem;
- identidade e nascimento;
- origem social e geográfica;
- espécie ou tipo;
- culturas, idiomas e relações religiosas iniciais de perfil;
- aparência-base e características identificadoras;
- personalidade, traços, valores e sensibilidades de necessidades;
- atributos-base, competências-base e capacidades perceptivas;
- perfil mágico individual e resistência-base à influência;
- biografia, voz, conflitos internos e sementes narrativas.

### 6.2 Estado inicial

Todo campo mutável fica agrupado sob initial_state. Ele pode semear:

- localização, residência, estado de vida e estágio de vida;
- famílias, facções, cargos, profissões, emprego e compromissos;
- satisfação de necessidades e emoções;
- modificadores de atributos e progresso de competências;
- saúde, condições, diagnósticos e prognósticos conhecidos;
- dinheiro, recursos, inventário, propriedade, dívidas, renda e despesas;
- domínio mágico, magias e rituais conhecidos;
- objetivos, medos, segredos, conhecimento, crenças, suspeitas e memórias;
- relações, prestígio, reputações e rotina.

### 6.3 Estado da campanha

Depois da inicialização, o save possui os valores atuais, eventos, mudanças, influências, tarefas, efeitos, inventário materializado, propriedade, memória, conhecimento, relações e histórico. O arquivo autoral não é atualizado a cada tick.

### 6.4 Derivados

Idade, urgência de necessidade, valor efetivo de atributo, condição geral de saúde, nível abstrato de riqueza, tipos de relação, posição lendária, listas inversas, legalidade efetiva e demais agregações são calculados. Não são fontes manuais concorrentes.

## 7. Estruturas compartilhadas do NPC

### 7.1 Fonte

Todo registro que exige origem usa uma estrutura compatível com:

~~~yaml
source:
  source_type_key: null
  source_entity_id: null
  source_subrecord_id: null
  source_event_id: null
  source_description: null
~~~

O tipo e ao menos uma referência ou descrição estruturada precisam ser suficientes para explicar a origem. Prosa solta não substitui a fonte.

### 7.2 Visibilidade

Registros sensíveis usam:

~~~yaml
visibility:
  classification_key: null
  self_awareness_key: null
  disclosure_condition_keys: []
~~~

classification_key distingue ao menos public, private, secret e system_restricted. self_awareness_key distingue known, suspected e unknown para o próprio NPC. Conhecedores externos são derivados dos registros de conhecimento, crença, suspeita, percepção e comunicação; não são mantidos como lista inversa.

### 7.3 Condição editorial

Objetivos, rotina, compromissos e outros registros podem usar condições editoriais:

~~~yaml
condition:
  condition_key: null
  condition_type_key: null
  subject_id: null
  observed_property_key: null
  operator_key: null
  number_value: null
  boolean_value: null
  key_value: null
  entity_id_value: null
  quantity_value: null
  reference_ids: []
  description: null
~~~

Exatamente uma forma de valor é usada quando o operador exigir valor. Esta estrutura documenta intenção e dados; não é DSL nem expressão executável.

## 8. Categorias de simulação e autoria

simulation_profile separa:

- origin_category_key: seed, generated_persistent ou promoted_from_aggregate;
- initial_simulation_category_key: seed ou persistent para arquivos completos;
- promotion_provenance: exigida quando a origem for promoted_from_aggregate.

Aggregate é nível de simulação sem arquivo completo. Historical é estado de ciclo de vida preservado no save. Legendary é derivado de impacto histórico. A categoria de origem nunca é sobrescrita porque o NPC morreu, desapareceu, foi retirado ou se tornou lendário.

Um NPC completo só existe quando possui relevância persistente. Não se cria ficha para preencher contagem.

## 9. Identidade, nomes, nascimento, origem e idade

identity contém:

- primary_name inicial;
- former_names, nicknames e titles, cada um com chave local, forma exibida, período ou motivo quando aplicável;
- pronouns estruturados;
- birth;
- creature_id;
- social_origin;
- geographic_origin_ids;
- identifying_features.

birth contém calendar_id, date, place_id, precision_key, earliest_possible_date, latest_possible_date e source. precision_key distingue data exata, estimada, intervalo ou desconhecida.

Idade cronológica nunca é armazenada como número fixo junto da data. Ela é derivada da data atual do mundo, data de nascimento e calendário. Idade aparente inicial pode existir em base_appearance porque é observação de aparência, não idade cronológica.

## 10. Espécie, cultura, idioma e religião

creature_id, quando aplicável, referencia creature.* e identifica espécie ou tipo. O NPC registra variações individuais; não existe creature.* concorrente para o mesmo indivíduo.

cultural_affiliations permite múltiplas culturas, cada uma com culture_id, affiliation_key, intensity de 0 a 100, source e visibility. Nenhuma cultura determina personalidade, moralidade, inteligência, agressividade, profissão, lealdade ou opinião política.

language_proficiencies usa language_id, speaking, comprehension, reading e writing em 0 a 100, source e visibility. Idiomas não são inferidos apenas por cultura.

religion_relations usa religion_id, relation_key, commitment de 0 a 100, source e visibility. Um NPC pode seguir, rejeitar, reinterpretar ou mudar de relação com uma tradição. Doutrina religiosa e crença pessoal permanecem distintas.

## 11. Aparência

base_appearance registra traços relativamente estáveis:

- apparent_age_key;
- build_key;
- face, hair, eyes e skin;
- marks;
- identifying_features;
- individual_variations.

initial_state.appearance_state pode semear roupa, sujeira, ferimentos visíveis, disfarce, envelhecimento já ocorrido, transformação, efeitos mágicos e equipamento visível. Depois da inicialização, a aparência atual pertence ao save. Descrição estética só vira mecânica quando houver efeito estruturado.

Retrato e outros assets são opcionais.

## 12. Personalidade, traços, moralidade e valores

### 12.1 Eixos

personality.axes usa exatamente dez chaves estáveis, na escala de -100 a 100:

| Chave | -100 | 100 |
|---|---|---|
| boldness | cautela | ousadia |
| empathy | egoísmo | empatia |
| ambition | contentamento | ambição |
| discipline | espontaneidade | disciplina |
| sociability | reserva | sociabilidade |
| suspicion | confiança | suspeita |
| spirituality | pragmatismo | espiritualidade |
| curiosity | tradição | curiosidade |
| honesty | dissimulação | honestidade |
| aggression | pacifismo | agressividade |

Personalidade muda lentamente, não é emoção e não determina ação sozinha.

### 12.2 Traços

Cada personality.traits contém trait_key, intensity de 0 a 100, source, conceptual_effects, relevant_condition_keys e notes. Cada efeito conceitual declara effect_key, affected_factor_keys e direction_key. Lista de adjetivos sem consequência sistêmica é inválida.

### 12.3 Moralidade

Não existe alinhamento único, moral_score, good, evil, hero ou villain. Moralidade emerge de valores, crenças, objetivos, ações, relações, contexto, consequências e reputações.

### 12.4 Valores

value_profile usa value_key e weight de 0 a 100. Chaves canônicas:

- family, power, wealth, knowledge, faith;
- freedom, duty, tradition, justice, survival;
- community, prestige, magic, truth, love.

Cada entrada pode registrar source e condition_keys. Extensão exige chave estável, justificativa documental e compatibilidade com o vocabulário futuro. Um NPC não recebe todos os valores com o mesmo peso.

## 13. Necessidades e emoções

### 13.1 Necessidades

need_profile define baseline e sensitivity individuais, ambos em 0 a 100, para:

- food, rest, safety, health;
- belonging, affection, autonomy, status;
- purpose, wealth, knowledge, faith.

initial_state.needs registra satisfaction de 0 a 100, source, evaluated_at e notes. Urgência é derivada; satisfação atual pertence ao save. Necessidade baixa amplia opções corretivas, mas não garante ação.

### 13.2 Emoções

initial_state.emotions usa emotion_key entre fear, anger, sadness, hope, guilt, shame, pride, affection e stress. Cada registro contém intensity de 0 a 100, trigger, target_id, origin_event_id, origin_memory_id, started_at, decay_profile_key, reinforcement_keys e visibility.

Emoção é transitória, não personalidade e não garante ação.

## 14. Atributos, competências e percepção

### 14.1 Atributos

attributes usa attribute_key e base_value de 0 a 100 para vigor, agility, intellect, presence, will, perception e magical_attunement.

initial_state.attribute_modifiers registra modifier_key, attribute_key, operation, value, persistence_key, duration, source e condition_keys. Modificador pode ser persistente ou temporário no estado. effective_value é sempre derivado e não é escrito manualmente.

### 14.2 Competências

competencies usa competency_key, base_level de 0 a 100, source, specializations, certifications e learning_evidence. Chaves iniciais incluem healing, combat, diplomacy, commerce, leadership, investigation, stealth, agriculture, smithing, writing, theology, alchemy, runes, teaching, navigation e administration.

initial_state.competency_progress registra competency_key, initial_experience, last_practice e source. Profissão não é competência; cargo não é profissão; nenhuma pasta de competências é criada.

### 14.3 Percepção limitada

perception_profile registra sentidos, acuity_base, attention_baseline, awareness_capabilities, limitation_keys, detection_condition_keys e magical_perception. initial_state.perception_state pode semear consciência, atenção e limitações transitórias.

Capacidade perceptiva não concede conhecimento. Presença, alcance, condição, atenção, evidência e comunicação continuam necessários.

## 15. Saúde

initial_state.health contém sementes estruturadas de:

- injuries;
- disease_instances;
- disabilities;
- pain;
- fatigue;
- intoxications;
- immunities;
- active_magic_effects;
- true_prognosis;
- known_diagnoses;
- known_prognoses.

Cada ocorrência registra chave local, fonte, início, gravidade ou intensidade, referências aplicáveis, evidências, visibilidade e demais campos definidos pelo contrato de saúde.

disease_instances referencia disease_id e registra estágio, gravidade, sintomas, exposição e fonte iniciais. Não duplica a definição disease.*.

known_diagnoses e known_prognoses registram observador, hipótese, confiança, evidências, fonte, data e visibilidade. Podem estar errados. Diagnóstico conhecido não substitui o estado verdadeiro.

overall_condition é derivada dos componentes. Ferimentos, doenças, dor, fadiga, intoxicações, imunidades e efeitos atuais pertencem ao save após a inicialização.

## 16. Família, facções, profissão, cargo e emprego

### 16.1 Família e parentesco

initial_state.family_affiliations usa family_id, affiliation_key, source, effective_date e visibility. A família não mantém member_ids.

Parentesco concreto usa relationship_records com kinship_facts. Tipos como guardian, child, sibling, spouse, partner, adopter, adopted, tutor e dependent exigem par factual compatível quando aplicável. Mapas ad hoc como mother: npc.example são proibidos.

### 16.2 Facções e cargos

initial_state.faction_affiliations registra:

- faction_id;
- role_key ou null;
- membership_state_key;
- start_date;
- entry_method_key;
- commitment de 0 a 100;
- source;
- visibility.

role_key precisa existir em faction.roles. A facção não mantém membros, líder ou ocupantes atuais.

### 16.3 Profissão e trabalho

initial_state.occupational_state distingue:

- primary_profession;
- secondary_professions;
- employments.

Cada vínculo profissional usa profession_id, rank_key, experience_source e visibility. Cada emprego usa employment_key, profession_id, employer_id, workplace_location_id, faction_role_key opcional, schedule_keys, compensation, employment_state_key, start_date e source.

Profissão usa profession.*. Cargo usa faction role_key. Emprego é vínculo atual. Tarefa é ação. Competência é capacidade. Nenhum desses conceitos substitui outro.

## 17. Dinheiro, riqueza, inventário, propriedade e proveniência

### 17.1 Patrimônio inicial

initial_state.material_state separa:

- money_balances;
- resource_holdings;
- inventory_seeds;
- artifact_holdings;
- property_interests;
- debts;
- contracts;
- income_sources;
- expense_commitments.

Não existe wealth: 18 como única fonte. Um nível de riqueza pode ser derivado desses componentes.

### 17.2 Inventário

Cada inventory_seed contém inventory_seed_key, item_id, quantity, quality_key, placement_key, storage_location_id, container_seed_key, sentimental, provenance e notes.

Ao iniciar a campanha:

- item comum gera item_instance;
- recurso permanece quantidade fungível;
- artefato preserva sua identidade artifact.*;
- item sentimental continua item_instance com metadado apropriado.

Inventário atual pertence ao save. Um artefato não é duplicado como item comum.

### 17.3 Propriedade

property_interests distingue physical_possession, recognized_ownership, shared_ownership, custody, loan, debt e claim. Cada registro aponta para um inventory_seed_key, artifact_id, location_id, resource_holding_key ou contract_key, registra contraparte, fração quando aplicável, source, effective_date e visibility.

Posse física não prova propriedade. Mudanças posteriores geram eventos. O mesmo objeto não pode existir em dois inventários.

Proveniência relevante registra source, previous_owner_ids, origin_event_id, acquisition_method_key e notes. Não se inventa histórico apenas para preencher o campo.

## 18. Magia, afinidade e domínio

magic_profile pode definir:

- sensitivity, capacity, control, general_resistance e corruption_tolerance, todos em 0 a 100;
- affinities por magic_school_id e valor de 0 a 100;
- learning_traditions;
- block_keys;
- undiscovered_potential, com visibilidade system_restricted quando o NPC não o conhece;
- influence_resistance_profile.

Afinidade não concede magia. Acesso pode depender de ensino, pesquisa, item, artefato, religião, facção, lei, oportunidade ou evento.

initial_state.magic_mastery contém um spell_id ou ritual_id, nunca ambos, e:

- stage_key;
- progress e mastery de 0 a 100;
- stability de 0 a 100;
- source obrigatória;
- teacher_npc_id quando aplicável;
- started_at e last_practice_at;
- known_risk_keys;
- personal_variants;
- perceived_legality;
- visibility.

Não existe lista simples known_spells. A definição real permanece em spell.* ou ritual.*. Estágios seguem o contrato mágico: unknown, theoretical, studying, unstable, usable, mastered, magisterial e personal_variant.

## 19. Objetivos e condições

initial_state.goals usa IDs goal.* incorporados. Cada objetivo contém:

- id e owner_npc_id;
- goal_type_key e structured_description;
- priority de 0 a 100;
- source;
- state_key;
- deadline;
- success_conditions e failure_conditions;
- steps;
- required_resources;
- ally_npc_ids e obstacle_entity_ids;
- related_secret_id;
- initial_progress de 0 a 100;
- related_event_ids;
- visibility.

Estados permitidos: potential, considered, active, blocked, suspended, completed, abandoned, failed e replaced.

structured_description separa action_key, subject_id, target_entity_ids, outcome_key e editorial_summary. Condições usam a estrutura editorial da seção 7.3 e não formam uma DSL.

Todo objetivo possui origem. Objetivos atuais e mudanças posteriores pertencem ao save.

## 20. Medos e segredos

### 20.1 Medos

initial_state.fears usa IDs fear.* e registra category_key, target_entity_ids, theme_key, intensity de 0 a 100, source, trigger_keys, evidence_ids, preferred_response_keys, coping_strategy_keys, related_memory_ids e visibility.

Respostas podem incluir flee, avoid, attack, seek_protection, control e rationalize. Medo não garante resposta.

### 20.2 Segredos

initial_state.secrets usa IDs secret.* e registra:

- owner_npc_id;
- structured_truth;
- involved_entity_ids;
- origin_event_id;
- evidence_ids;
- severity de 0 a 100;
- exposure_risk de 0 a 100;
- expected_consequences;
- initial_state_key;
- visibility.

structured_truth separa sujeito, propriedade, valor, referências e resumo editorial. O segredo não mantém lista de conhecedores ou suspeitos. Essas direções são derivadas de knowledge_records e belief_records.

Segredos pertencentes primariamente a evento, facção ou família serão definidos pelos contratos correspondentes; o NPC apenas referencia quando aplicável.

## 21. Conhecimento, crença e suspeita

### 21.1 Conhecimento

initial_state.knowledge_records usa IDs knowledge.* e contém owner_npc_id, statement, known_content, source, acquired_at, evidence_ids, confidence de 0 a 100, last_confirmed_at, contradictions, perceptual_or_communicated_origin e visibility.

statement separa subject_id, property_key, value estruturado e reference_ids. Conhecimento precisa corresponder ao fato verdadeiro, mas nunca recebe acesso ao estado global. Biografia não concede conhecimento.

### 21.2 Crença e suspeita

initial_state.belief_records usa IDs belief.*. epistemic_state_key distingue belief e suspicion. Cada registro contém subject, believed_value, confidence de 0 a 100, source, evidence_ids, acquired_at, reinforcement_ids, contradiction_ids e visibility.

Crença não copia a verdade global. Suspeita não é conhecimento. Uma mentira é uma comunicação que o emissor sabe ser falsa; ela não exige prefixo ou pasta própria nesta fase.

## 22. Memória e biografia

initial_state.memories usa IDs memory.* e contém:

- owner_npc_id;
- event_id ou situation_key;
- perceived_version;
- origin_type_key e source;
- participant_ids;
- location_id e occurred_at;
- emotion_records;
- valence;
- salience e certainty de 0 a 100;
- tags;
- related_secret_id;
- last_recalled_at;
- relationship_effects;
- forgetting_rate;
- visibility.

Toda memória possui origem em experiência, percepção, comunicação, tradição recebida, documento, magia válida ou outra via registrada. Ela não copia automaticamente o evento verdadeiro.

Biografia fica no corpo Markdown. É apresentação editorial e não entra em decisão, conhecimento ou memória sem registro estruturado correspondente. Não se copia toda a biografia para memórias.

## 23. Relações direcionais e conteúdo sensível

initial_state.relationship_records usa IDs relationship.{source_slug}.{target_slug}. Cada registro contém:

- source_npc_id e target_npc_id;
- familiarity de 0 a 100;
- trust, affection, respect e attraction de -100 a 100;
- fear, resentment, loyalty e dependency de 0 a 100;
- debt como valor assinado e unidade ou moeda quando aplicável;
- derived_type_keys;
- kinship_facts;
- origin_event_ids;
- relevant_memory_ids;
- last_initial_interaction_at;
- visibility.

A relação A→B não representa B→A. Dimensões emocionais nunca são forçadas a ser simétricas.

Fatos objetivos de parentesco, tutela, mentoria, autoridade e dívida precisam de pares compatíveis quando aplicável. O validador futuro verificará incompatibilidades; o contrato não duplica automaticamente o registro inverso.

Romance permanece não explícito. attraction e romance são proibidos quando qualquer participante estiver abaixo da idade adulta definida pelo mundo. Crianças priorizam cuidado, saúde, educação, vínculo, desenvolvimento e proteção.

## 24. Prestígio e reputação

initial_state.prestige registra value de 0 a 100, causes, effective_date e visibility. Prestígio representa visibilidade, reconhecimento e posição social geral.

initial_state.reputations é contextual. Cada registro contém reputation_key, audience_type_key, audience_entity_id, context_key, value, scale_key, confidence, source, cause_event_ids, effective_date e visibility.

Audiências podem ser assentamento, facção, família, religião, profissão, cultura ou outro grupo aprovado. Não existe reputação universal simples. A escala final de reputação permanece controlada pelo vocabulário futuro e precisa ser declarada por scale_key.

## 25. Rotina e compromissos

### 25.1 Rotina

initial_state.routine_blocks registra routine_key, period_key, time_window, intended_action_key, location_id, priority de 0 a 100, frequency, conditions, flexibility de 0 a 100, interruptible e related_goal_id.

Rotina é plano flexível. Necessidades, emergências, objetivos, ordens, viagens e eventos podem interrompê-la. A tarefa atualmente executada pertence ao save.

### 25.2 Compromissos

initial_state.commitments registra commitment_key, commitment_type_key, involved_entity_ids, source, effective_date, deadline, obligation_keys, consequence_keys, related_goal_ids e visibility.

Tipos podem representar promessa, contrato, dívida, ordem, dever ou responsabilidade. Compromisso influencia decisão sem garantir ação. Contratos materiais e financeiros continuam referenciando as estruturas de material_state.

## 26. Utility AI e influência do Arquiteto

O contrato não implementa Utility AI. Ele fornece personalidade, valores, necessidades, emoções, objetivos, relações, conhecimento, crenças, memórias, risco percebido, oportunidade, compromissos e resistência.

decision_profile pode registrar risk_tolerance, change_resistance, influence_resistance_baseline e protected_value_keys, todos como capacidades conceituais ou valores-base de 0 a 100. Não contém fórmula, peso técnico final, ação escolhida ou configuração do motor.

Influência atual nunca fica no arquivo estático nem em initial_state. Ela pertence ao save, possui intensidade, duração, alvo, resistência, resultado e evento, pode falhar e não garante decisão.

O NPC nunca conhece automaticamente o usuário ou a causa real da influência. Compulsão permanece fora do MVP.

## 27. Ciclo de vida, histórico e legado

O contrato permite representar nascimento, infância, aprendizagem, entrada em profissão, relações, mudança de residência, maturidade, envelhecimento, aposentadoria, desaparecimento, morte e legado.

birth é histórico no perfil. initial_state.lifecycle_state pode semear life_state_key, development_stage_key, residence_start_date e retirement_state_key. Mudanças posteriores são eventos.

NPC morto, desaparecido, retirado ou histórico permanece consultável. Eventos, relações, memórias coletivas, propriedade, cargos anteriores, legado e referências não são apagados.

legendary é estado derivado de alcance e influência histórica. O arquivo não recebe um booleano arbitrário is_legendary e não é reescrito quando o limiar for atingido.

## 28. Promoção de população agregada

Uma pessoa agregada pode ser promovida quando adquirir relevância. A promoção futura cria ID estável, identidade, contexto, localização, vínculos, estado coerente, evento ou origem e proveniência.

promotion_provenance registra aggregate_source_key, origin_context_id, promotion_event_id, generated_at e source. A promoção não grava automaticamente um novo arquivo no pacote estático; o formato persistente e a política de promoção editorial permanecem adiados.

## 29. Visibilidade, lore e assets

Informação pública, privada, secreta e restrita ao sistema permanece distinguível. Conhecimento do próprio NPC, conhecimento de outros e visão onisciente são derivados por perspectiva e registros, não pela simples presença de um campo no arquivo.

O corpo Markdown pode conter:

- Biografia;
- Aparência narrativa;
- Conflito interno;
- Voz e comportamento observável;
- Contexto;
- Sementes narrativas;
- Observações editoriais.

Prosa não substitui objetivos, memórias, relações, conhecimento, inventário, saúde, magia, localização ou afiliações.

art é opcional. Ausência de retrato não invalida o NPC. Este contrato não cria prompt, placeholder gráfico ou asset.

## 30. Campos derivados

Não são armazenados manualmente como fonte:

- idade cronológica;
- valores efetivos dos atributos;
- urgência das necessidades;
- condição geral de saúde;
- riqueza agregada;
- propriedade atual depois da inicialização;
- tipos derivados de relação;
- membros de família e facção;
- titulares atuais consultados pela instituição;
- legalidade efetiva;
- prestígio e reputação atuais depois da inicialização;
- ações e tarefas atuais;
- influências ativas;
- condição histórica e lendária derivadas;
- conhecedores e suspeitos de um segredo.

## 31. Invariantes

1. O ID do NPC nunca depende do nome atual.
2. Idade é derivada da data e do calendário.
3. Estado atual pertence ao save.
4. Personalidade não é emoção.
5. Moralidade não é um número simples.
6. Necessidade não garante ação.
7. Emoção não garante ação.
8. Valor efetivo de atributo é derivado.
9. Profissão não é competência.
10. Profissão não é cargo.
11. Família não mantém lista manual de membros.
12. Facção não mantém lista manual de membros.
13. Riqueza não é apenas um número abstrato.
14. Inventário atual pertence ao save.
15. Artefato único não pode ser duplicado.
16. Afinidade não concede magia.
17. Magia conhecida possui fonte.
18. Objetivo possui origem.
19. Memória possui origem.
20. Conhecimento possui fonte.
21. Crença não duplica a verdade.
22. Segredo não mantém lista inversa de conhecedores.
23. Relação é direcionada.
24. Fatos recíprocos são compatíveis.
25. Reputação é contextual.
26. Diagnóstico conhecido pode estar errado.
27. Biografia não concede conhecimento.
28. Influência não garante decisão.
29. NPC não conhece o usuário.
30. Pessoa agregada não vira persistente sem promoção.
31. NPC morto ou histórico não perde referências.
32. Ausência de retrato não invalida o NPC.
33. Criança não participa de conteúdo impróprio.
34. Nenhum campo mutável atual fica fora de initial_state.
35. Espécie e NPC não concorrem pela identidade do mesmo indivíduo.
36. Estado histórico ou lendário não apaga a categoria de origem.
37. Conhecimento, crença, suspeita, memória e biografia permanecem distintos.
38. O mesmo objeto não existe em dois inventários.
39. Propriedade, posse, custódia, empréstimo, dívida e reivindicação permanecem distintos.
40. Nenhuma mecânica necessária existe somente na prosa.

## 32. Validação manual

Antes de encaminhar um NPC futuro para revisão:

- validar YAML, campos comuns, schema_version e content_status;
- conferir pasta, prefixo, slug e unicidade do ID;
- confirmar que todos os subregistros incorporados usam IDs previsíveis e únicos;
- validar referências por categoria e ausência de nomes como chaves;
- conferir perfil separado de initial_state;
- procurar qualquer valor atual fora de initial_state;
- conferir nascimento, precisão, calendário e ausência de idade fixa concorrente;
- validar criatura, culturas, idiomas e religiões sem determinismo cultural;
- conferir dez eixos de personalidade na faixa correta;
- validar valores, necessidades, emoções, atributos e competências nas escalas aplicáveis;
- confirmar valor efetivo, urgência, saúde geral e riqueza como derivados;
- validar saúde sem duplicar disease.*;
- conferir família sem member_ids e parentesco por relações;
- conferir facção, role_key, profissão, competência, emprego e tarefa separados;
- validar money, quantity, inventário, item_instance futura, artefato e proveniência;
- confirmar que propriedade e posse não foram confundidas;
- validar magia conhecida com fonte e exatamente um spell_id ou ritual_id;
- conferir objetivos, condições editoriais, estados e origens;
- conferir medos, respostas e memórias relacionadas;
- conferir segredo sem lista de conhecedores;
- validar conhecimento e memória com fonte;
- conferir crença e suspeita sem copiar a verdade global;
- validar relação direcionada, escalas e fatos recíprocos;
- impedir romance ou atração impróprios envolvendo menores;
- conferir prestígio geral e reputações contextuais;
- validar rotina flexível e compromissos sem ação garantida;
- confirmar ausência de influência atual e metaconhecimento;
- confirmar ausência de entidade real, evento, rumor, arte, código, DSL ou schema executável;
- confirmar corpo Markdown coerente e sem mecânica concorrente;
- remover todos os placeholders antes de content_status: approved.

## 33. Decisões adiadas

Permanecem para fases posteriores:

- vocabulários concretos de nomes, títulos, origens, traços e aparência;
- data, calendário, idade adulta e regras de precisão de Eldrath;
- escalas finais de reputação, dívida e experiência;
- catálogo final de competências, traços, condições, rotinas e compromissos;
- fórmulas de necessidade, emoção, atributo, saúde, riqueza, prestígio e Utility AI;
- pesos, normalização, seleção de ações, resistência e influência;
- linguagem executável de condições e validação automatizada;
- formato persistente de NPC promovido, item_instance, saúde, propriedade e histórico;
- regras detalhadas de sucessão, herança, emprego, salário e contratos;
- entidades reais de eventos, rumores, história e conflitos;
- banco de dados, API, interface, código e assets.

## 34. Estado editorial

Este contrato e o template de NPC concluem a subetapa documental de NPCs da Fase 1. Eles não criam as 30 entidades-semente, não materializam as âncoras mencionadas no GDD e não iniciam a Fase 5.

Os contratos de eventos, rumores, história, cadeias causais, conflitos latentes, gatilhos e ameaças monstruosas foram concluídos depois deste contrato. A Fase 1 aguarda auditoria editorial final, consolidação e encerramento explícito.
