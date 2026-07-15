# Convenções de IDs

Este documento resume as regras de ID aplicáveis ao contrato comum da Fase 1. A definição completa de formato de arquivo, referências e semântica está em [`CONTENT_SCHEMA.md`](CONTENT_SCHEMA.md); `Base/GDD.md` continua sendo a fonte canônica.

## Formato

Todo ID de conteúdo segue o padrão:

```text
tipo.nome_estavel
```

Regras obrigatórias:

- usar letras minúsculas;
- usar somente caracteres ASCII;
- separar palavras com underscore (`_`);
- começar com um prefixo correspondente ao tipo da entidade;
- usar IDs, e não nomes visíveis, em referências entre entidades;
- nunca reciclar um ID removido;
- permitir que o nome visível mude sem quebrar referências;
- fazer cada ID representar uma única entidade;
- tratar qualquer referência ausente como erro;
- não reutilizar IDs de entidades removidas;
- nunca usar nomes visíveis como chave permanente.

## ID e nome de arquivo

Para entidades persistentes, a pasta determina a categoria, o front matter contém o ID completo e o arquivo usa somente o slug estável após o primeiro ponto. O prefixo não é repetido no arquivo.

| ID | Caminho correto | Caminho incorreto |
|---|---|---|
| `npc.lysandra_vale` | `npcs/lysandra_vale.md` | `npcs/npc.lysandra_vale.md` |
| `spell.purifying_light` | `magic/spells/purifying_light.md` | `magic/spells/spell_purifying_light.md` |
| `faction.order_of_dawn_healers` | `factions/order_of_dawn_healers.md` | `factions/Ordem_das_Curandeiras.md` |

Manifestos, índices, READMEs e arquivos em `_templates/` são exceções explícitas: eles não representam uma entidade persistente e não recebem nome derivado de ID.

Uma mudança cosmética de nome visível nunca autoriza renomear o ID ou o arquivo. Se uma mudança de ID for legitimamente necessária, ela exigirá migração documentada futura. Conteúdo `deprecated` mantém seu ID reservado; removê-lo do uso ativo não permite reciclá-lo.

## Prefixos do sistema mágico

O contrato especializado do sistema mágico finaliza os prefixos abaixo. Escolas e subescolas usam a mesma entidade; efeitos aplicados pertencem ao save e não recebem prefixo de conteúdo próprio.

| Entidade | Prefixo | Caminho de entidade |
|---|---|---|
| escola ou subescola mágica | `magic_school.` | `magic/schools/{slug}.md` |
| magia | `spell.` | `magic/spells/{slug}.md` |
| ritual | `ritual.` | `magic/rituals/{slug}.md` |
| definição reutilizável de efeito mágico | `magic_effect.` | `magic/effects/{slug}.md` |
| artefato | `artifact.` | `magic/artifacts/{slug}.md` |

`parent_school_id` referencia outro `magic_school.*`; não existe `magic_subschool.*`. Uma aplicação usa `magic_effect_id` para referenciar `magic_effect.*`; não existe arquivo `effect_instance`. As regras completas estão em [`MAGIC_SYSTEM_ENTITIES.md`](schemas/MAGIC_SYSTEM_ENTITIES.md).

## Prefixos de criaturas e doenças

O contrato especializado de criaturas, saúde e doenças finaliza os dois prefixos de conteúdo abaixo. Condições de saúde e ocorrências concretas pertencem ao save e não recebem prefixo ou arquivo de conteúdo próprio.

| Entidade | Prefixo | Caminho de entidade |
|---|---|---|
| espécie, tipo ou arquétipo de criatura | `creature.` | `creatures/{slug}.md` |
| definição estática de doença | `disease.` | `diseases/{slug}.md` |

Um indivíduo persistente usa futuramente `npc.*` e referencia `creature.*`. Uma instância de doença referencia `disease.*` no save. Não existem nesta fase os prefixos `condition.`, `injury.`, `symptom.`, `poison.`, `infection.` ou `health.`. As regras completas estão em [`CREATURE_HEALTH_AND_DISEASE_ENTITIES.md`](schemas/CREATURE_HEALTH_AND_DISEASE_ENTITIES.md).

## Prefixo de NPC e subregistros incorporados

O contrato especializado de NPCs finaliza o prefixo do arquivo principal e os prefixos de subregistros identificáveis. Somente `npc.*` representa uma entidade com arquivo próprio neste conjunto.

| Registro | Prefixo | Persistência editorial |
|---|---|---|
| NPC persistente | `npc.` | `npcs/{slug}.md` |
| objetivo individual | `goal.` | subregistro incorporado ao NPC ou ao save |
| medo individual | `fear.` | subregistro incorporado ao NPC ou ao save |
| segredo pessoal | `secret.` | subregistro incorporado ao NPC ou ao save |
| memória individual | `memory.` | subregistro incorporado ao NPC ou ao save |
| crença ou suspeita | `belief.` | subregistro incorporado ao NPC ou ao save |
| conhecimento individual | `knowledge.` | subregistro incorporado ao NPC ou ao save |
| relação direcionada | `relationship.` | subregistro incorporado ao NPC ou ao save |

Formas previsíveis:

```text
goal.npc_slug.stable_goal
fear.npc_slug.stable_fear
secret.npc_slug.stable_secret
memory.npc_slug.stable_memory
belief.npc_slug.stable_belief
knowledge.npc_slug.stable_knowledge
relationship.source_slug.target_slug
```

`belief.*` usa um campo estruturado para distinguir crença de suspeita; não existe prefixo `suspicion.`. Não existem arquivos ou pastas independentes para objetivos, medos, segredos, memórias, crenças, conhecimento, relações, reputações, emoções ou necessidades. O ID do NPC e os IDs incorporados permanecem estáveis quando nomes, títulos, família, profissão, residência ou condição histórica mudarem. As regras completas estão em [`NPC_SYSTEM_ENTITIES.md`](schemas/NPC_SYSTEM_ENTITIES.md).

## Exemplos válidos

| ID | Motivo |
|---|---|
| `npc.lysandra_vale` | Prefixo de tipo, minúsculas, ASCII e palavras separadas por underscore. |
| `faction.order_of_dawn_healers` | Identifica de forma estável uma facção sem depender do nome visível. |
| `settlement.aurenfall` | Possui tipo explícito e nome estável previsível. |
| `spell.purifying_light` | Permite que magias sejam referenciadas pelo ID mesmo se o título mudar. |
| `magic_school.example_school` | Exemplo exclusivamente estrutural de escola ou subescola. |
| `ritual.example_ritual` | Exemplo exclusivamente estrutural de procedimento ritual. |
| `magic_effect.example_effect` | Exemplo exclusivamente estrutural de definição reutilizável. |
| `artifact.example_artifact` | Exemplo exclusivamente estrutural de artefato. |
| `creature.example_creature` | Exemplo exclusivamente estrutural de espécie ou tipo de criatura. |
| `disease.example_disease` | Exemplo exclusivamente estrutural de definição de doença. |
| `goal.npc_slug.stable_goal` | Exemplo estrutural de objetivo incorporado, previsível e associado ao slug estável do NPC. |
| `relationship.source_slug.target_slug` | Exemplo estrutural de relação direcionada; a ordem identifica origem e alvo. |
| `event.seed.plague_of_white_ash` | Usa segmentos de tipo para identificar um evento-semente e mantém o nome estável em minúsculas. |

## Exemplos inválidos

| ID inválido | Problema |
|---|---|
| `NPC.LysandraVale` | Usa maiúsculas, não separa palavras com underscore e não segue o prefixo normalizado. |
| `npc.lysandra vale` | Contém espaço; palavras devem ser separadas por underscore. |
| `npc.lysândra_vale` | Contém caractere fora de ASCII. |
| `lysandra_vale` | Não possui prefixo obrigatório de tipo. |
| `faction.order-of-dawn` | Usa hífens em vez de underscore entre palavras. |
| `Aurenfall` | É um nome visível, não uma chave permanente com tipo explícito. |
| `spell.purifying_light` para duas magias | Um mesmo ID não pode representar mais de uma entidade. |
| `npc.lysandra_vale` reutilizado após remoção | IDs removidos não podem ser reciclados, mesmo que o nome volte a ser usado. |

Uma referência como `teacher: faction.order_of_dawn_healers` é válida apenas se a entidade referenciada existir. Se estiver ausente, a autoria ou validação deve acusar erro; não se deve substituir o ID pelo nome da facção.

Este documento não define campos, schemas completos, expressões regulares nem implementação de validação.
