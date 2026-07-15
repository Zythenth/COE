# Contrato editorial comum de conteúdo

**Versão do contrato:** `1.0.0`  
**Estado:** contrato comum concluído; schemas fundamentais, geográficos e de economia material e contrato conceitual de intervenção concluídos; Fase 1 em andamento.

## Objetivo

Este documento define o contrato editorial compartilhado por todos os arquivos de conteúdo de Eldrath: formato, identidade, referências, semântica de valores, revisão e verificação manual. Ele não substitui os schemas especializados futuros de NPCs, regiões, assentamentos, facções, magias, eventos ou qualquer outra entidade.

Em caso de conflito sobre o mundo, [`Base/GDD.md`](../../Base/GDD.md) permanece a fonte canônica. Este contrato define como registrar conteúdo sem antecipar as regras específicas de cada categoria.

## Escopo e limites

- `content/` conterá as definições iniciais autorais: entidades, dados estruturados, lore e relações que existem antes de uma campanha.
- Lore complementa os dados estruturados; não os contradiz nem substitui dados mecânicos necessários.
- O estado futuro da simulação — acontecimentos, mutações, saves e histórico de campanha — não pertence a `content/`. `data/` só será criado na etapa de programação autorizada.
- Intervenções do Arquiteto, comandos, eventos de campanha, instâncias de item, quantidades atuais de recursos, evidências, percepções, crenças adquiridas, memórias e rumores derivados pertencem ao estado da campanha, nunca ao pacote estático.
- O conteúdo estático pode definir capacidades, limites e condições permitidas para intervenções futuras, sem registrar uma intervenção concreta.
- `_templates/` guarda modelos editoriais, nunca conteúdo real e nunca deve ser carregado como entidade pelo futuro carregador.
- `assets/` contém recursos complementares associados a entidades; a ausência de arte não invalida conteúdo.
- `design/` guarda material de processo visual futuro e não é conteúdo do mundo.

Este contrato não cria entidades, lore, calendário, enums do mundo, regras de simulação ou implementação executável.

O contrato conceitual de [intervenção, percepção e conhecimento](schemas/INTERVENTION_PERCEPTION_AND_KNOWLEDGE.md) preserva a distinção entre causa real restrita, fato, evidência, percepção, interpretação, conhecimento, crença, suspeita, memória e rumor. Futuros schemas de NPC, evento, rumor e memória deverão obedecer a essa separação. Não existe categoria nem quantidade planejada de “intervenções iniciais”.

## Formato dos arquivos

- Entidades que precisem de lore usam Markdown com front matter YAML.
- YAML puro é reservado a manifestos, índices ou estruturas que não tenham corpo narrativo.
- Todos os arquivos usam UTF-8 e finais de linha consistentes dentro de cada arquivo.
- A indentação YAML é de dois espaços; tabs são proibidos em YAML.
- Cada entidade persistente ocupa um arquivo próprio.
- HTML e scripts executáveis são proibidos em arquivos de conteúdo.
- Âncoras e aliases YAML são proibidos nesta fase.
- Campos desconhecidos não devem ser inventados silenciosamente: devem ser definidos no schema especializado aplicável antes de serem usados em conteúdo aprovado.

## ID, pasta e nome de arquivo

O diretório determina a categoria, o front matter registra o ID completo e o nome de arquivo usa apenas o slug estável do ID. O prefixo do ID não se repete no nome de arquivo.

| ID | Caminho correto |
|---|---|
| `npc.lysandra_vale` | `npcs/lysandra_vale.md` |
| `spell.purifying_light` | `magic/spells/purifying_light.md` |
| `faction.order_of_dawn_healers` | `factions/order_of_dawn_healers.md` |
| `settlement.aurenfall` | `settlements/aurenfall.md` |

- Nomes visíveis podem mudar; IDs e nomes de arquivo não mudam por uma alteração cosmética de nome.
- Uma mudança legítima de ID exigirá migração documentada em etapa futura.
- O mesmo slug pode existir em categorias diferentes, pois os IDs completos continuam distintos.
- Manifestos, índices, READMEs e templates são exceções explícitas: não representam uma entidade persistente e não obedecem ao padrão de arquivo de entidade.

As regras complementares de formato de ID estão em [`ID_CONVENTIONS.md`](ID_CONVENTIONS.md).

## Campos comuns

Os campos abaixo são a base mínima para entidades que adotem este contrato. Um schema especializado pode acrescentar campos e restringir valores, mas não deve redefinir silenciosamente a semântica comum.

| Campo | Tipo | Finalidade e regra |
|---|---|---|
| `schema_version` | string de versão | Versão do contrato ou schema especializado que interpreta o arquivo. Deve estar entre aspas no YAML. |
| `id` | string | ID completo, estável e único da entidade. Deve corresponder à categoria e ao nome de arquivo. |
| `name` | string não vazia | Nome visível atual. Não é uma chave de referência. |
| `content_status` | enum editorial | Estado de autoria: `draft`, `in_review`, `approved` ou `deprecated`. |
| `tags` | lista de strings | Classificação auxiliar controlada; pode ser `[]` quando se sabe que não há tags aplicáveis. |
| `aliases` | lista de strings, opcional | Outros nomes visíveis, históricos ou de busca; nunca substituem `id`. |
| `summary` | string, opcional | Resumo curto para leitura humana; não substitui campos mecânicos. |
| `references` | lista de IDs completos, opcional | Referências genéricas e verificáveis. Schemas especializados definem relações estruturadas e categorias permitidas quando necessário. |
| `art` | lista de caminhos relativos a assets, opcional | Recursos complementares. Não é requisito para aprovar a entidade. |
| `notes` | string, opcional | Observação editorial delimitada; não pode ocultar mecânica, lore canônico ou segredos de visibilidade futura. |

Campos opcionais só são usados quando fizerem sentido para a entidade. O schema especializado poderá exigir um campo opcional para seu tipo, sempre de maneira documentada.

## Estado editorial (`content_status`)

O estado editorial descreve a maturidade do arquivo, não o estado interno da entidade no mundo:

| Estado | Significado |
|---|---|
| `draft` | Em autoria; pode ter referências ainda não resolvidas e não serve como conteúdo aprovado. |
| `in_review` | Pronto para revisão editorial, mas ainda não aprovado. |
| `approved` | Revisado e coerente com o contrato, com referências resolvidas. |
| `deprecated` | Mantido por histórico ou compatibilidade, mas não deve receber novas dependências sem decisão explícita. |

Estados como `alive`, `dead`, `missing`, `active`, `dissolved`, `legal` e `forbidden` descrevem o mundo e, quando cabíveis, terão campos próprios nos schemas especializados. Eles nunca substituem `content_status`.

## Semântica de ausência e valores vazios

- Campo omitido: não se aplica ou é opcional e não foi usado.
- `null`: a informação se aplica, mas é atualmente desconhecida.
- Lista vazia: sabe-se que não há item algum.
- String vazia: proibida.
- `a definir`, `TBD`, `TODO` e `desconhecido` dentro de campos mecânicos: proibidos.
- Zero: valor numérico real; nunca substitui desconhecido.
- `false`: valor booleano real; nunca substitui ausência.

Exemplos corretos:

```yaml
aliases: []
references: []
historical_date: null
quantity: 0
is_public: false
```

Exemplos incorretos:

```yaml
summary: ""
quantity: 0 # usado para significar "desconhecido"
duration_hours: "TBD"
is_public: false # usado para significar "não informado"
```

## Referências cruzadas

- Entidades são referenciadas por ID completo; nomes visíveis não funcionam como referência.
- Caminhos de arquivos não substituem IDs.
- Referências de conteúdo `approved` não podem apontar para entidades inexistentes.
- Referências futuras não podem ser registradas como se já estivessem resolvidas.
- Relações direcionais registram o ID do alvo; a reciprocidade só existe quando o schema especializado a exigir.
- Listas de IDs não devem misturar categorias sem documentação explícita no schema especializado.
- Referências circulares são permitidas quando representam relações reais. Ciclos de dependência inválidos devem ser identificados pelos schemas especializados.
- Toda referência deve ser verificável por busca no repositório.

## Tags e vocabulário

- Tags usam letras minúsculas, ASCII e underscore para palavras compostas.
- Tags são classificações auxiliares; não substituem campos estruturados.
- Sinônimos duplicados devem ser evitados.
- Novas tags devem ser documentadas no schema especializado ou no vocabulário controlado quando ele for criado.
- Tags não podem ocultar dados que precisem de campo próprio.

Nenhuma lista extensa de tags de Eldrath é definida nesta tarefa.

## Datas

- Datas do mundo usarão um formato canônico ligado ao calendário de Eldrath.
- O formato definitivo será congelado na tarefa do calendário.
- `"eldrath-482-03-11"`, exemplo presente no GDD, é apenas referência provisória nesta fase.
- Datas reais de edição, quando necessárias, usam ISO 8601.
- Datas do mundo e datas reais nunca compartilham o mesmo campo.
- Strings de data devem ficar entre aspas no YAML.

## Valores numéricos

- Faixas permitidas serão declaradas pelo schema especializado.
- Percentuais não podem misturar escalas de `0–1` e `0–100`.
- Moeda deve declarar unidade.
- Duração deve declarar unidade.
- Distância deve declarar unidade.
- Números desconhecidos usam `null`, nunca zero.
- Valores derivados não devem ser duplicados manualmente sem necessidade.

## Corpo Markdown

O front matter guarda dados estruturados; o corpo Markdown guarda lore, contexto e explicações. A prosa não pode contradizer os campos estruturados. Títulos seguem uma hierarquia consistente, e campos mecânicos não podem existir somente na prosa.

Informações secretas deverão respeitar o futuro modelo de visibilidade. A organização do corpo pode variar por entidade depois que o template especializado correspondente for definido.

## Versionamento editorial

Este é o contrato editorial inicial, versão `1.0.0`.

- `schema_version` identifica a versão que interpreta o arquivo e deve ser atualizado conforme o contrato aplicável.
- A versão do schema define a estrutura de um arquivo; a versão do pacote de conteúdo identifica o conjunto editorial de Eldrath; a versão do GDD identifica a especificação canônica do projeto. São versões distintas.
- Schemas não podem mudar silenciosamente.
- Mudanças incompatíveis exigirão uma migração documentada em etapa futura.
- Arquivos antigos não podem ser reinterpretados sem registro da mudança e da migração correspondente.

## Ciclo editorial

O fluxo é `draft → in_review → approved → deprecated`.

- O autor responsável prepara e atualiza conteúdo em `draft` e o encaminha para `in_review` quando estiver completo para análise.
- No processo atual, a aprovação para `approved` depende de revisão e autorização explícita do responsável editorial do projeto; referências devem estar resolvidas.
- Um conteúdo aprovado pode ser marcado como `deprecated` pelo responsável editorial quando houver razão registrada; `deprecated` não significa exclusão automática.
- Um ID de conteúdo obsoleto continua reservado e não pode ser reciclado.
- Aprovação individual não substitui a auditoria geral do mundo prevista antes do congelamento.

## Categorias de conteúdo

| Categoria | Prefixo de ID planejado | Formato principal | Template especializado futuro | Dependências gerais | Estado atual |
|---|---|---|---|---|---|
| `calendars/` | `calendar` | Markdown com front matter YAML | sim | identidade e contrato comum | vazia |
| `languages/` | `language` | Markdown com front matter YAML | sim | identidade e contrato comum | vazia |
| `cultures/` | `culture` | Markdown com front matter YAML | sim | identidade, calendário e idiomas | vazia |
| `regions/` | `region` | Markdown com front matter YAML | sim | reino, culturas e contrato comum | vazia |
| `settlements/` | `settlement` | Markdown com front matter YAML | sim | regiões, reino, recursos e rotas | vazia |
| `locations/` | `location` | Markdown com front matter YAML | sim | regiões e assentamentos | vazia |
| `routes/` | `route` | Markdown com front matter YAML | sim | regiões, assentamentos e locais | vazia |
| `npcs/` | `npc` | Markdown com front matter YAML | sim | contexto macro, social e mágico | vazia |
| `families/` | `family` | Markdown com front matter YAML | sim | culturas, reino, assentamentos e facções | vazia |
| `factions/` | `faction` | Markdown com front matter YAML | sim | reino, culturas, religiões e economia | vazia |
| `religions/` | `religion` | Markdown com front matter YAML | sim | cosmologia e culturas | vazia |
| `professions/` | `profession` | Markdown com front matter YAML | sim | economia, assentamentos e instituições | vazia |
| `creatures/` | `creature` | Markdown com front matter YAML | sim | geografia, clima e magia | vazia |
| `resources/` | `resource` | Markdown com front matter YAML | sim | regiões, clima e economia | vazia |
| `items/` | `item` | Markdown com front matter YAML | sim | recursos, profissões, economia e magia | vazia |
| `laws/` | `law` | Markdown com front matter YAML | sim | reino, política, culturas e magia | vazia |
| `diseases/` | `disease` | Markdown com front matter YAML | sim | ambiente, assentamentos, recursos e magia | vazia |
| `events/` | `event` | Markdown com front matter YAML | sim | entidades envolvidas e cronologia | vazia |
| `rumors/` | `rumor` | Markdown com front matter YAML | sim | eventos, NPCs, lugares e facções | vazia |
| `magic/schools/` | `school` | Markdown com front matter YAML | sim | princípios mágicos, instituições e leis | vazia |
| `magic/spells/` | `spell` | Markdown com front matter YAML | sim | escolas, efeitos, leis e instituições | vazia |
| `magic/rituals/` | `ritual` | Markdown com front matter YAML | sim | escolas, magias, efeitos e instituições | vazia |
| `magic/artifacts/` | `artifact` | Markdown com front matter YAML | sim | escolas, efeitos, itens e história | vazia |
| `magic/effects/` | `effect` | Markdown com front matter YAML | sim | contrato comum e regras de magia | vazia |

Esta tabela estabelece somente os prefixos e formatos-base. Ela não define os campos específicos dessas categorias.

## Validação editorial manual

Antes de encaminhar conteúdo para revisão, conferir:

- ID completo, único e válido;
- nome de arquivo derivado apenas do slug do ID;
- pasta correspondente à categoria;
- campos comuns aplicáveis;
- referências existentes e na categoria permitida;
- `content_status` correto;
- uso correto de `null`;
- listas vazias somente quando se sabe que não há itens;
- tags compatíveis com o vocabulário;
- datas com campo e formato adequados;
- corpo Markdown coerente com o front matter;
- ausência de placeholders;
- ausência de contradição com o GDD, o contrato e entidades aprovadas.

## Decisões adiadas

As tarefas posteriores definirão:

- campos específicos de cada entidade;
- enums do mundo;
- calendário definitivo;
- faixas numéricas;
- regras de herança;
- regras de simulação;
- validação executável;
- banco de dados;
- migrações automatizadas.
