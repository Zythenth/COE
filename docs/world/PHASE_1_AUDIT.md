# Auditoria editorial final da Fase 1

## 1. Objetivo

Verificar se os contratos editoriais e templates da Fase 1 formam um conjunto completo, coerente, preenchível e suficiente para iniciar a autoria real de Eldrath, corrigindo somente inconsistências comprovadas e sem criar entidades, lore ou implementação.

## 2. Escopo

Foram examinados o GDD canônico 1.4 inicial, as regras persistentes do projeto, todos os documentos de `docs/world/`, os 11 contratos de `docs/world/schemas/`, os 28 templates, o manifesto, os READMEs, a árvore de conteúdo, o estado Git e as reservas de assets e design. A auditoria não abrange criação de mundo, arte, interface, código, dependências ou execução de integração externa.

## 3. Fontes examinadas

| Camada | Fonte | Extensão examinada | Resultado |
|---|---|---|---|
| 1 | `Base/GDD.md` | leitura integral; versão e hash inicial confirmados | fonte canônica confirmada |
| 2 | instruções locais não versionadas | leitura integral | regras de fase, escopo e preservação confirmadas |
| 3–5 | `CONTENT_SCHEMA.md`, `ID_CONVENTIONS.md` e 11 contratos especializados | leitura integral e comparação cruzada | conjunto completo após correções registradas |
| 6–9 | 28 templates, manifesto, documentos de acompanhamento e READMEs | leitura integral, inventário e validação estrutural | compatíveis após sincronização editorial |
| repositório | árvore, Git, pastas de conteúdo, assets e design | inventário integral | worktree inicial limpo; nenhuma entidade ou implementação |

## 4. Metodologia

1. confirmação transacional de branch, limpeza, unicidade, versão e hash do GDD;
2. leitura integral por ordem de precedência;
3. inventário independente de schemas, templates e categorias;
4. comparação de caminhos, prefixos, campos, referências, propriedade e estado;
5. teste conceitual das invariantes de causalidade, conhecimento, ameaças e GitHub;
6. classificação de cada divergência como correção determinada, adiamento legítimo ou bloqueio;
7. correções mínimas e sincronização do encerramento;
8. validações automáticas e manuais finais.

## 5. Inventário de schemas

| Nº | Schema | Escopo | Estado final |
|---:|---|---|---|
| 1 | `FOUNDATIONAL_ENTITIES.md` | mundo, calendário, idioma, cultura e reino | aprovado |
| 2 | `GEOGRAPHY_ENTITIES.md` | região, assentamento, local e rota | aprovado |
| 3 | `MATERIAL_ECONOMY_ENTITIES.md` | recurso, profissão, item e estruturas econômicas | aprovado |
| 4 | `INTERVENTION_PERCEPTION_AND_KNOWLEDGE.md` | intervenção, evidência, percepção, conhecimento, crença e memória | aprovado após correção |
| 5 | `SOCIETY_INSTITUTIONS_AND_LAW_ENTITIES.md` | religião, facção, família e lei | aprovado após correção |
| 6 | `MAGIC_SYSTEM_ENTITIES.md` | escola, magia, ritual, efeito e artefato | aprovado após correção |
| 7 | `CREATURE_HEALTH_AND_DISEASE_ENTITIES.md` | criatura, doença, saúde e condições | aprovado após correção |
| 8 | `NPC_SYSTEM_ENTITIES.md` | NPC e subregistros incorporados | aprovado após correção |
| 9 | `EVENT_RUMOR_HISTORY_AND_CONFLICT_ENTITIES.md` | evento, rumor, história, gatilho e conflito | aprovado após correção |
| 10 | `MONSTROUS_THREATS_AND_INCURSIONS.md` | ameaças, grupos, hordas, ataques e incursões | aprovado após correção |
| 11 | `GITHUB_DERIVED_WORLD_GENERATION.md` | geração opcional, snapshot, fórmula, mapa e campanha | aprovado após correção |

Total: 11 schemas especializados, além do contrato comum.

## 6. Inventário de templates

| Template | Schema responsável | Formato | Resultado |
|---|---|---|---|
| `base_entity.md` | `CONTENT_SCHEMA.md` | front matter YAML + Markdown | base conceitual aprovada; valores de versão e estado são placeholders intencionais e não representam entidade |
| `world.template.yaml` | `FOUNDATIONAL_ENTITIES.md` | YAML | aprovado |
| `calendar.template.md` | `FOUNDATIONAL_ENTITIES.md` | front matter YAML + Markdown | aprovado |
| `language.template.md` | `FOUNDATIONAL_ENTITIES.md` | front matter YAML + Markdown | aprovado |
| `culture.template.md` | `FOUNDATIONAL_ENTITIES.md` | front matter YAML + Markdown | aprovado |
| `kingdom.template.yaml` | `FOUNDATIONAL_ENTITIES.md` | YAML | aprovado |
| `region.template.md` | `GEOGRAPHY_ENTITIES.md` | front matter YAML + Markdown | aprovado |
| `settlement.template.md` | `GEOGRAPHY_ENTITIES.md` | front matter YAML + Markdown | aprovado |
| `location.template.md` | `GEOGRAPHY_ENTITIES.md` | front matter YAML + Markdown | aprovado |
| `route.template.md` | `GEOGRAPHY_ENTITIES.md` | front matter YAML + Markdown | aprovado |
| `resource.template.md` | `MATERIAL_ECONOMY_ENTITIES.md` | front matter YAML + Markdown | aprovado |
| `profession.template.md` | `MATERIAL_ECONOMY_ENTITIES.md` | front matter YAML + Markdown | aprovado |
| `item.template.md` | `MATERIAL_ECONOMY_ENTITIES.md` | front matter YAML + Markdown | aprovado |
| `religion.template.md` | `SOCIETY_INSTITUTIONS_AND_LAW_ENTITIES.md` | front matter YAML + Markdown | aprovado |
| `faction.template.md` | `SOCIETY_INSTITUTIONS_AND_LAW_ENTITIES.md` | front matter YAML + Markdown | aprovado |
| `family.template.md` | `SOCIETY_INSTITUTIONS_AND_LAW_ENTITIES.md` | front matter YAML + Markdown | aprovado |
| `law.template.md` | `SOCIETY_INSTITUTIONS_AND_LAW_ENTITIES.md` | front matter YAML + Markdown | aprovado |
| `magic_school.template.md` | `MAGIC_SYSTEM_ENTITIES.md` | front matter YAML + Markdown | aprovado |
| `spell.template.md` | `MAGIC_SYSTEM_ENTITIES.md` | front matter YAML + Markdown | aprovado |
| `ritual.template.md` | `MAGIC_SYSTEM_ENTITIES.md` | front matter YAML + Markdown | aprovado |
| `magic_effect.template.md` | `MAGIC_SYSTEM_ENTITIES.md` | front matter YAML + Markdown | aprovado |
| `artifact.template.md` | `MAGIC_SYSTEM_ENTITIES.md` | front matter YAML + Markdown | aprovado |
| `creature.template.md` | `CREATURE_HEALTH_AND_DISEASE_ENTITIES.md` | front matter YAML + Markdown | aprovado |
| `disease.template.md` | `CREATURE_HEALTH_AND_DISEASE_ENTITIES.md` | front matter YAML + Markdown | aprovado |
| `npc.template.md` | `NPC_SYSTEM_ENTITIES.md` | front matter YAML + Markdown | aprovado |
| `event.template.md` | `EVENT_RUMOR_HISTORY_AND_CONFLICT_ENTITIES.md` | front matter YAML + Markdown | aprovado |
| `rumor.template.md` | `EVENT_RUMOR_HISTORY_AND_CONFLICT_ENTITIES.md` | front matter YAML + Markdown | aprovado |
| `conflict.template.md` | `EVENT_RUMOR_HISTORY_AND_CONFLICT_ENTITIES.md` | front matter YAML + Markdown | aprovado |

Total: 28 templates; 27 especializados e uma base conceitual.

## 7. Inventário de categorias

| Categoria do manifesto | Prefixo | Diretório | Schema | Estado final |
|---|---|---|---|---|
| `calendars` | `calendar.` | existe; somente `.gitkeep` | fundamental | aprovado |
| `languages` | `language.` | existe; somente `.gitkeep` | fundamental | aprovado |
| `cultures` | `culture.` | existe; somente `.gitkeep` | fundamental | aprovado |
| `regions` | `region.` | existe; somente `.gitkeep` | geografia | aprovado |
| `settlements` | `settlement.` | existe; somente `.gitkeep` | geografia | aprovado |
| `locations` | `location.` | existe; somente `.gitkeep` | geografia | aprovado |
| `routes` | `route.` | existe; somente `.gitkeep` | geografia | aprovado |
| `npcs` | `npc.` | existe; somente `.gitkeep` | NPC | aprovado |
| `families` | `family.` | existe; somente `.gitkeep` | sociedade | aprovado |
| `factions` | `faction.` | existe; somente `.gitkeep` | sociedade | aprovado |
| `religions` | `religion.` | existe; somente `.gitkeep` | sociedade | aprovado |
| `professions` | `profession.` | existe; somente `.gitkeep` | economia | aprovado |
| `creatures` | `creature.` | existe; somente `.gitkeep` | criatura e saúde | aprovado |
| `resources` | `resource.` | existe; somente `.gitkeep` | economia | aprovado |
| `items` | `item.` | existe; somente `.gitkeep` | economia | aprovado |
| `laws` | `law.` | existe; somente `.gitkeep` | sociedade | aprovado |
| `diseases` | `disease.` | existe; somente `.gitkeep` | criatura e saúde | aprovado |
| `events` | `event.` | existe; somente `.gitkeep` | evento e conflito | aprovado |
| `rumors` | `rumor.` | existe; somente `.gitkeep` | evento e conflito | aprovado |
| `conflicts` | `conflict.` | existe; somente `.gitkeep` | evento e conflito | aprovado |
| `magic/schools` | `magic_school.` | existe; somente `.gitkeep` | magia | aprovado após correção |
| `magic/spells` | `spell.` | existe; somente `.gitkeep` | magia | aprovado |
| `magic/rituals` | `ritual.` | existe; somente `.gitkeep` | magia | aprovado |
| `magic/artifacts` | `artifact.` | existe; somente `.gitkeep` | magia | aprovado |
| `magic/effects` | `magic_effect.` | existe; somente `.gitkeep` | magia | aprovado após correção |

Total: 25 categorias, sem duplicação. Não existem `demons/`, `monsters/`, `hordes/` ou `incursions/`.

## 8. Matriz de requisitos da Fase 1

| Requisito | Fonte | Evidência | Resultado | Correção | Estado final |
|---|---|---|---|---|---|
| estrutura comum | GDD; `CONTENT_SCHEMA.md` | formato, campos comuns, ausência, revisão e conteúdo versus save definidos | conforme | estado da fase sincronizado | aprovado após correção |
| IDs | GDD; `ID_CONVENTIONS.md` | formato, prefixos, estabilidade, não reciclagem e categorias técnicas distinguidos | conforme | prefixos mágicos provisórios corrigidos no contrato comum | aprovado após correção |
| referências | `CONTENT_SCHEMA.md`; schemas | direção, cardinalidade, existência e ausência de inversas definidas | conforme | nenhuma | aprovado |
| mundo | `FOUNDATIONAL_ENTITIES.md`; template | contrato e template YAML existentes; arquivo real ausente como exigido | conforme | nenhuma | aprovado |
| calendário | `FOUNDATIONAL_ENTITIES.md`; template | eras, meses, estações, datas e adiamentos contratados | conforme | nenhuma | aprovado |
| idioma | `FOUNDATIONAL_ENTITIES.md`; template | identidade, escrita, uso e relações contratados | conforme | nenhuma | aprovado |
| cultura | `FOUNDATIONAL_ENTITIES.md`; template | valores, normas, práticas e referências contratados | conforme | nenhuma | aprovado |
| reino | `FOUNDATIONAL_ENTITIES.md`; template | governo, moedas e estado inicial delimitados | conforme | nenhuma | aprovado |
| região | `GEOGRAPHY_ENTITIES.md`; template | hierarquia, bioma, clima, fronteiras e estado inicial definidos | conforme | nenhuma | aprovado |
| assentamento | `GEOGRAPHY_ENTITIES.md`; template | tipo, papel administrativo, economia e governante inicial separados | conforme | nenhuma | aprovado |
| local | `GEOGRAPHY_ENTITIES.md`; template | região, assentamento opcional, pai, acesso e descoberta separados | conforme | nenhuma | aprovado |
| rota | `GEOGRAPHY_ENTITIES.md`; template | extremos, direção, distância, duração e estado inicial definidos | conforme | nenhuma | aprovado |
| recurso | `MATERIAL_ECONOMY_ENTITIES.md`; template | definição fungível, unidades, fluxos e perigos contratados | conforme | nenhuma | aprovado |
| profissão | `MATERIAL_ECONOMY_ENTITIES.md`; template | progressão, tarefas, produção e requisitos contratados | conforme | nenhuma | aprovado |
| item | `MATERIAL_ECONOMY_ENTITIES.md`; template | definição separada de instância e artefato | conforme | nenhuma | aprovado |
| religião | schema social; template | doutrina separada de organização e difusão inicial | conforme | nenhuma | aprovado |
| facção | schema social; template | organização, papéis, decisões, presença e membros derivados | conforme | nenhuma | aprovado |
| família | schema social; template | identidade familiar separada de membros e parentesco | conforme | adiamentos obsoletos atualizados | aprovado após correção |
| lei | schema social; template | jurisdição, vigência, normas, exceções e sanções definidas | conforme | adiamentos obsoletos atualizados | aprovado após correção |
| escola mágica | schema mágico; template | `magic_school.*`, subescola por pai e relações direcionais | conforme | referência de versão e prefixo comum atualizados | aprovado após correção |
| magia | schema mágico; template | técnica, requisitos, custos, alvos, efeitos, riscos e aprendizagem | conforme | referência de versão atualizada | aprovado após correção |
| ritual | schema mágico; template | papéis, preparação, etapas, interrupção e resultado contratados | conforme | referência de versão atualizada | aprovado após correção |
| efeito mágico | schema mágico; template | definição reutilizável separada de aplicação | conforme | prefixo comum atualizado | aprovado após correção |
| artefato | schema mágico; template | identidade singular e estado inicial separados do estado atual | conforme | referência de versão atualizada | aprovado após correção |
| criatura | schema de criaturas; template | espécie/tipo, ecologia, população agregada e indivíduo separados | conforme | referência de versão atualizada | aprovado após correção |
| doença | schema de criaturas; template | definição, instância, infecção, diagnóstico e tratamento separados | conforme | referência de versão atualizada | aprovado após correção |
| NPC | schema de NPC; template | perfil, `initial_state`, subregistros, percepção e decisão contratados | conforme | referência e estado editorial atualizados | aprovado após correção |
| evento | schema de eventos; template | conteúdo estático separado de evento concreto imutável | conforme | referência de versão atualizada | aprovado após correção |
| rumor | schema de eventos; template | afirmação, verdade restrita, versão e genealogia definidos | conforme | referência de versão atualizada | aprovado após correção |
| conflito | schema de eventos; template | tensão e possibilidades sem vencedor fixo | conforme | referência de versão atualizada | aprovado após correção |
| intervenção | contrato transversal | comando, alteração, evidência, evento e origem restrita separados | conforme | referência de versão atualizada | aprovado após correção |
| percepção | contrato transversal; NPC | observador, alcance, sentidos, evidência e versão percebida | conforme | referência de versão atualizada | aprovado após correção |
| conhecimento | contrato transversal; NPC | fonte, evidência, confiança e ausência de onisciência | conforme | referência de versão atualizada | aprovado após correção |
| causalidade | contrato transversal; eventos | causa, raiz, capacidade, oportunidade e consequência | conforme | nenhuma | aprovado |
| ameaças monstruosas | contrato de ameaças | espécie, indivíduo, população e fonte de ameaça separados | conforme | referência de versão atualizada | aprovado após correção |
| incursões | contrato de ameaças | ataque e incursão concretos pertencem ao save e aos eventos | conforme | referência de versão atualizada | aprovado após correção |
| geração pelo GitHub | contrato GitHub | modos, snapshot, fórmula, edição, offline, segurança e saves definidos | conforme após teste de bordas | fallback de ausência total e precedência de constantes explicitados | aprovado após correção |

## 9. Auditoria de IDs

| Requisito | Fonte | Evidência | Resultado | Correção | Estado final |
|---|---|---|---|---|---|
| formato `tipo.nome_estavel` | GDD; `ID_CONVENTIONS.md` | minúsculas, ASCII, underscore e prefixo obrigatórios | conforme | nenhuma | aprovado |
| prefixos de conteúdo | contrato comum e especializados | 27 tipos de entidade mapeados; 25 categorias de pasta | dois prefixos provisórios no contrato comum | `school` → `magic_school`; `effect` → `magic_effect` | aprovado após correção |
| namespaces não editoriais | `ID_CONVENTIONS.md`; schemas | subregistros, instâncias, eventos concretos, snapshots e ramificações possuem proprietários distintos | conforme | nenhuma pasta criada para subregistro | aprovado |
| estabilidade e resolução | contrato comum | ID não reciclável; nome não é chave; referência ausente é erro | conforme | nenhuma | aprovado |

## 10. Auditoria de caminhos

| Requisito | Fonte | Evidência | Resultado | Correção | Estado final |
|---|---|---|---|---|---|
| manifesto versus diretórios | manifesto; árvore | 25 entradas únicas correspondem a 25 pastas-folha | conforme | nenhuma | aprovado |
| categoria versus prefixo | contrato comum; ID; schemas | todos os prefixos apontam a caminhos existentes | duas células provisórias | corrigidas no contrato comum | aprovado após correção |
| categorias indevidas | GDD; ameaças | ausência confirmada de pastas paralelas de monstros, demônios, hordas e incursões | conforme | nenhuma | aprovado |
| arquivos singulares | contrato fundamental | `world.yaml` e `kingdom.yaml` inexistentes; templates presentes | conforme ao estado da fase | nenhuma | aprovado |

## 11. Auditoria de referências

| Requisito | Fonte | Evidência | Resultado | Correção | Estado final |
|---|---|---|---|---|---|
| destino e tipo | contrato comum; schemas | cada campo especializado declara prefixos permitidos | conforme | nenhuma | aprovado |
| direção canônica | schemas geográfico, social, mágico e saúde | região, presença de facção, doença-vetor e escola são mantidos no proprietário | conforme | nenhuma | aprovado |
| inversas | mesmos contratos | consultas derivadas substituem listas inversas manuais | conforme | nenhuma | aprovado |
| opcionais e ausentes | contrato comum | omissão, `null` e `[]` possuem semânticas distintas | conforme | nenhuma | aprovado |

## 12. Auditoria de propriedade canônica

| Dado | Proprietário estático | Proprietário inicial | Proprietário atual | Fonte derivada | Referências permitidas | Referências proibidas |
|---|---|---|---|---|---|---|
| membros de facção | papéis e políticas em `faction.*` | afiliação em `npc.initial_state` | save e eventos | consulta de NPCs por `faction_id` | `npc.*`, `faction.*`, cargo local | `faction.member_ids` concorrente |
| membros de família | identidade em `family.*` | relações do NPC | save e eventos | consulta de parentesco e relações | `npc.*`, `family.*`, eventos | lista de pessoas em `family.*` |
| liderança | papéis e processo em `faction.*` ou governo | ocupação de cargo/ruler no estado inicial | save e eventos | consulta de ocupantes | NPC, facção, assentamento, reino | líder atual fixo no contrato institucional |
| profissão | definição `profession.*` | ocupação do NPC | save | consulta por `profession_id` | NPC, profissão, facção empregadora | lista de trabalhadores em `profession.*` |
| emprego | regras da profissão e instituição | `npc.initial_state.occupation` | save e contratos/eventos | consulta de vínculos | NPC, profissão, facção, local | emprego atual em definição de profissão |
| inventário | definições `item.*`, `resource.*`, `artifact.*` | sementes no NPC/assentamento/artefato | save | consulta de posses e estoques | IDs de definição e local | instância atual em arquivo de definição |
| propriedade | regras da entidade possuída | interesses em `npc.initial_state` | save e eventos | consulta de titularidade | NPC, facção, família, item, artefato, local | proprietário atual fixo na definição |
| magia conhecida | `spell.*` e `ritual.*` definem técnica | domínio em `npc.initial_state.magic_mastery` | save | consulta de domínio | NPC, spell, ritual, fonte | lista inversa de conhecedores na magia |
| afinidade | perfil mágico do NPC | valor-base do NPC | save quando alterável | cálculo de capacidade | NPC, escola, fonte | afinidade individual na escola |
| reputação | escalas e causas contratadas | `npc.initial_state.reputations` | save e eventos | reputação por audiência/contexto | NPC, audiência, evento | reputação universal ou lista inversa |
| relações | estrutura `relationship.*` incorporada | registros direcionais iniciais | save e eventos | tipos derivados | dois NPCs, memória, evento | relação simétrica presumida |
| memória | estrutura incorporada do NPC | `npc.initial_state.memories` | save e eventos | efeitos relacionais derivados | NPC, evento, percepção, fonte | memória em biografia sem origem |
| crença | estrutura incorporada do NPC | `npc.initial_state.belief_records` | save | interpretação derivada de evidências | NPC, fonte, evidência, rumor | verdade do motor como crença automática |
| conhecimento | estrutura incorporada do NPC | `npc.initial_state.knowledge_records` | save | confiança e contradições | NPC, fonte, evidência, percepção | biografia ou metadado administrativo |
| rumor | definição `rumor.*` | alcance e versão iniciais | transmissões no save e eventos | genealogia e credibilidade | evento, evidência, NPC, grupo, lugar | fato ou crença tratados como rumor idêntico |
| evento | possibilidade/história em `event.*` | fatos anteriores autorizados | log imutável da campanha | timeline, crônica e resumo | entidades, causa, evidência, consequência | reescrita de evento concreto |
| conflito | definição `conflict.*` | `conflict.initial_state` | save e eventos | tensão e estado derivados | lados, recursos, eventos, rumores | vencedor ou resultado fixo no conteúdo |
| criatura | espécie/tipo em `creature.*` | distribuição agregada autorizada | save para ocorrências | habitats e ameaças por consulta | creature, região, doença, recurso | indivíduo persistente em `creature.*` |
| indivíduo | perfil `npc.*` | `npc.initial_state` | save e eventos | idade, condição e posição | creature, família, facção, profissão | identidade duplicada como criatura |
| população | capacidade em `creature.*` | `creature.initial_state.population_distribution` | save | agregações por território | creature e um alvo geográfico | um NPC por integrante |
| horda | capacidade da espécie | somente quando o estado inicial da campanha autorizar | save | agregação de população/grupo | creature, líder NPC, local, evento | pasta ou entidade `horde.*` de conteúdo |
| ataque | capacidades estáticas e conflito | fila/estado inicial quando autorizado | eventos e save | consequência de causa, capacidade e oportunidade | ator, alvo, local, conflito | ataque atual em `creature.*` |
| incursão | capacidades e possibilidades | fila/estado inicial quando autorizado | eventos e save | sequência de ataques e movimento | ameaça, rota, lugar, conflito | pasta ou entidade `incursion.*` |
| doença | definição `disease.*` | exposição possível autorizada | definição continua estática | relações epidemiológicas | criatura, recurso, item, lugar | estágio atual de pessoa |
| infecção | nenhuma entidade estática própria | instância inicial no estado autorizado | save e eventos | diagnóstico e transmissão | disease, hospedeiro, fonte, evento | arquivo `infection.*` |
| legalidade | normas em `law.*` | aplicabilidade pela jurisdição e estado inicial | derivada de lei + save | consulta jurídica contextual | lei, jurisdição, sujeito, objeto, licença | booleano global em magia/item/NPC |
| rota | `route.*` | `route.initial_state` | save | regiões e controle por consulta | assentamento/local nos extremos | lista inversa em extremos |
| controle territorial | capacidade/presença de `faction.*` | `faction.initial_state.territorial_presence` | save e eventos | consulta geográfica | facção e território | controlador duplicado na geografia |
| governante | regra de governo e cargo | `settlement.initial_state.ruler_id` ou equivalente do reino | save e eventos | consulta de ocupação | NPC e jurisdição | governante atual permanente em prosa |
| snapshot GitHub | contrato do snapshot | snapshot confirmado e congelado | o mesmo snapshot imutável | prévia e auditoria | projetos públicos, versões, hash | token e identidades desnecessárias |
| checkpoint | contrato de campanha | checkpoint inicial | checkpoints posteriores imutáveis | restauração validada | campanha, snapshot, hashes, versões | conteúdo autoral reescrito |
| estado da campanha | nenhum arquivo estático | checkpoint inicial | save e log ordenado | consultas, timeline e interface | IDs técnicos e IDs de conteúdo resolvidos | estado atual em `content/` |

Resultado: todas as entidades e estados possuem proprietário; nenhuma duplicação de propriedade permanece aberta.

## 13. Auditoria de conteúdo versus estado

| Requisito | Fonte | Evidência | Resultado | Correção | Estado final |
|---|---|---|---|---|---|
| mutáveis fora do conteúdo | GDD; schemas | posição, saúde, emoção, estoque, ocupante, líder, preço, hordas, ataques, propagação e intervenções atuais pertencem ao save | conforme | nenhuma | aprovado |
| uso de `initial_state` | schemas | somente sementes iniciais explicitamente autorizadas | conforme | nenhuma | aprovado |
| mudanças posteriores | contratos de eventos e save | evento imutável e estado de campanha registram transições | conforme | nenhuma | aprovado |
| templates | 28 arquivos | avisos editoriais e agrupamento de valores mutáveis compatíveis | conforme | nenhuma | aprovado |

## 14. Auditoria de dados estruturados versus prosa

| Requisito | Fonte | Evidência | Resultado | Correção | Estado final |
|---|---|---|---|---|---|
| mecânica estruturada | contrato comum e especializados | custos, efeitos, referências, causalidade, economia e estado inicial têm campos | conforme | nenhuma | aprovado |
| papel da prosa | contratos e templates | corpo explica contexto e lore, sem redefinir dados | conforme | nenhuma | aprovado |
| campos órfãos | comparação de 28 templates com 11 schemas | todo campo especializado possui contrato semântico; não se exigiu igualdade textual | conforme | nenhuma | aprovado |

## 15. Auditoria de vocabulários

| Requisito | Fonte | Evidência | Resultado | Correção | Estado final |
|---|---|---|---|---|---|
| proprietário | contratos especializados | cada chave pertence ao campo e schema que a define | disperso, mas coerente | centralizado em `CONTROLLED_VOCABULARY.md` | aprovado após correção |
| listas aprovadas | schemas | 12 registros possuem valores ou referências normativas utilizáveis | conforme | catalogados sem duplicação integral | aprovado |
| decisões futuras | schemas | 25 registros dependem de conteúdo ou implementação | legítimo | proprietário, formato e fase registrados | adiado explicitamente |
| extensão | contrato comum e registro central | chaves estáveis; mudanças incompatíveis exigem migração | conforme | política consolidada | aprovado após correção |

## 16. Auditoria de templates

| Requisito | Fonte | Evidência | Resultado | Correção | Estado final |
|---|---|---|---|---|---|
| schema responsável | inventário da seção 6 | todos os 28 modelos mapeados | conforme | nenhuma | aprovado |
| YAML e duplicatas | validação estrutural | 26 front matters e 2 YAML puros válidos; nenhuma chave duplicada | conforme | nenhuma | aprovado |
| versão e estado | contratos e parse | 27 templates especializados usam `1.0.0` e `draft`; base genérica usa placeholders intencionais | conforme | nenhuma | aprovado |
| prefixos e campos | ID e schemas | 27 templates especializados usam prefixo correto; campos são semanticamente contratados | conforme | nenhuma | aprovado |
| propriedade e estado | schemas | campos mutáveis ficam em `initial_state` ou são explicitamente estáticos | conforme | nenhuma | aprovado |
| placeholders e corpo | templates | placeholders somente em `_templates/`; avisos e seções editoriais presentes | conforme | nenhuma | aprovado |
| entidade real | árvore de conteúdo | nenhum template contém conteúdo real; todos usam exemplos estruturais genéricos | conforme | nenhuma | aprovado |

## 17. Auditoria de quantidades

| Requisito | Fonte | Evidência | Resultado | Correção | Estado final |
|---|---|---|---|---|---|
| metas fixas | GDD; `CONTENT_STATUS.md` | 4 regiões, 1 capital, 3 cidades, 4 vilas, 12 locais, 8 facções, 6 famílias, 3 tradições, 5 instituições, 30 NPCs-semente, até 150 persistentes, 60 magias, 12 artefatos, 20 profissões, 40 eventos, 20 rumores, 8 conflitos e 15 escolas preservados | conforme | nenhuma | aprovado |
| metas abertas | GDD; contratos | calendários, idiomas, culturas, rotas, recursos, itens, rituais, efeitos, criaturas, doenças e leis permanecem `a definir` | legítimo | registradas como adiadas | adiado explicitamente |
| quantidades existentes | árvore e status | todas as entidades reais iguais a zero | conforme | nenhuma | aprovado |
| templates e contratos | GDD | não contam como entidades | conforme | nenhuma | aprovado |

## 18. Auditoria do manifesto

| Requisito | Fonte | Evidência | Resultado | Correção | Estado final |
|---|---|---|---|---|---|
| YAML e unicidade | `manifest.yaml` | parse válido; 25 caminhos e 25 categorias vazias, sem repetição | conforme | nenhuma | aprovado |
| diretórios | árvore | correspondência exata com as 25 pastas-folha | conforme | nenhuma | aprovado |
| estado editorial | encerramento transacional | contratos e templates aprovados após auditoria | `in_review` ficou superado pelo fechamento | alterado para `approved` | aprovado após correção |
| conteúdo pendente | manifesto e árvore | `world.yaml` e `kingdom.yaml` continuam `not_created`; implementação `not_started` | conforme | nenhuma | aprovado |

## 19. Auditoria de causalidade

| Requisito | Fonte | Evidência | Resultado | Correção | Estado final |
|---|---|---|---|---|---|
| cadeia completa | contrato transversal | causa real → alteração → evidência → percepção → interpretação → crença → memória → rumor → consequência | conforme | nenhuma | aprovado |
| evento-raiz | contrato de eventos | exige classificação, fundamento e escopo | conforme | nenhuma | aprovado |
| ataque | contrato de ameaças | exige causa, capacidade, oportunidade e consequência | conforme | nenhuma | aprovado |

## 20. Auditoria de percepção e conhecimento

| Requisito | Fonte | Evidência | Resultado | Correção | Estado final |
|---|---|---|---|---|---|
| presença e alcance | contrato transversal; NPC | ausência impede percepção automática; sentidos e condições limitam observação | conforme | nenhuma | aprovado |
| biografia | contrato de NPC | não concede conhecimento sem fonte | conforme | nenhuma | aprovado |
| estados epistêmicos | NPC; eventos | fato, conhecimento, crença, memória e rumor são registros distintos | conforme | nenhuma | aprovado |
| origem | NPC | memória, conhecimento e crença registram fonte | conforme | nenhuma | aprovado |

## 21. Auditoria de intervenções

| Requisito | Fonte | Evidência | Resultado | Correção | Estado final |
|---|---|---|---|---|---|
| origem restrita | contrato transversal | usuário aparece apenas em log administrativo/onisciente | conforme | nenhuma | aprovado |
| correção mental | GDD; contrato | correção silenciosa continua proibida | conforme | nenhuma | aprovado |
| influência | contrato | modificador não escolhe ação nem garante decisão | conforme | nenhuma | aprovado |
| compulsão | GDD; contrato | fora do MVP | conforme | nenhuma | aprovado |

## 22. Auditoria de eventos e rumores

| Requisito | Fonte | Evidência | Resultado | Correção | Estado final |
|---|---|---|---|---|---|
| evento concreto | contrato de eventos | ID técnico separado e registro imutável | conforme | nenhuma | aprovado |
| `event.*` | ID e schema | somente conteúdo histórico, base ou possibilidade editorial | conforme | nenhuma | aprovado |
| versões de rumor | schema e template | genealogia, mutações, correções e verdade restrita separadas | conforme | nenhuma | aprovado |

## 23. Auditoria de conflitos

| Requisito | Fonte | Evidência | Resultado | Correção | Estado final |
|---|---|---|---|---|---|
| vencedor | schema e template | somente resoluções possíveis e condições; resultado efetivo no save | conforme | nenhuma | aprovado |
| estado | `conflict.initial_state` | tensão inicial separada do estado atual | conforme | nenhuma | aprovado |
| causalidade | schema | origem, queixas, recursos, capacidades e eventos relacionados | conforme | nenhuma | aprovado |

## 24. Auditoria de criaturas e ameaças

| Requisito | Fonte | Evidência | Resultado | Correção | Estado final |
|---|---|---|---|---|---|
| espécie e indivíduo | contratos de criatura/NPC | `creature.*` versus `npc.*` | conforme | nenhuma | aprovado |
| agregação | contrato de ameaças | população, grupo e horda não materializam cada integrante | conforme | nenhuma | aprovado |
| culto e doutrina | contratos social e ameaças | organização `faction.*`; crença `religion.*` | conforme | nenhuma | aprovado |
| fonte persistente | contratos | ninho ou portal pode usar `location.*` | conforme | nenhuma | aprovado |
| ataque/incursão | contrato de ameaças | save e eventos, sem pasta própria | conforme | nenhuma | aprovado |

## 25. Auditoria da geração pelo GitHub

| Requisito | Fonte | Evidência | Resultado | Correção | Estado final |
|---|---|---|---|---|---|
| opcionalidade | seções 2–4 | Eldrath e criação manual permanecem disponíveis | conforme | nenhuma | aprovado |
| fórmula e pesos | seções 8–10 | versão `github-relevance-v1.0.0`; pesos somam 100%; normalização e limites definidos | conforme | nenhuma | aprovado |
| um repositório | regra de único valor | normalizações relativas recebem 0,5 e não dividem por zero | ambiguidade residual para P95 zero | precedência da regra especial explicitada | aprovado após correção |
| dois repositórios | normalização | postos 0 e 1; empates usam posto médio; desempate determinístico | conforme | nenhuma | aprovado |
| métricas constantes | regra de constantes | 0,5 para todos, sem diferença artificial | conforme após explicitação | precedência registrada | aprovado após correção |
| todas ausentes | fórmula e erros | antes não havia resultado explícito para denominador sem componente | incompleto | pontuação `null`, explicação e alternativas manuais definidas | aprovado após correção |
| estrelas extremas | P95 + log | valor limitado antes do log; estrelas não dominam o total | conforme | nenhuma | aprovado |
| projeto novo | maturidade e elegibilidade | idade baixa não exclui; componentes disponíveis são renormalizados | conforme | nenhuma | aprovado |
| projeto antigo ativo | atividade e maturidade separadas | recência e idade não são juízo de valor | conforme | nenhuma | aprovado |
| somente forks | seção 21 | visíveis, identificados e incluíveis explicitamente | conforme | nenhuma | aprovado |
| somente arquivados | seção 22 | visíveis e elegíveis; sem penalidade moral automática | conforme | nenhuma | aprovado |
| poucos/excedentes | seções 19–20 | sem duplicar poucos e sem descartar excedentes silenciosamente | conforme | nenhuma | aprovado |
| edição e congelamento | seções 7, 28 e 30 | associações editáveis; snapshot confirmado congelado; atualização explícita | conforme | nenhuma | aprovado |
| offline e reinício | seções 26, 35 e 36 | sem nova consulta; velocidade não altera resultado | conforme | nenhuma | aprovado |
| privacidade e segurança | seções 23–25 | dados públicos, sem token, clone, execução ou NPC automático | conforme | nenhuma | aprovado |
| acessibilidade | seção 17 | alternativa textual obrigatória ao mapa | conforme | nenhuma | aprovado |

Os testes foram conceituais e abstratos; nenhum perfil real foi consultado e nenhuma fixture foi salva.

## 26. Auditoria de privacidade e segurança

| Requisito | Fonte | Evidência | Resultado | Correção | Estado final |
|---|---|---|---|---|---|
| dados pessoais | contrato GitHub | somente público, consentido e minimizado | conforme | nenhuma | aprovado |
| segredos | contrato GitHub | token, cabeçalhos e identidades desnecessárias excluídos | conforme | nenhuma | aprovado |
| execução | contrato GitHub | sem clone, scripts, workflows ou dependências | conforme | nenhuma | aprovado |
| texto externo | contrato GitHub | não confiável, limitado, sanitizado e nunca instrução | conforme | nenhuma | aprovado |
| visibilidade do jogo | contratos transversal e NPC | origem administrativa e verdade restrita não vazam para personagens | conforme | nenhuma | aprovado |

## 27. Auditoria da documentação pública

| Requisito | Fonte | Evidência | Resultado | Correção | Estado final |
|---|---|---|---|---|---|
| estado público | `README.md` | contratos concluídos, início da construção do mundo e ausência de aplicação | estado antigo após encerramento | atualizado | aprovado após correção |
| referências privadas | `README.md` | não cita diretórios ou arquivos canônicos privados, agentes, prompts ou autoria automatizada | conforme | nenhuma | aprovado |
| ordem de leitura | READMEs internos | checklist → contrato comum → vocabulários → schema → template | faltava consolidação | ordem atualizada | aprovado após correção |

## 28. Inconsistências encontradas

Foram encontrados 12 apontamentos objetivos, agrupados em quatro classes:

| ID | Problema | Ocorrências | Evidência | Estado final |
|---|---|---:|---|---|
| I-01 | contratos especializados citavam versões antigas do GDD | 7 | referências a 1.2 ou 1.3 em contratos posteriores ao GDD 1.4 | aprovado após correção |
| I-02 | prefixos mágicos provisórios no contrato comum | 2 | `school` e `effect` contradiziam `magic_school` e `magic_effect` já finalizados | aprovado após correção |
| I-03 | decisões adiadas do contrato social descreviam contratos já concluídos como futuros | 2 | schemas de NPC/eventos e contratos de criaturas ainda apareciam como próximas atividades | aprovado após correção |
| I-04 | caso-limite de ausência total de métricas no cálculo GitHub não tinha resultado explícito | 1 | todos os componentes indisponíveis deixavam o denominador sem regra | aprovado após correção |

## 29. Correções realizadas

| Problema | Evidência | Fonte canônica | Solução | Arquivos envolvidos |
|---|---|---|---|---|
| versões antigas | sete referências 1.2/1.3 | GDD vigente e hierarquia documental | atualização transacional para GDD 1.5 | contratos de intervenção, sociedade, magia, criaturas, NPC, eventos e ameaças |
| prefixos provisórios | tabela comum divergia do contrato mágico e IDs | `CONTENT_SCHEMA.md` precede, mas o próprio contrato mágico declarava finalização aprovada e o GDD exige IDs de tipo | consolidação de `magic_school` e `magic_effect` no contrato comum | `CONTENT_SCHEMA.md` |
| próximos passos obsoletos | contratos já existentes eram descritos como futuros | GDD 1.4 e inventário da Fase 1 | redação restrita a entidades, estado e implementação realmente futuros | schema social |
| ausência total no GitHub | fórmula sem componente disponível | princípios canônicos de transparência, ausência sem punição, criação manual e Eldrath disponível | pontuação `null`, explicação, sem ordenação e sem divisão por zero; regra de constante ganha precedência | contrato GitHub |

Atualizações transacionais de encerramento, não contadas como inconsistências iniciais: GDD 1.5, fase e próxima atividade, instruções locais não versionadas, README público, manifesto, mapa, estado, ordem de autoria e READMEs internos.

## 30. Decisões deliberadamente adiadas

| Requisito | Fonte | Evidência | Resultado | Correção | Estado final |
|---|---|---|---|---|---|
| vocabulários dependentes do mundo | schemas fundamental, geográfico, social, mágico e saúde | 25 registros catalogados com formato, proprietário e fase | não impedem a identidade geral | centralizados sem inventar valores | adiado explicitamente |
| quantidades não fixadas | GDD e status | categorias marcadas `a definir` | não impedem a fase seguinte | preservadas | adiado explicitamente |
| sobreposição 5 instituições/8 facções | GDD e schema social | GDD não determina inclusão | não impede autoria inicial; classificação possui dois booleanos | preservada para Fase 4 | adiado explicitamente |
| IDs e formatos técnicos | eventos, intervenção e GitHub | dependem de especificação e implementação | não afetam IDs de conteúdo | proprietário futuro registrado | adiado explicitamente |
| fórmulas executáveis | contratos mágico, saúde, NPC e ameaças | estruturas e invariantes existem; parâmetros finais dependem de implementação | não impede autoria estruturada | preservadas | adiado explicitamente |
| interfaces e persistência | todos os contratos | fases futuras explicitamente definidas | programação continua proibida | preservadas | adiado explicitamente |

## 31. Bloqueios

| Requisito | Fonte | Evidência | Resultado | Correção | Estado final |
|---|---|---|---|---|---|
| contradições canônicas abertas | auditoria completa | nenhuma permaneceu após correções determinadas | sem bloqueio | não aplicável | aprovado |
| template não preenchível | comparação schema-template | nenhum | sem bloqueio | não aplicável | aprovado |
| entidade sem proprietário | matriz da seção 12 | nenhuma | sem bloqueio | não aplicável | aprovado |
| ID ou referência sem regra | contratos e convenções | nenhuma para conteúdo da Fase 2 | sem bloqueio | não aplicável | aprovado |

Bloqueios finais: zero.

## 32. Validações automáticas

| Validação | Evidência | Resultado |
|---|---|---|
| estado Git inicial | `git status --short` vazio; branch `main` preservada | aprovado |
| unicidade do GDD | exatamente `Base/GDD.md` | aprovado |
| hash inicial | `B65812E99116B8292DBEFAF7119FAD5B060D75FFEFDA0EADFF27A3CBFA00E973` | aprovado |
| YAML e front matter | manifesto, 26 front matters e 2 templates YAML analisados; sem chave duplicada | aprovado |
| schema e estado de template | 27 especializados em `1.0.0` e `draft`; base genérica reconhecida como exceção editorial | aprovado |
| prefixos de template | todos os 27 especializados correspondem ao tipo | aprovado |
| manifesto versus diretórios | 25 categorias únicas e 25 pastas-folha correspondentes | aprovado |
| schemas versus templates | 11 schemas, 28 templates e nenhuma categoria editável sem contrato/template | aprovado |
| links Markdown | todos os links locais resolvidos | aprovado |
| cercas e títulos | cercas balanceadas e hierarquia válida fora de blocos de código | aprovado |
| placeholders | nenhuma ocorrência real fora de `_templates/` | aprovado |
| conteúdo real | zero arquivo de entidade fora de manifesto, README e `.gitkeep` | aprovado |
| `.gitkeep` | presente somente nas 25 pastas-folha vazias | aprovado |
| código, dependências e assets | nenhum código, dependência ou asset novo | aprovado |
| versões e fases antigas | nenhuma referência operacional obsoleta permaneceu | aprovado |
| whitespace do diff | `git diff --check` sem erro | aprovado |
| hash final do GDD | `28929D79698ACC6BD03C66C699D26A81E782190A5EC2274524B0327101CA64FA` | aprovado |
| cópia temporária | comparação confirmou somente alterações autorizadas de versão e encerramento; cópia removida | aprovado |

## 33. Validações manuais

| Requisito | Fonte | Evidência | Resultado | Correção | Estado final |
|---|---|---|---|---|---|
| hierarquia canônica | todas as fontes | divergências inferiores corrigidas sem alterar decisões superiores | conforme | registradas | aprovado após correção |
| semântica schema-template | 28 pares/grupos | campos obrigatórios, opcionais, estado, referências e corpo compatíveis | conforme | nenhuma | aprovado |
| propriedade | matriz da seção 12 | proprietário estático, inicial, atual e derivado definido | conforme | nenhuma | aprovado |
| causalidade e conhecimento | contratos transversal, NPC e eventos | separações e origens preservadas | conforme | nenhuma | aprovado |
| ameaças | criatura, eventos e ameaças | agregação, ataque e incursão coerentes | conforme | nenhuma | aprovado |
| fórmula GitHub | oito cenários solicitados e casos de constante/ausência | comportamento definido após correção | conforme | regra de borda adicionada | aprovado após correção |
| privacidade e documentação pública | contrato GitHub e README | limites e linguagem pública preservados | conforme | estado atualizado | aprovado após correção |

## 34. Critérios para encerramento

| Critério | Evidência | Resultado | Estado final |
|---|---|---|---|
| contratos necessários existem | 11 schemas + contrato comum cobrem 37 requisitos | atendido | aprovado |
| templates compatíveis | 28 inventariados e validados | atendido | aprovado |
| IDs e referências consistentes | convenções, prefixos e caminhos consolidados | atendido | aprovado após correção |
| proprietários definidos | matriz completa | atendido | aprovado |
| conteúdo e estado separados | contratos e templates | atendido | aprovado |
| vocabulários com proprietário | 37 catalogados | atendido | aprovado após correção |
| adiamentos não bloqueiam autoria | proprietário e fase registrados | atendido | adiado explicitamente |
| nenhuma contradição aberta | zero bloqueio | atendido | aprovado |
| nenhuma entidade real | 25 categorias vazias | atendido | aprovado |
| validações passam | seções 32 e 33 | atendido | aprovado |

## 35. Conclusão

A auditoria editorial final foi aprovada. As 12 inconsistências comprovadas foram corrigidas sem reestruturação ampla, sem alteração de lore e sem decisão arbitrária. Os contratos, templates, vocabulários, caminhos, propriedades e limites de estado permitem iniciar a autoria real do mundo em tarefas específicas.

## 36. Estado final da fase

Fase 1 — Contratos editoriais e templates: concluída, consolidada e explicitamente encerrada. GDD final: versão 1.5. Entidades reais existentes: zero. Programação iniciada: não.

## 37. Próxima fase

Próxima fase: Fase 2 — Fundamentos do mundo. Estado: não iniciada. Próxima atividade autorizável: identidade geral de Eldrath, sem antecipar calendário, idiomas, culturas, reino ou qualquer outra entidade fora do escopo de uma tarefa específica.
