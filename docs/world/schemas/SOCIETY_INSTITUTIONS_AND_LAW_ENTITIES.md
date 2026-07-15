# Sociedade, instituições e lei — schemas editoriais

**Versão do contrato especializado:** `1.0.0`

**Contrato comum:** [`CONTENT_SCHEMA.md`](../CONTENT_SCHEMA.md), versão `1.0.0`

**Estado:** contratos de `religion`, `faction`, `family` e `law` concluídos; entidades reais não iniciadas.

Este documento especializa o contrato editorial comum para tradições religiosas, organizações institucionais, grupos familiares e regras jurídicas. Ele define representação autoral, propriedade canônica, referências e validação manual. Não é schema executável, JSON Schema, linguagem de regras, código, conteúdo real ou lore de Eldrath.

Em caso de conflito, [`Base/GDD.md`](../../../Base/GDD.md), versão `1.2`, permanece a fonte canônica. Este contrato integra o GDD sem modificá-lo.

## 1. Escopo e regras compartilhadas

As quatro entidades usam Markdown com front matter YAML, um arquivo por entidade e `schema_version: "1.0.0"`. Todo arquivo novo começa com `content_status: draft` e usa os campos comuns `id`, `name`, `tags`, `aliases`, `summary`, `references`, `art` e `notes` conforme o contrato comum.

| Entidade | Prefixo | Diretório futuro | Arquivo |
|---|---|---|---|
| religião ou tradição religiosa | `religion.` | `content/worlds/eldrath/religions/` | `{slug}.md` |
| facção ou instituição | `faction.` | `content/worlds/eldrath/factions/` | `{slug}.md` |
| família, linhagem ou casa dinástica | `family.` | `content/worlds/eldrath/families/` | `{slug}.md` |
| lei pública reconhecida | `law.` | `content/worlds/eldrath/laws/` | `{slug}.md` |

Regras obrigatórias:

- IDs são estáveis, usam ASCII, minúsculas e `snake_case`; o nome visível nunca é chave.
- Referências entre entidades usam IDs completos. Chaves locais estáveis terminam em `_key` e só são válidas dentro da estrutura que as define.
- Campos estruturados guardam identidade, relações, condições e regras; o corpo Markdown explica contexto e lore sem redefini-los.
- Campo omitido significa opcional ou não aplicável; `null` significa aplicável, porém ainda desconhecido; `[]` afirma ausência conhecida.
- Um arquivo `approved` não pode conter placeholder, referência inexistente, nome usado como chave nem informação mecânica apenas na prosa.
- Conteúdo estático, estado inicial e estado atual da campanha são dimensões diferentes.
- Campos derivados são documentados, mas não armazenados como listas inversas.
- Nenhuma regra depende de IA generativa.

## 2. Propriedade canônica dos dados

| Informação | Proprietário canônico | Não deve ser duplicada em |
|---|---|---|
| doutrina, cosmologia, prática e interpretação religiosa | `religion.*` | facção religiosa, família, lei ou reino |
| organização, cargos, autoridade, política e presença territorial inicial | `faction.*` | religião, família, região, assentamento, local ou rota |
| parentesco conceitual, identidade familiar e regras familiares | `family.*` | facção dinástica, lei ou listas genealógicas manuais |
| parentesco concreto entre pessoas | relações futuras de `npc.*` e eventos | `family.*` |
| regra pública reconhecida e sua jurisdição | `law.*` | reino, região, assentamento, facção, religião ou família |
| afiliação e cargo atuais de uma pessoa | futuro `npc.*` ou estado da campanha | `faction.*` |
| estado jurídico atual depois do início | estado da campanha e eventos | arquivo `law.*` |
| posição territorial inicial de uma facção | `faction.initial_state.territorial_presence` | entidades geográficas |
| vínculo de facção com religião | `faction.religion_ids` | `religion.organization_ids` |
| vínculo de casa política com dinastia | `faction.dynastic_family_id` | lista inversa em `family.*` |
| profissão como atividade econômica | `profession.*` | cargo de facção |

Uma consulta futura pode mostrar a direção inversa, mas não a mantém manualmente. Por exemplo, organizações de uma religião são derivadas das facções que a referenciam; leis de um assentamento são derivadas da jurisdição das leis; instituições ligadas a uma família são derivadas das facções com `dynastic_family_id` correspondente.

## 3. Definição estática, estado inicial, estado atual e derivados

### Definição estática

Pode registrar identidade, origem, propósito, doutrina, tradição, regras, estrutura possível, cargos possíveis, processos decisórios, sucessão conceitual, política de recrutamento, bases históricas e referências estáveis.

### Estado inicial

Quando uma condição mutável precisar semear a campanha, ela fica explicitamente sob `initial_state` ou, no caso jurídico, no campo inequivocamente inicial `initial_legal_status`. O valor é copiado ao criar o save e não representa verdade eterna.

### Estado atual da campanha

O save será proprietário de membros e seguidores atuais, ocupantes de cargos, líder, tesouro, influência, coesão, reputação, propriedades, alianças, conflitos, decisões, herdeiros vivos, reivindicações, aplicação da lei, processos, condenações e demais mutações.

### Campos derivados

Campos derivados são consultas calculadas por referências canônicas. Eles não aparecem nos templates como listas editáveis. Cada contrato abaixo declara suas principais derivações.

## 4. `religion` — tradição de crença

### 4.1 Finalidade e fronteira

`religion.*` representa uma tradição de crença: cosmologia, doutrina, valores, tabus, práticas, ritos, símbolos, concepções sobre vida e morte e diversidade interpretativa. Não representa automaticamente uma organização.

Uma ordem religiosa, templo organizado, sacerdócio institucional, culto organizado ou comunidade com membros, liderança, cargos, tesouro, objetivos, propriedades ou decisões coletivas é `faction.*`. A facção referencia uma ou mais religiões por `religion_ids`. `religion.*` nunca mantém `organization_ids`.

“Culto” segue a mesma regra:

- tradição de crença: `religion.*`;
- organização: `faction.*`;
- ambas as dimensões: duas entidades ligadas da facção para a religião, sem campos duplicados.

### 4.2 Campos

Todos os campos especializados abaixo aparecem no template. Estruturas opcionais usam `null` ou `[]` até serem aplicáveis; conteúdo `approved` preenche os valores exigidos pela entidade sem inventar dados.

| Campo | Estrutura e propriedade |
|---|---|
| `tradition_type_key` | classificação estrutural da tradição |
| `origin` | `description` editorial, `date`, `period_key` e `event_id` de origem |
| `origin_culture_id` | cultura de origem por ID `culture.*` ou `null` |
| `cosmology` | princípios, estrutura do cosmos, relatos de origem e escatologia |
| `sacred_entities_or_principles` | conceitos internos com `principle_key` estável, nome editorial, tipo e função |
| `doctrines` | doutrinas por `doctrine_key`, nome editorial, resumo, centralidade e visibilidade |
| `values`, `virtues` | valores e virtudes por chaves locais estáveis |
| `violations`, `taboos` | pecados, violações e tabus religiosos; não são crimes automaticamente |
| `practices`, `rites` | práticas e ritos, requisitos editoriais e participação |
| `festivals` | festividades por `festival_key` e vínculo opcional com calendário |
| `liturgical_calendar` | `calendar_id` e regras litúrgicas referenciais |
| `sacred_texts` | textos por chave local e `item_id` opcional quando houver definição material |
| `symbols` | símbolos religiosos editoriais; não substituem assets |
| `sacred_object_ids` | IDs `item.*` ou `artifact.*` quando existirem |
| `sacred_location_ids` | IDs `location.*` |
| `funerary_practices` | práticas funerárias por chave |
| `afterlife_conceptions` | concepções de morte e pós-vida por chave |
| `magic_position` | posição geral sobre magia |
| `magic_school_positions` | posições futuras direcionadas a `school.*` |
| `participation_rules` | regras conceituais de participação; não listam participantes |
| `conceptual_organization` | papéis, modelos e tradições organizacionais sem membros, cargos ocupados ou tesouro |
| `internal_diversity` | fontes e eixos de diversidade interna |
| `interpretations` | interpretações por `interpretation_key`, escopo e diferenças doutrinárias |
| `branches` | ramificações internas ainda não modeladas como entidades independentes |
| `ancestor_religion_id` | religião ancestral quando a tradição for uma entidade independente |
| `doctrinal_relations` | relações direcionais com outras `religion.*` |
| `initial_state` | difusão inicial datada, por região ou assentamento, sem lista de seguidores |
| `deferred_decisions` | decisões específicas e delimitadas, nunca `TODO` vago |

`origin.description` e os campos `name` internos são editoriais; chaves e IDs continuam sendo as referências permanentes. Uma ramificação que adquirir identidade autônoma usa outra entidade `religion.*` e aponta `ancestor_religion_id` para a ancestral. A ancestral não mantém lista inversa de descendentes.

### 4.3 Estado inicial e derivados

`initial_state.diffusion` registra `region_id` ou `settlement_id`, `presence_key`, `visibility_key`, data e notas. Exatamente um alvo geográfico é usado por entrada. A estrutura descreve difusão inicial agregada, nunca seguidores individuais.

São derivados:

- organizações religiosas, consultando `faction.religion_ids`;
- regiões associadas, consultando `initial_state.diffusion`;
- tradições descendentes, consultando `ancestor_religion_id`;
- seguidores, líderes religiosos, cargos ocupados e membros, consultando NPCs e o save futuro.

### 4.4 Invariantes

- Religião não possui membros, seguidores completos, líder institucional, exército, propriedades atuais ou tesouro.
- `conceptual_organization` descreve somente modelos e papéis religiosos.
- Doutrina religiosa não é lei; força jurídica exige `law.*` e autoridade competente.
- Relações doutrinárias são direcionais. Reciprocidade só existe quando registrada pelo outro ponto de vista ou derivada por regra futura.
- Uma relação genuinamente simétrica é armazenada uma vez no arquivo cujo ID for lexicograficamente menor; a direção inversa é derivada.

## 5. `faction` — organização institucional

### 5.1 Finalidade e tipos

`faction.*` representa organização capaz de possuir pertencimento, autoridade, estrutura, decisões e capacidades coletivas. Todas as instituições usam a mesma categoria; não se criam pastas separadas para guildas, ordens, academias, cultos, conselhos, casas nobres ou órgãos.

Vocabulário estrutural inicial de `faction_type_key`:

- `noble_house`;
- `guild`;
- `academy`;
- `religious_order`;
- `organized_cult`;
- `council`;
- `army`;
- `merchant_group`;
- `criminal_network`;
- `organized_community`;
- `political_movement`;
- `magic_circle`;
- `research_institution`;
- `government_body`.

Essas chaves não são lore nem entidades.

### 5.2 Campos

| Campo | Estrutura e propriedade |
|---|---|
| `faction_type_key` | tipo estrutural |
| `scope_classification` | booleanos `counts_as_main_faction` e `counts_as_magic_institution` |
| `symbol`, `motto` | identidade editorial |
| `foundation` | data, período e `event_id` de fundação |
| `purpose`, `ideology` | finalidade e ideologia estruturadas |
| `values`, `taboos` | valores e tabus institucionais |
| `founding_objectives` | objetivos fundadores; não são objetivos atuais |
| `membership_criteria` | critérios de pertencimento sem lista de membros |
| `recruitment_policy`, `exit_policy`, `expulsion_policy` | políticas institucionais estáticas |
| `internal_structure` | unidades internas por `unit_key`, finalidade e autoridade |
| `roles` | definições de cargos por `role_key` |
| `decision_processes` | processos, quorum, desempate e participantes por chaves de cargo |
| `succession_rules` | regras institucionais de sucessão, sem ocupantes |
| `internal_authority` | escopos e limites de autoridade |
| `policies` | políticas institucionais; não são leis públicas automaticamente |
| `culture_ids` | culturas associadas |
| `religion_ids` | direção canônica para tradições religiosas |
| `dynastic_family_id` | direção canônica para `family.*` quando for casa política |
| `profession_ids` | profissões associadas; não cargos |
| `magic_school_ids` | referências futuras a `school.*` |
| `power_sources` | fontes estáveis de poder |
| `capabilities` | capacidades institucionais definidas |
| `restrictions` | limites estruturais e legais |
| `content_secret_ids` | segredos de conteúdo por ID futuro, não percepções atuais |
| `initial_state` | sede, presença, relações e valores iniciais sem membros ou titulares |
| `deferred_decisions` | decisões específicas adiadas |

### 5.3 Cargos e profissão

Cada entrada de `roles` contém:

- `role_key` estável;
- `editorial_name`;
- `purpose`;
- `authority`;
- `requirements`;
- `allowed_quantity: { minimum, maximum }`;
- `occupancy_rule`;
- `succession_rule`;
- `decision_process_keys`.

`role_key` pertence à facção e identifica uma posição institucional. Um cargo não vira `profession.*`. Profissão define atividade econômica ou competência ocupacional; cargo define autoridade dentro de uma organização. Requisitos de um cargo podem referenciar `profession.*`, mas não fundem os conceitos.

Ocupantes atuais ou iniciais não aparecem em `roles`. Eles serão ligados por NPCs ou pela inicialização futura do estado.

### 5.4 Processo decisório

Cada `decision_processes` usa `process_key`, finalidade, escopo, `eligible_role_keys`, método, regra de quorum, regra de desempate e regra de registro. Toda chave de cargo precisa existir no mesmo arquivo.

Decisões concretas, propostas, votos, apoiadores, opositores e resultados pertencem a eventos e ao save. `policies` registra somente políticas institucionais definidas; mudanças de política durante a campanha geram eventos.

### 5.5 Estado inicial e relações entre facções

`initial_state` pode conter:

- `effective_date`;
- `headquarters_location_id`;
- `territorial_presence`;
- `institutional_relations`;
- `institutional_metrics`;
- `treasury.money`;
- notas editoriais.

`territorial_presence` é a fonte canônica para presença, atuação, controle ou influência inicial da facção. Cada entrada aponta para exatamente um `kingdom.*`, `region.*`, `settlement.*`, `location.*` ou `route.*` e registra `presence_type_key`, intensidade, visibilidade e fundamento. Entidades geográficas não mantêm a lista inversa.

Uma relação institucional inicial contém:

- `relation_key` local;
- `target_faction_id`;
- `relation_type_key`;
- `stance_key`;
- `trust`;
- `hostility`;
- `obligation`;
- `foundation`;
- `origin_event_id`;
- `visibility_key`;
- `initial_date`;
- `symmetric`.

Relações direcionais ficam no arquivo da facção de origem. Se `symmetric: true`, a entrada é armazenada uma vez no arquivo cujo ID for lexicograficamente menor; a consulta deriva a direção inversa. Relações atuais e alterações posteriores pertencem ao save.

### 5.6 Instituições mágicas

Toda instituição mágica é `faction.*` com tipo e classificação adequados. Pode futuramente referenciar escolas, magias, rituais, artefatos, políticas de ensino e restrições de acesso, sem duplicar esses contratos.

`scope_classification` preserva separadamente as metas de oito facções principais e cinco instituições mágicas. O GDD não determina se as cinco instituições estão incluídas nas oito facções principais; essa sobreposição permanece decisão editorial adiada. Nenhuma contagem é alterada por templates.

### 5.7 Campos derivados e exclusivos do save

São derivados:

- religiões que possuem organizações, por `religion_ids`;
- instituições políticas de uma dinastia, por `dynastic_family_id`;
- regiões, assentamentos, locais e rotas com presença de facção, por `initial_state.territorial_presence`;
- profissões ligadas a facções, por `profession_ids`.

São exclusivos do save: membros, ocupantes, líder, tesouro atual, influência atual, coesão atual, legitimidade atual, reputações, propriedades, conflitos, alianças, decisões e objetivos correntes.

### 5.8 Invariantes

- Não existe lista completa e atual de membros no arquivo.
- `religion_ids` é a única direção armazenada entre facção e religião.
- `dynastic_family_id` é a única direção armazenada entre casa política e família dinástica.
- Casa nobre institucional usa `faction.*` mesmo quando ligada a `family.*`.
- Regras internas não são leis públicas sem reconhecimento de autoridade competente em `law.*`.
- `treasury` dentro de `initial_state` é semente, nunca saldo atual.

## 6. `family` — família, linhagem e casa dinástica

### 6.1 Família, casa e lar

`family.*` representa identidade familiar, linhagem conceitual, tradição de parentesco, convivência, herança e legado.

- **Família:** rede de parentesco, convivência, herança e identidade compartilhada.
- **Casa dinástica:** família com função histórica, nobiliárquica ou sucessória; continua sendo `family.*`.
- **Casa como instituição política:** usa `family.*` para linhagem e `faction.*` para organização, liderança, cargos, tesouro, território, diplomacia e decisões. A facção aponta `dynastic_family_id` para a família.
- **Lar:** residência compartilhada por parentes ou não parentes. Não é sinônimo de família e não recebe entidade nesta tarefa.

### 6.2 Campos

| Campo | Estrutura e propriedade |
|---|---|
| `family_type_key` | tipo familiar, de linhagem ou dinástico |
| `origin` | origem, data, período e evento de formação |
| `culture_id` | cultura principal associada por `culture.*` |
| `origin_region_ids` | regiões de origem, não residências atuais |
| `shared_identity` | identidade compartilhada estruturada |
| `lineage_concept` | concepção editorial da linhagem, sem árvore genealógica |
| `naming_conventions` | convenções de nome |
| `traditions`, `values`, `taboos` | tradições e normas familiares |
| `traditional_profession_ids` | ocupações tradicionais por `profession.*` |
| `traditional_religion_ids` | religiões tradicionalmente associadas |
| `symbols`, `coat_of_arms`, `motto` | identidade familiar ou dinástica |
| `traditional_seat_location_id` | assento tradicional; não residência atual |
| `dynastic_condition` | natureza dinástica e escopo histórico |
| `traditional_titles` | títulos tradicionais, não titulares atuais |
| `family_succession_rules` | regras familiares de sucessão |
| `family_inheritance_rules` | regras familiares de herança |
| `legacy` | legado estruturado |
| `founding_event_ids`, `historical_event_ids` | eventos por ID |
| `content_secret_ids` | segredos familiares de conteúdo |
| `historical_reputation` | reputação histórica editorial, não percepção pública atual |
| `initial_state` | condição inicial mínima, sem membros, líder ou herdeiro |
| `deferred_decisions` | decisões específicas adiadas |

Vínculos institucionais são considerados como campo derivado: consultam facções cujo `dynastic_family_id` aponta para a família. O template de família não mantém uma lista inversa de facções.

### 6.3 Parentesco e árvore genealógica

Pai, mãe, filho, adoção, união, separação, tutela e demais relações concretas serão registradas nas relações de NPCs e nos eventos correspondentes. `family.*` não duplica a árvore genealógica nem mantém lista completa de membros.

`lineage_concept` pode explicar critérios editoriais de pertencimento, ramos conceituais e identidade, mas não substitui relações pessoa a pessoa.

### 6.4 Estado inicial, derivados e save

`initial_state` pode registrar `effective_date`, `prominence_key`, `continuity_status_key`, `dynastic_status_key` e notas. Não contém membros vivos, líder, herdeiro, patrimônio, inventário, residências ou reivindicações ativas.

São derivados:

- facções dinásticas, por `faction.dynastic_family_id`;
- membros e genealogia, por relações futuras de NPC;
- instituições, títulos ocupados, herdeiros e reivindicações, por NPCs, facções, leis, contratos e estado.

São exclusivos do save: líder atual, herdeiro atual, membros atuais, patrimônio, inventário, residências, conflitos, alianças, reputação atual e reivindicações.

### 6.5 Invariantes

- Família não contém árvore genealógica manual nem lista completa de membros.
- Título tradicional não identifica titular.
- Assento tradicional não afirma propriedade ou residência atual.
- Tradição familiar não é lei, doutrina religiosa, decisão institucional, testamento ou resultado efetivo de sucessão.
- Casa política e família dinástica são duas entidades relacionadas quando ambas as dimensões existirem.

## 7. Herança, sucessão e precedência

Os contratos distinguem:

- tradição familiar em `family.*`;
- regra cultural em `culture.*`;
- doutrina religiosa em `religion.*`;
- lei aplicável em `law.*`;
- decisão institucional em eventos e estado de `faction.*`;
- testamento ou contrato individual em contratos futuros;
- resultado efetivo em eventos e estado da campanha.

Uma tradição familiar não adquire força jurídica automaticamente. Futuro resultado de sucessão deverá considerar jurisdição, vigência, autoridade, cultura, religião, contratos, relações, poder, eventos e decisão política. Este documento não implementa motor de sucessão nem define precedência executável.

## 8. `law` — regra normativa pública

### 8.1 Finalidade e fronteira

`law.*` representa regra normativa com força jurídica reconhecida por autoridade competente. Não representa crime concreto, caso, investigação, suspeito, acusado, julgamento, testemunho, evidência, condenação ou percepção pública.

Doutrina religiosa, tradição familiar e regra interna de facção não são leis automaticamente. Uma regra interna usa `law.*` apenas quando possuir força jurídica pública reconhecida e jurisdição definida.

### 8.2 Campos

| Campo | Estrutura e propriedade |
|---|---|
| `formal_title` | título jurídico formal, separado do nome editorial |
| `law_category_key` | categoria normativa |
| `jurisdiction` | `level_key` e exatamente um `entity_id` de reino, região ou assentamento |
| `legislative_authority_id` | autoridade legisladora por ID `faction.*` |
| `enforcement_authority_ids` | autoridades fiscalizadoras por IDs `faction.*` |
| `adjudication_authority_ids` | autoridades julgadoras por IDs `faction.*` |
| `promulgation_date` | data de promulgação |
| `effective_date` | início de vigência |
| `end_date` | término inicial conhecido ou `null` |
| `initial_legal_status` | situação jurídica inicial, distinta de `content_status` |
| `regulated_behavior` | sujeito, ação, objeto e contexto regulados |
| `subject_rules`, `object_rules` | sujeitos e objetos alcançados |
| `conditions` | condições editoriais por `condition_key` |
| `normative_rules` | obrigação, permissão, proibição ou restrição por `rule_key` |
| `exceptions` | exceções por `exception_key` |
| `licenses` | licenças, autoridade emissora, escopo e condições |
| `sanctions` | sanções por `sanction_key` |
| `precedence` | relações de precedência com outras leis |
| `replaced_law_ids` | leis que esta lei substitui ou revoga |
| `basis` | fundamento jurídico, político ou histórico |
| `initial_state` | apoio e oposição institucionais iniciais |
| `public_visibility_key` | visibilidade pública inicial |
| `publication_methods` | formas de publicação |
| `deferred_decisions` | decisões específicas adiadas |

`content_status` descreve revisão do arquivo: `draft`, `in_review`, `approved` ou `deprecated`. `initial_legal_status` descreve a situação jurídica inicial da lei. Os dois campos nunca se substituem.

### 8.3 Jurisdição

`jurisdiction.level_key` aceita `kingdom`, `region` ou `settlement` e precisa concordar com o prefixo de `entity_id`. Uma lei pública possui exatamente uma jurisdição canônica por arquivo. Quando a mesma norma for promulgada por autoridades diferentes, cada ato jurídico recebe sua própria entidade e relações explícitas de precedência ou derivação.

Locais herdam a aplicabilidade potencial das leis do assentamento, região e reino a que pertencem. Eles não repetem `law_ids`. Aplicabilidade efetiva ainda considera vigência, sujeitos, objetos, condições, exceções e precedência.

Autoridades legisladoras, fiscalizadoras, julgadoras, emissoras de licença e publicadoras são instituições modeladas como `faction.*`. Uma pessoa pode exercer essa autoridade como ocupante de cargo no estado futuro, mas seu nome ou ID de NPC não substitui a instituição competente no contrato estático da lei.

### 8.4 Condições e regra normativa

Este contrato não inventa linguagem executável. Cada `conditions` documenta:

- `condition_key`;
- sujeito;
- ação;
- objeto;
- contexto;
- condição editorial;
- exceções relacionadas;
- consequência normativa relacionada.

Cada `normative_rules` possui `rule_key`, `normative_type_key`, referências a sujeitos, objetos, condições, exceções e sanções, além de texto editorial curto. `normative_type_key` aceita:

- `obligation`;
- `permission`;
- `prohibition`;
- `restriction`.

Listas conceituais de obrigações, permissões, proibições e restrições são derivadas filtrando `normative_rules`; não são quatro listas duplicadas.

### 8.5 Exceções, licenças e sanções

Exceções e licenças usam chaves locais estáveis, condições explícitas, escopo e autoridade por ID. Licença não é cargo nem profissão.

`sanctions.category_key` admite:

- `warning`;
- `fine`;
- `restitution`;
- `loss_of_office`;
- `license_suspension`;
- `confiscation`;
- `service`;
- `exile`;
- `imprisonment`;
- `magical_prohibition`;
- `capital_punishment`.

Pena capital só é aplicável quando permitida pela configuração futura. Multas usam obrigatoriamente o contrato `money: { amount, currency_key }` de [`MATERIAL_ECONOMY_ENTITIES.md`](MATERIAL_ECONOMY_ENTITIES.md). Este contrato não cria valores reais. Restituição distingue dinheiro, quantidade material e obrigação; confisco aponta categorias ou objetos aplicáveis sem inventário atual.

Sanção declarada não é executada automaticamente pelo conteúdo. Aplicação, decisão, cumprimento e falha pertencem a eventos e ao estado da campanha.

### 8.6 Vigência, precedência, substituição e revogação

`initial_legal_status` e as datas definem a situação no início da campanha. Aprovação, suspensão, revogação, substituição, exceção temporária, reforma ou mudança de jurisdição depois da inicialização ocorrem por eventos e estado; o arquivo estático não é reescrito silenciosamente.

`replaced_law_ids` é a direção canônica: a lei nova aponta para as leis que substitui ou revoga. A “lei substituta” de uma lei antiga é derivada consultando quem a referencia; não se armazena simultaneamente `replacement_law_id`.

`precedence` registra `target_law_id`, `relation_key`, fundamento e escopo. Não é linguagem de resolução automática.

### 8.7 Apoio e oposição institucionais

`initial_state.institutional_positions` registra `faction_id`, `position_key`, fundamento, visibilidade e data inicial. `position_key` distingue apoio, oposição ou neutralidade por vocabulário futuro. Mudanças políticas posteriores pertencem ao save e a eventos.

### 8.8 Lei, crime, evidência e percepção

O futuro sistema deve manter separados:

1. ato verdadeiro;
2. lei aplicável;
3. violação objetiva;
4. evidência;
5. testemunho;
6. suspeito;
7. acusado;
8. culpado reconhecido;
9. decisão jurídica;
10. percepção pública;
11. rumor.

Uma Intervenção do Arquiteto pode produzir ato ou evidência, mas sua origem extradiegética permanece restrita ao sistema. Autoridades e NPCs só conhecem causas por percepção, evidência, comunicação, investigação ou outra via diegética válida. `law.*` não contém crimes, processos ou rumores.

### 8.9 Campos derivados e exclusivos do save

São derivados:

- leis aplicáveis em potencial a região, assentamento ou local, por jurisdição e hierarquia geográfica;
- lei substituta, por `replaced_law_ids`;
- listas de obrigações, permissões, proibições e restrições, por `normative_type_key`.

São exclusivos do save: estado jurídico atual depois do início, aplicação corrente, investigações, suspeitos, acusados, processos, evidências, testemunhos, julgamentos, decisões, condenações, cumprimento de sanções e percepção pública.

### 8.10 Invariantes

- `content_status` e `initial_legal_status` são independentes.
- Jurisdição usa ID de reino, região ou assentamento e concorda com `level_key`.
- Lei não armazena crimes, casos, processos, acusados, evidências ou julgamentos.
- Doutrina, tradição e política interna não possuem força jurídica automática.
- Multa usa `money`; dinheiro nunca é quantidade física.
- Sanção estática não executa ação.
- Mudança legal durante a campanha gera evento e estado.

## 9. Integrações canônicas

### Religião e cultura

`religion.origin_culture_id` registra origem da tradição. `culture.religion_relations` registra somente a perspectiva cultural sobre tradições e pode ser direcional. Não é lista inversa de religiões originadas nem substitui `religion.doctrinal_relations`.

### Religião e reino

Difusão religiosa inicial é propriedade de `religion.initial_state.diffusion`. Dominância é uma consulta agregada futura. Tolerância e proibição jurídicas são derivadas de `law.*` aplicável, não listas manuais no reino.

### Facção e geografia

Presença, influência, atuação e controle institucionais iniciais pertencem a `faction.initial_state.territorial_presence`. Região, assentamento, local e rota não mantêm a direção inversa. A hierarquia espacial continua pertencendo às entidades geográficas.

Em uma rota, `initial_state.toll.collector_id` é a fonte canônica da cobrança inicial: usa `faction.*` para a autoridade institucional ou `npc.*` para o cobrador inicialmente designado. Essa referência não concede controle institucional: controle inicial continua derivado de `faction.initial_state.territorial_presence`, e cobrança ou controle atuais pertencem ao save.

### Facção e profissão

`profession.*` define atividade econômica. `faction.roles` define cargos. Associações estáveis partem de `faction.profession_ids`; caminhos de formação podem referenciar facções específicas sem transformar cargo em profissão.

### Facção e lei

`faction.policies` e regras internas pertencem à facção. `law.*` é usado somente para força jurídica reconhecida. Autoridades legisladoras, fiscalizadoras e julgadoras podem apontar para `faction.*`.

### Família e facção

`family.*` possui linhagem e identidade; `faction.*` possui organização política. A referência canônica é `faction.dynastic_family_id`. Membros, liderança, patrimônio, relações, títulos ocupados e objetivos não são duplicados.

## 10. Validação manual conjunta

Antes de aprovar conteúdo futuro:

- conferir `schema_version: "1.0.0"`, prefixo, slug, pasta e `content_status`;
- conferir YAML, campos comuns, tipos, `null`, listas vazias e ausência de strings vazias;
- validar todas as referências por ID e chaves locais;
- confirmar separação entre definição estática, `initial_state`, derivados e save;
- confirmar ausência de listas inversas manuais;
- confirmar que religião não possui lista de organizações ou seguidores;
- confirmar que facção não possui lista completa de membros ou ocupantes;
- confirmar que família não possui árvore genealógica ou membros completos;
- confirmar que lei não possui crime, processo, evidência ou julgamento;
- conferir cargos, quantidade permitida, ocupação, sucessão e participação decisória;
- conferir relações institucionais direcionais e regra de simetria;
- conferir `religion_ids` e `dynastic_family_id` como direções canônicas;
- conferir jurisdição, vigência, precedência, substituição, exceções, licenças e sanções;
- conferir multas pelo contrato `money`;
- confirmar que regra religiosa, familiar ou institucional não foi tratada automaticamente como lei;
- confirmar que origem extradiegética não virou conhecimento de NPC;
- confirmar corpo Markdown coerente, sem lore mecânico concorrente;
- confirmar ausência de placeholders em `approved`;
- confirmar funcionamento editorial completo sem IA generativa.

## 11. Decisões adiadas

Permanecem deliberadamente adiados:

- vocabulários concretos de tradições, doutrinas, posições, presença, autoridade, relações, família e categorias jurídicas;
- escalas de confiança, hostilidade, influência, coesão, legitimidade, proeminência e difusão;
- datas, religiões, facções, famílias, leis, valores, símbolos, textos, locais e eventos reais;
- sobreposição exata entre as oito facções principais e as cinco instituições mágicas;
- modelagem de lares, caso se prove necessária;
- schemas de NPC, parentesco concreto, títulos ocupados, contratos individuais, eventos, crimes, processos, evidências e rumores;
- catálogo e valores reais de sanções, multas, restituições, licenças e exceções;
- motor de sucessão e resolução de conflitos entre família, cultura, religião, lei, contratos e poder;
- linguagem ou arquitetura executável de condições legais;
- estado persistente, validação automatizada, banco de dados, API e implementação;
- quantidade de leis, que continua `a definir`;
- contratos de escolas de magia, magias, rituais, efeitos e artefatos, que formam a próxima atividade documental.
