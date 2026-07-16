# Sistema mágico — schemas editoriais

**Versão do contrato especializado:** `1.0.0`

**Contrato comum:** [`CONTENT_SCHEMA.md`](../CONTENT_SCHEMA.md), versão `1.0.0`

**Estado:** contratos de `magic_school`, `spell`, `ritual`, `magic_effect` e `artifact` concluídos; entidades reais não iniciadas.

Este documento especializa o contrato editorial comum para o sistema mágico. Ele define representação autoral, propriedade canônica, estruturas mecânicas, referências e validação manual. Não é schema executável, JSON Schema, DSL, código, conteúdo real ou lore de Eldrath.

Em caso de conflito, [`Base/GDD.md`](../../../Base/GDD.md), versão `1.5`, permanece a fonte canônica. O sistema precisa funcionar de forma completa, determinística e validável sem IA generativa.

## 1. Objetivo

Definir como escolas e subescolas, magias, rituais, efeitos mágicos reutilizáveis e artefatos serão escritos sem depender da interpretação de prosa livre. Magia é simultaneamente conhecimento, capacidade, técnica, custo, risco, evidência, poder social, objeto de ensino, objeto de pesquisa e objeto de regulação.

Todo efeito mecânico precisa de representação estruturada. O corpo Markdown explica história, interpretação e contexto; ele não calcula custos, seleciona alvos, aplica efeitos, determina legalidade nem altera estado.

## 2. Escopo, limites e dependências

O contrato cobre:

- taxonomia de escolas e subescolas;
- técnicas individuais reproduzíveis;
- procedimentos rituais com papéis e etapas;
- definições reutilizáveis de efeito;
- objetos mágicos únicos ou narrativamente significativos;
- custos, alcance, duração, alvos, risco, falha e corrupção;
- aprendizado, domínio, variantes e descoberta;
- sinais, resíduos, evidências e percepção;
- integração com facções, religiões, leis, itens, recursos, profissões, Intervenções do Arquiteto e estado da campanha.

Dependências editoriais:

1. [contrato editorial comum](../CONTENT_SCHEMA.md);
2. [entidades fundamentais](FOUNDATIONAL_ENTITIES.md), para unidades, tempo, reino e moedas;
3. [entidades geográficas](GEOGRAPHY_ENTITIES.md), para locais, assentamentos, regiões e ambiente;
4. [economia material](MATERIAL_ECONOMY_ENTITIES.md), para `quantity`, `money`, recursos, itens e profissões;
5. [intervenção, percepção e conhecimento](INTERVENTION_PERCEPTION_AND_KNOWLEDGE.md), para causalidade, evidência e conhecimento limitado;
6. [sociedade, instituições e lei](SOCIETY_INSTITUTIONS_AND_LAW_ENTITIES.md), para facções, religiões e legalidade contextual.

Não são criados nesta fase: entidades reais, vocabulário mágico de Eldrath, fórmulas, linguagem de workflow, instâncias de efeito, instâncias de item, save, banco, API, código, assets ou validação automatizada.

## 3. Termos

- **Escola mágica:** domínio conceitual, conjunto de princípios, métodos e relações taxonômicas.
- **Subescola:** a mesma entidade `magic_school.*`, com `parent_school_id` preenchido.
- **Facção mágica:** organização `faction.*` responsável por membros, cargos, ensino institucional, pesquisa e poder social.
- **Magia:** técnica individual reproduzível de conjuração relativamente delimitada.
- **Ritual:** procedimento mágico estruturado por preparação, papéis, etapas, condições e interrupções.
- **Efeito mágico:** definição mecânica reutilizável `magic_effect.*`.
- **Aplicação de efeito:** referência a uma definição de efeito com parâmetros editoriais estruturados.
- **Instância de efeito:** aplicação já resolvida no estado da campanha.
- **Artefato:** objeto mágico único, nomeado, singular, historicamente significativo ou persistentemente relevante.
- **Item encantado:** definição `item.*` comum ou reproduzível; não é artefato automaticamente.
- **Corrupção:** estado acumulável da campanha, com fontes e consequências estruturadas.

## 4. Prefixos, caminhos e formatos

| Entidade | Prefixo | Diretório futuro | Arquivo |
|---|---|---|---|
| escola ou subescola | `magic_school.` | `content/worlds/eldrath/magic/schools/` | `{slug}.md` |
| magia | `spell.` | `content/worlds/eldrath/magic/spells/` | `{slug}.md` |
| ritual | `ritual.` | `content/worlds/eldrath/magic/rituals/` | `{slug}.md` |
| efeito mágico reutilizável | `magic_effect.` | `content/worlds/eldrath/magic/effects/` | `{slug}.md` |
| artefato | `artifact.` | `content/worlds/eldrath/magic/artifacts/` | `{slug}.md` |

Todos usam Markdown com front matter YAML, um arquivo por entidade, `schema_version: "1.0.0"` e `content_status: draft` ao iniciar a autoria. Os prefixos `magic_school.` e `magic_effect.` finalizam as categorias anteriormente apenas planejadas como `school` e `effect` no contrato comum.

Escolas e subescolas compartilham pasta, prefixo e template. Não existe pasta, prefixo ou lista aninhada separada para subescolas. Também não existe pasta ou template para `effect_instance` ou corrupção.

## 5. Propriedade canônica

| Informação | Proprietário canônico | Não deve ser duplicada em |
|---|---|---|
| princípios, domínio, métodos e taxonomia de uma escola | `magic_school.*` | facção mágica, magia ou ritual |
| membros, cargos, liderança, sede, tesouro, ensino e pesquisa institucionais | `faction.*` | escola mágica |
| técnica, requisitos, custos, alvos, efeitos e domínio possível de uma magia | `spell.*` | NPC, facção ou escola |
| procedimento, papéis, etapas, interrupções e resultado ritual | `ritual.*` | tag de magia ou prosa livre |
| regra mecânica reutilizável | `magic_effect.*` | cópias integrais em magia, ritual, item ou artefato |
| aplicação atual de efeito | save da campanha | `magic_effect.*` ou conteúdo estático |
| definição de item encantado comum | `item.*` | artefato sem identidade própria |
| identidade singular, poderes e história de artefato | `artifact.*` | `item.*` ou `item_instance` concorrente |
| estado atual de artefato | save da campanha | definição estática do artefato |
| legalidade efetiva | leis aplicáveis e estado da campanha | campo global simples em entidade mágica |
| estágio atual de domínio de um NPC | futuro `npc.*` e save | definição da magia |
| lista de ensinamentos de uma facção | consulta derivada das fontes de aprendizagem | lista completa concorrente em `faction.*` |

## 6. Regras compartilhadas

As cinco entidades usam os campos comuns `schema_version`, `id`, `name`, `content_status`, `tags`, `aliases`, `summary`, `references`, `art` e `notes`. IDs completos referenciam entidades; chaves locais estáveis terminam em `_key` e só são válidas no contexto que as define.

Campo omitido significa opcional ou não aplicável; `null` significa aplicável, porém desconhecido; `[]` afirma ausência conhecida. String vazia é proibida. Placeholders só existem em `_templates/` e não podem permanecer em conteúdo `approved`.

### 6.1 Quantidade, tempo e dinheiro

Quantidade reutiliza exatamente o contrato de economia material:

```yaml
quantity:
  value: null
  unit_key: null
```

Distância, duração, área quantitativa, materiais, recursos, cargas e magnitudes mensuráveis usam `value` e `unit_key`. Não se criam campos paralelos como `distance_meters`, `duration_hours`, `amount` ou `unit`.

Quando houver dinheiro, usa-se `money: { amount, currency_key }`. Recorrência econômica usa `period_key`; duração física continua usando uma quantidade temporal com `unit_key`.

### 6.2 Aplicação de efeito e parâmetros

Magias, rituais, itens encantados e artefatos referenciam efeitos por `magic_effect_id`. Uma aplicação possui `application_key` local, alvo contextual, parâmetros e condições. Não copia a definição completa.

Cada parâmetro declara `parameter_key` e exatamente uma forma de valor entre `number_value`, `boolean_value`, `key_value`, `entity_id` e `quantity`. O parâmetro precisa existir em `magic_effect.accepted_parameters` e respeitar tipo, unidade, faixa e obrigatoriedade definidos ali.

```yaml
effect_applications:
  - application_key: null
    magic_effect_id: null
    target_binding_key: null
    parameters: []
    condition_keys: []
    trigger_keys: []
```

Essa estrutura é dado editorial, não expressão executável. Um ciclo entre efeitos é inválido quando não possui condição de término explícita.

### 6.3 Custos, materiais, catalisadores e ferramentas

Uma entrada de custo possui:

- `cost_key` estável no arquivo;
- `category_key`: `mana`, `fatigue`, `health`, `time`, `concentration`, `memory`, `reputation`, `religious_favor`, `condition`, `resource`, `material`, `item` ou `environment`;
- `bearer_key`, distinguindo conjurador, alvo, participante específico, conjunto de participantes ou outro portador autorizado;
- `timing_key`, distinguindo imediato, por período, na conclusão, após gatilho ou diferido;
- `resource_id`, `item_id`, `quantity`, `condition_key` e `mechanical_state_key`, conforme a categoria;
- `consumption_mode_key`, distinguindo `consumed`, `preserved` e `not_applicable`;
- `deferred_trigger_key`, quando o custo for diferido;
- condições e notas editoriais.

Todo custo narrativo precisa apontar para estado mecânico verificável. `resource_id` usa `resource.*`; `item_id` usa `item.*`. A execução futura resolve quantidades e instâncias no save, sem referenciar uma `item_instance` específica na definição estática.

Estruturas especializadas preservam a diferença:

- `materials`: recursos ou itens consumidos;
- `catalysts`: recursos ou itens necessários e preservados;
- `required_tools`: definições `item.*` necessárias e preservadas;
- `environmental_conditions`: condições de local, clima, tempo ou fenômeno;
- `costs`: alterações mecânicas aplicadas aos portadores, inclusive custos diferidos.

### 6.4 Alcance

`range` é uma estrutura discriminada:

```yaml
range:
  mode_key: null
  distance:
    value: null
    unit_key: null
  connection_key: null
  global_permission_key: null
  condition_keys: []
```

`mode_key` aceita `self`, `touch`, `same_location`, `line_of_sight`, `distance`, `connection` ou `global`. Somente `distance` preenche `distance`; somente `connection` preenche `connection_key`; `global` exige autorização explícita em `global_permission_key`. Os demais modos mantêm esses campos nulos.

### 6.5 Duração e concentração

`duration` também é discriminada:

```yaml
duration:
  mode_key: null
  quantity:
    value: null
    unit_key: null
  end_condition_keys: []
  dispel_rule_keys: []
```

`mode_key` aceita `instantaneous`, `time_quantity`, `while_concentrating`, `until_condition`, `permanent` ou `until_dispelled`. `time_quantity` exige quantidade temporal; `until_condition` exige condição de término; `until_dispelled` exige regra de dissipação. `permanent` significa persistente até que uma regra explícita altere o estado, não irreversibilidade absoluta.

`concentration` declara se concentração é exigida, quantos vínculos simultâneos são permitidos, condições de manutenção e consequências estruturadas de ruptura. O estado atual da concentração pertence ao save.

### 6.6 Alvos e área

`targeting.allowed_category_keys` pode incluir `caster`, `npc`, `creature`, `item`, `artifact`, `resource`, `location`, `settlement`, `region`, `faction`, `memory`, `spell`, `magic_effect`, `event` e `area`. Cada entidade declara apenas as categorias realmente válidas.

`targeting` também possui `minimum_targets`, `maximum_targets`, `selection_rule_key`, `condition_keys` e `area`. `minimum_targets` e `maximum_targets` são inteiros não negativos; quando ambos forem conhecidos, o mínimo não supera o máximo.

`area` possui `shape_key`, dimensões por `quantity`, origem, propagação, exclusões e condições. Não se mistura string livre e número no mesmo campo.

### 6.7 Risco, falha e determinismo

Riscos e falhas usam estruturas verificáveis com:

- chave local;
- condições;
- `base_probability` na escala canônica `0`–`1`, coerente com o exemplo probabilístico do GDD;
- modificadores editoriais estruturados;
- `severity_key`;
- aplicações de efeito;
- exposição e evidência;
- corrupção;
- regra de alvo alternativo;
- área afetada;
- possibilidades de mitigação;
- `random_stream_key` nomeado.

Probabilidade desconhecida usa `null`, não zero. Nenhuma segunda escala probabilística é permitida. Modificadores não são expressões; usam operações editoriais do contrato econômico. Toda aleatoriedade futura precisa ser reproduzível por semente, estado, ordem e fluxo pseudoaleatório nomeado.

Falha não significa ausência de efeito. Resultados reduzidos, alvos incorretos, exposição, resíduo, dano, corrupção, anomalia, alteração de memória e rumor usam aplicações de efeito ou estruturas de evidência, nunca apenas prosa.

### 6.8 Corrupção

Conteúdo estático pode definir fontes, magnitude possível, sintomas, limiares conceituais, efeitos, resistências, tratamentos e evidências. Uma aplicação de corrupção usa magnitude estruturada e referencia efeitos quando houver consequência mecânica.

O save possui valor atual, fontes acumuladas, limiar atual, sintomas ativos, efeitos ativos e histórico. Não existe pasta `corruption/`; corrupção não é apenas texto narrativo.

### 6.9 Sinais, resíduos, evidências e percepção

`sensory_signals` e `evidence_profiles` podem declarar luz, som, odor, calor, frio, movimento, alteração visível, sensação, resíduo, marca, mudança de memória, anomalia ou detecção que exige habilidade ou magia. Cada entrada possui chave, modalidade, intensidade, alcance, duração, persistência, condições de detecção e referência a efeito quando houver comportamento mecânico.

Produzir evidência não concede identificação automática. Um NPC só conhece o que percebeu, inferiu, recebeu por comunicação ou investigou. Ver uma manifestação não revela automaticamente nome, escola, conjurador, intenção, causa real ou origem de uma Intervenção do Arquiteto.

### 6.10 Aprendizado e domínio

As etapas canônicas são, nesta ordem:

1. `unknown` — desconhecida;
2. `theoretical` — conhecida teoricamente;
3. `studying` — em estudo;
4. `unstable` — instável;
5. `usable` — utilizável;
6. `mastered` — dominada;
7. `magisterial` — magistral;
8. `personal_variant` — variante pessoal.

A definição de magia ou ritual registra requisitos, fatores, progressão possível e fontes iniciais. O NPC e o save registram estágio atual, progresso, professor, estudo, tentativas, falhas e variante pessoal.

Fontes de aprendizagem usam `source_key`, `source_type_key`, `source_entity_id`, condições de acesso e proveniência. Tipos podem representar facção, professor NPC, item, artefato, local, evento, pesquisa, tradição religiosa ou descoberta autônoma. Um NPC só aparece quando for fonte editorial específica, não em lista de professores atuais.

A direção canônica de ensinamento parte da magia ou ritual para a fonte inicial. A página da facção deriva a lista de ensinamentos; não há listas completas nos dois lados.

### 6.11 Regulação e legalidade

Entidades mágicas podem registrar `regulation.category_keys`, `regulation.magic_tag_keys`, requisitos conceituais de licença, riscos e observações editoriais. Esses dados classificam o objeto regulável; não declaram legalidade efetiva.

Legalidade depende de lei aplicável, jurisdição, vigência, sujeitos, objetos, condições, exceções, licenças, precedência e estado da campanha. Campos globais como `legal`, `illegal`, `licensed` ou `forbidden` são proibidos nas entidades mágicas.

## 7. `magic_school` — escola e subescola

### 7.1 Finalidade e campos

`magic_school.*` representa domínio conceitual e taxonomia. Seus campos especializados são:

| Campo | Estrutura e propriedade |
|---|---|
| `parent_school_id` | `magic_school.*` ou `null`; identifica subescola |
| `principles` | princípios por chave, nome editorial e resumo |
| `domain` | categorias e limites conceituais |
| `related_phenomena` | fenômenos por chaves e referências permitidas |
| `power_sources` | fontes conceituais e condições |
| `methods` | métodos de prática, estudo ou manifestação |
| `affinities` | afinidades e relações estruturadas |
| `related_aptitude_keys` | competências ou aptidões relacionadas |
| `typical_cost_profiles` | categorias e padrões típicos, sem custo de conjuração concreta |
| `typical_risk_profiles` | riscos típicos e condições |
| `corruption_relation` | fontes, resistência e sintomas conceituais |
| `common_signals` | sinais sensoriais típicos |
| `common_evidence` | evidências típicas, sem ocorrência atual |
| `school_relations` | relações direcionais com outras escolas |
| `regulation` | categorias e tags regulatórias, sem legalidade global |
| `origin` | descrição editorial, data, período e evento quando conhecidos |
| `editorial_history` | decisões e revisões da taxonomia, sem reescrever história do mundo |
| `deferred_decisions` | decisões específicas adiadas |

Uma escola não possui membros, líder, professores atuais, sede institucional, cargos, tesouro ou decisões políticas. Esses dados pertencem a `faction.*`.

### 7.2 Subescolas e hierarquia

Uma subescola é `magic_school.*` com `parent_school_id` preenchido. A escola pai não mantém lista aninhada de filhas; descendentes são derivados consultando `parent_school_id`.

Uma escola não pode ser sua própria pai, e a cadeia de ascendência não pode formar ciclo. Alterar a hierarquia de uma escola aprovada exige revisão de todas as referências afetadas.

### 7.3 Relações entre escolas

Cada relação possui `relation_key`, `target_magic_school_id`, `relation_type_key`, intensidade ou relevância, fundamento, condições, `expected_symmetry` e observações.

`relation_type_key` pode representar `synergy`, `opposition`, `dependency`, `derivation`, `overlap`, `incompatibility`, `amplification` ou `neutralization`. Relações podem ser direcionais. Quando uma relação for genuinamente simétrica, registra-se uma única entrada no arquivo cujo ID seja lexicograficamente menor; a consulta deriva a inversa.

## 8. `spell` — magia

### 8.1 Finalidade e campos

`spell.*` representa técnica individual reproduzível. Seus campos especializados abrangem:

- `primary_school_id`: exatamente um `magic_school.*`;
- `secondary_school_ids`: zero ou mais `magic_school.*`;
- `subschool_ids`: zero ou mais `magic_school.*` cujo `parent_school_id` esteja preenchido;
- `parent_spell_id`: `spell.*` ou `null` para variante canônica;
- origem, criador conhecido, evento de descoberta e ancestralidade mágica;
- raridade, dificuldade, requisitos e parâmetros aceitos;
- custos, materiais consumidos, catalisadores, ferramentas e condições ambientais;
- tempo de conjuração, alcance, área, alvos, número de alvos, duração e concentração;
- aplicações de efeitos, intensidade e parâmetros;
- riscos, falhas, corrupção, sinais sensoriais, resíduos e evidências;
- contramedidas;
- formas e fontes iniciais de aprendizagem;
- progressão de domínio;
- variantes canônicas relacionadas;
- regulação, tags, lore editorial, assets opcionais e decisões adiadas.

Escolas não mantêm lista inversa de magias. A escola principal precisa ser única; as listas secundária e de subescolas não repetem a principal nem possuem duplicatas.

Não pertencem ao arquivo: NPCs que atualmente conhecem a magia, domínio atual, professores atuais completos, conjurações atuais ou efeitos atualmente aplicados.

### 8.2 Magia versus ritual

Uma magia é uma técnica de conjuração relativamente delimitada. Um ritual possui orquestração explícita: preparação, papéis, participantes, materiais organizados, condições temporais e espaciais, etapas, pontos de interrupção e resultado acumulado.

Tempo longo de conjuração, sozinho, não transforma magia em ritual. A tag `ritual` não substitui `ritual.*`. Uma magia pode ser requisito de um ritual sem incorporar o procedimento ritual.

### 8.3 Variantes e descoberta de campanha

Uma variante canônica com comportamento mecanicamente distinto e reutilizável recebe outro `spell.*` e aponta `parent_spell_id` para sua base. A magia pai não mantém lista inversa de variantes.

Variante pessoal pertence ao domínio do NPC no save. Ela só se torna conteúdo estático por ação editorial explícita, validação, ID sem colisão e revisão.

Magia descoberta durante campanha pertence inicialmente ao save ou a uma sobreposição futura de campanha, possui origem causal e precisa de validação. Ela não reescreve silenciosamente o pacote estático. O formato dessa sobreposição permanece adiado.

## 9. `ritual` — procedimento mágico

### 9.1 Finalidade e campos

`ritual.*` representa um procedimento estruturado. Seus campos especializados abrangem:

- escolas, origem, propósito e dificuldade;
- preparação e duração estimada;
- local necessário, condições ambientais e temporais;
- participantes mínimos e máximos;
- papéis locais estáveis e requisitos por papel;
- magias, competências, materiais consumidos, catalisadores, ferramentas e artefatos necessários;
- etapas ordenadas, condições de avanço, interrupções e retomada;
- efeitos parciais e resultado de sucesso;
- aplicações de efeitos, custos, riscos, falhas e corrupção;
- sinais, resíduos, evidências e contramedidas;
- formas e fontes iniciais de aprendizagem;
- regulação, tags, lore editorial, assets opcionais e decisões adiadas.

Papéis usam `role_key` local; não são automaticamente profissão, cargo de facção ou NPC. Um requisito por papel pode referenciar profissão, competência ou condição sem fundir os conceitos.

### 9.2 Etapas

Cada etapa possui:

- `step_key` estável;
- `order` inteiro positivo e único;
- nome editorial;
- `responsible_role_key` existente no ritual;
- ação exigida em descrição editorial curta;
- duração quantitativa;
- requisitos e recursos;
- condição de sucesso e condição de falha;
- aplicações de efeito parcial;
- `interruptible` e `resumable`;
- regras editoriais de retomada.

As etapas são dados de autoria, não linguagem executável de workflow. Ordens não se repetem, referências de papel resolvem localmente e a retomada não pode ignorar o estado produzido pelas etapas já concluídas.

## 10. `magic_effect` — definição reutilizável

### 10.1 Finalidade, categorias e campos

`magic_effect.*` define comportamento e parâmetros possíveis. Categorias estruturais podem representar dano, cura, remoção ou aplicação de condição, modificação de atributo ou relação, alteração de percepção, barreira, revelação, ocultação, movimento, invocação, transformação, estímulo, resíduo, resistência ou corrupção. Essas categorias são vocabulário estrutural, não conteúdo de Eldrath.

Campos especializados:

| Campo | Estrutura e propriedade |
|---|---|
| `effect_category_key` | categoria estrutural |
| `valid_target_category_keys` | categorias de alvo permitidas |
| `accepted_parameters` | chave, tipo, obrigatoriedade, unidade, faixa e valores permitidos |
| `unit_key` | unidade padrão quando aplicável |
| `allowed_duration_mode_keys` | modos de duração aceitos |
| `intensity_rule` | escala, limites e regra editorial de intensidade |
| `stacking` | modo, máximo, renovação e grupo de exclusividade |
| `application_conditions` | condições estruturadas |
| `termination_conditions` | condições de término |
| `triggers` | gatilhos editoriais, sem expressão executável |
| `modifiers` | modificadores estruturados |
| `resistance` | categorias, fontes e resultado de resistência |
| `immunity` | categorias e condições de imunidade |
| `dissipation` | meios e condições de dissipação |
| `countermeasures` | contramedidas referenciáveis |
| `observability` | condições de observação e identificação |
| `sensory_signals` | sinais possíveis |
| `evidence_profiles` | evidências possíveis |
| `consequences` | aplicações adicionais ou referências estruturadas |
| `regulation` | categorias e tags regulatórias |
| `deferred_decisions` | decisões específicas adiadas |

`stacking.mode_key`, renovação, exclusividade e limites precisam ser explícitos. Um efeito não mantém lista inversa de todas as magias, rituais, itens ou artefatos que o usam.

### 10.2 Definição versus instância

A definição `magic_effect.*` descreve comportamento e parâmetros aceitos. A instância aplicada pertence ao save e registra fonte, magia ou ritual originador, alvo, intensidade, parâmetros resolvidos, início, término, duração restante, empilhamento, estado, evidências e evento de aplicação.

Não existe pasta nem template de instância. Efeito atual nunca é gravado no arquivo de definição.

## 11. `artifact` — objeto mágico singular

### 11.1 Finalidade e campos

`artifact.*` representa objeto único, nomeado, historicamente significativo, mecanicamente singular ou persistentemente relevante. Seus campos abrangem:

- forma material e `base_item_id` opcional para `item.*`;
- origem, criador, data ou período e evento de criação;
- escolas;
- aplicações de efeitos, poderes e ativações;
- custos, cargas possíveis e regeneração;
- condições, requisitos e vínculo;
- consciência, quando aplicável;
- riscos, corrupção e falhas;
- sinais, resíduos, evidências e contramedidas;
- destruição e reparo;
- formas e fontes de aprendizagem;
- segredos de conteúdo;
- regulação, tags, lore editorial e assets opcionais;
- `initial_state` mínimo e decisões adiadas.

Ativações usam chave local, gatilho, requisitos, alvos, custos, duração, aplicações de efeito, riscos e condições. Poderes mecânicos sempre referenciam `magic_effect.*`; prosa não substitui a aplicação.

### 11.2 Artefato versus item

Item encantado comum ou reproduzível permanece `item.*`. Artefato não é sinônimo de todo item mágico.

O artefato pode apontar `base_item_id` para sua forma material genérica. A direção inversa é derivada; `item.*` não mantém `artifact_id`. A identidade, origem, poderes, riscos, segredos e história singular permanecem no artefato.

Um artefato não possui simultaneamente uma `item_instance` concorrente representando o mesmo objeto único. Sua definição canônica e seu estado persistente de campanha formam uma única identidade.

### 11.3 Estado inicial e estado atual

`initial_state` pode semear localização, portador, proprietário reconhecido, condição, cargas, vínculo, conhecimento público, segredos inicialmente descobertos e notas, sempre identificados como valores iniciais.

Depois de iniciar a campanha, o save possui localização atual, portador atual, proprietário reconhecido, condição atual, cargas atuais, vínculo atual, efeitos ativos, conhecimento público, segredos descobertos e histórico de uso. Esses valores não são mantidos como propriedades estáticas permanentes.

## 12. Integrações canônicas

### 12.1 Facções

Toda academia, ordem, círculo, guilda, instituição de pesquisa ou autoridade licenciadora é `faction.*`. A facção pode registrar relações com escolas, política de ensino, pesquisa, segredo, acesso, capacidade de licenciamento e categorias mágicas controladas.

Fontes iniciais de aprendizagem ficam na magia ou ritual. Ensinamentos oferecidos por uma facção são derivados dessas referências. Ocupantes, professores e alunos atuais pertencem aos NPCs e ao save.

### 12.2 Religiões

`religion.*` pode registrar postura doutrinária sobre escolas, práticas, rituais, artefatos, formas de aprendizagem e corrupção. Essa postura não é lei. Organizações religiosas continuam sendo `faction.*`.

### 12.3 Leis

`law.*` pode alcançar IDs `magic_school.*`, `spell.*`, `ritual.*` e `artifact.*`, categorias de entidade e tags mágicas por regras de objeto estruturadas. A aplicabilidade efetiva permanece derivada por jurisdição, vigência, condições, exceções, licenças e estado.

### 12.4 Itens e recursos

Custos e materiais usam `resource.*` e `item.*`. Material consumido, catalisador preservado e ferramenta necessária são papéis diferentes. Definições estáticas não apontam para `item_instance` específica.

Item encantado comum pode referenciar `magic_school.*` e aplicações de `magic_effect.*` no contrato de item. Um artefato usa `base_item_id` e identidade própria; o item não mantém lista inversa de artefatos.

### 12.5 Profissões

Requisitos mágicos de `profession.*` podem referenciar `magic_school.*`, `spell.*`, `ritual.*`, afinidades e condições. Profissão não concede automaticamente conhecimento, domínio, licença ou filiação. Cargo institucional continua pertencendo a `faction.roles`.

### 12.6 Intervenções do Arquiteto

Intervenções podem produzir sinais, evidências ou efeitos apenas por capacidades autorizadas e comandos registrados. A causa real permanece restrita. Uma manifestação percebida não concede identificação automática, e nenhum efeito altera estado fora da cadeia comando → evento → efeito → evidência → percepção → consequência.

## 13. Conteúdo estático, estado inicial, campanha e derivados

### Conteúdo estático

Define identidade, taxonomia, capacidades, custos possíveis, efeitos, regras, riscos, aprendizado, regulação classificatória e referências.

### Estado inicial

Somente valores mutáveis necessários para semear a campanha ficam sob `initial_state`. O uso principal neste conjunto é o estado inicial de artefato. Esses valores são copiados ao save e não são atualizados no arquivo.

### Estado atual da campanha

Inclui conjurações, rituais em andamento, participantes, custos pagos, efeitos aplicados, corrupção atual, domínio de NPC, pesquisa, disponibilidade de ensino, estado de artefato, legalidade efetiva e descobertas de campanha.

### Campos derivados

São derivados e não mantidos manualmente:

- subescolas de uma escola;
- magias de uma escola;
- variantes filhas de uma magia;
- usuários, professores e instituições ligados a magia;
- ensinamentos de uma facção;
- entidades que usam um efeito;
- artefatos baseados em um item;
- legalidade efetiva;
- estado atual de artefato;
- efeitos ativos e corrupção atual.

## 14. IA generativa e determinismo

IA generativa pode ajudar a propor ou apresentar lore sujeito a revisão, mas não pode decidir efeitos, custos, alvos, probabilidades, corrupção, legalidade, estado, domínio, sucesso ou validade mecânica.

Toda seleção probabilística futura usa fluxo pseudoaleatório nomeado. Mesma versão, conteúdo, semente, configuração, estado e ordem de comandos precisa produzir o mesmo resultado. Texto opcional não participa da resolução.

## 15. Invariantes

1. Toda magia possui exatamente uma escola principal válida.
2. Escola não é facção e nunca possui membros, líder, professores, cargos ou tesouro.
3. Subescola usa `magic_school.*`, possui `parent_school_id` e não forma ciclo.
4. Aplicação de efeito referencia definição `magic_effect.*` existente.
5. Instância de efeito não pertence ao conteúdo estático.
6. Artefato único não possui duas identidades concorrentes como artefato e `item_instance`.
7. Item comum ou encantado reproduzível não é automaticamente artefato.
8. Todo custo narrativo possui representação mecânica verificável.
9. Material consumido, catalisador preservado e ferramenta necessária permanecem distintos.
10. Alcance quantitativo usa `quantity.value` e `unit_key`.
11. Duração quantitativa usa `quantity.value` e `unit_key`.
12. Legalidade efetiva é derivada das leis e do estado, nunca de enum global na magia.
13. Conhecimento mágico não surge sem fonte válida.
14. Afinidade não concede automaticamente conhecimento ou domínio.
15. Professores e conhecedores atuais não ficam na definição da magia.
16. Ocupantes, professores e alunos atuais não ficam na facção estática.
17. Efeito atual, conjuração atual e ritual em andamento pertencem ao save.
18. Toda aleatoriedade futura é reproduzível por fluxo nomeado.
19. Evidência mágica não concede identificação automática.
20. Ausência de arte não invalida conteúdo.

Invariantes adicionais: referências usam IDs; listas inversas são derivadas; probabilidades usam apenas `0`–`1`; nenhum efeito mecânico existe somente na prosa; uma magia não substitui ritual por tag; e IA nunca participa da resolução.

## 16. Validação manual

Antes de encaminhar conteúdo futuro para revisão:

- conferir caminho, slug, prefixo, `schema_version`, `content_status` e campos comuns;
- validar YAML, `null`, listas vazias, booleanos, números e ausência de strings vazias;
- validar referências por categoria e ausência de nomes usados como chaves;
- conferir hierarquia e ausência de ciclo em escolas;
- conferir escola principal única e listas sem duplicata;
- conferir que escola não contém dados institucionais;
- distinguir magia de ritual e validar papéis, ordens e etapas;
- validar toda aplicação contra a definição de efeito e seus parâmetros;
- confirmar ausência de instâncias de efeito em conteúdo;
- conferir custos, materiais, catalisadores, ferramentas e portadores;
- validar `unit_key`, `currency_key`, quantidades e períodos aplicáveis;
- conferir discriminação de alcance, duração, alvos e área;
- validar probabilidades `0`–`1`, modificadores, severidade e fluxo pseudoaleatório;
- conferir corrupção estruturada e separada do valor atual;
- conferir sinais, resíduos, evidências e limites de percepção;
- confirmar fontes de aprendizagem e ausência de conhecedores atuais;
- conferir variantes canônicas e ausência de variantes pessoais estáticas automáticas;
- confirmar legalidade contextual e ausência de enum global simples;
- distinguir item encantado comum de artefato e confirmar direção `artifact.base_item_id`;
- conferir `initial_state` de artefato e ausência de estado atual no arquivo;
- confirmar ausência de listas inversas manuais;
- confirmar corpo Markdown coerente e sem mecânica concorrente;
- confirmar ausência de placeholders em `approved`;
- confirmar funcionamento completo sem IA e sem arte;
- confirmar que nenhuma entidade, save, asset, DSL, código ou schema executável foi criado pelo contrato.

## 17. Decisões adiadas

Permanecem deliberadamente adiados:

- entidades, nomes, lore e vocabulários mágicos reais de Eldrath;
- valores, custos, unidades, probabilidades, dificuldades e escalas de intensidade concretos;
- enum final de categorias de efeito, alvo, risco, falha, corrupção, evidência e regulação;
- fórmulas de mana, resistência, concentração, dissipação, empilhamento e domínio;
- quantidade de rituais e efeitos, que continua `a definir`;
- sobreposição entre as cinco instituições mágicas e as oito facções principais;
- catálogo de licenças, leis, sanções e jurisdições mágicas reais;
- modelo persistente de conjuração, ritual em andamento, efeito aplicado, corrupção, pesquisa e artefato;
- formato da sobreposição de conteúdo descoberta em campanha e política de promoção editorial;
- validação automatizada, JSON Schema, banco, API, interface e implementação;
- assets, prompts de imagem e direção visual.
