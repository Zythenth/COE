# Schemas editoriais do mundo

Esta pasta reúne contratos editoriais especializados: documentos legíveis que definem como cada categoria de entidade deve ser representada antes de receber conteúdo. Eles não são schemas executáveis, JSON Schema, tipos de programação ou mecanismos de validação automatizada.

O contrato compartilhado vigente é a versão [`1.0.0`](../CONTENT_SCHEMA.md). Os schemas especializados acrescentam campos e restrições por entidade, sem redefinir a semântica de campos comuns, IDs, referências, `null`, listas vazias ou estados editoriais.

## Documentos existentes

| Documento | Entidades cobertas | Dependência editorial | Estado |
|---|---|---|---|
| [FOUNDATIONAL_ENTITIES.md](FOUNDATIONAL_ENTITIES.md) | `world`, `calendar`, `language`, `culture`, `kingdom` | contrato comum | concluído |
| [GEOGRAPHY_ENTITIES.md](GEOGRAPHY_ENTITIES.md) | `region`, `settlement`, `location`, `route` | contrato comum e entidades fundamentais | concluído |
| [MATERIAL_ECONOMY_ENTITIES.md](MATERIAL_ECONOMY_ENTITIES.md) | `resource`, `profession`, `item` e contratos econômicos compartilhados | contrato comum, entidades fundamentais e geografia | concluído |
| [INTERVENTION_PERCEPTION_AND_KNOWLEDGE.md](INTERVENTION_PERCEPTION_AND_KNOWLEDGE.md) | contrato transversal de estado de campanha; não cria entidades | GDD, contrato comum e economia material | concluído |
| [SOCIETY_INSTITUTIONS_AND_LAW_ENTITIES.md](SOCIETY_INSTITUTIONS_AND_LAW_ENTITIES.md) | `religion`, `faction`, `family` e `law` | contrato comum, entidades fundamentais, geografia, economia material e contrato transversal | concluído |
| [MAGIC_SYSTEM_ENTITIES.md](MAGIC_SYSTEM_ENTITIES.md) | `magic_school`, `spell`, `ritual`, `magic_effect` e `artifact` | contratos anteriores, especialmente economia material, intervenção, sociedade e lei | concluído |
| [CREATURE_HEALTH_AND_DISEASE_ENTITIES.md](CREATURE_HEALTH_AND_DISEASE_ENTITIES.md) | `creature`, `disease` e estruturas conceituais de saúde e condições; não cria entidades de condição | contratos anteriores, especialmente geografia, economia, intervenção, sociedade, lei e magia | concluído |
| [NPC_SYSTEM_ENTITIES.md](NPC_SYSTEM_ENTITIES.md) | `npc` e subregistros incorporados de objetivos, medos, segredos, memória, conhecimento, crenças, relações e estado inicial | todos os contratos anteriores | concluído |
| [EVENT_RUMOR_HISTORY_AND_CONFLICT_ENTITIES.md](EVENT_RUMOR_HISTORY_AND_CONFLICT_ENTITIES.md) | `event`, `rumor`, `conflict`, causalidade, gatilhos, arcos e projeções históricas | todos os contratos anteriores | concluído |
| [MONSTROUS_THREATS_AND_INCURSIONS.md](MONSTROUS_THREATS_AND_INCURSIONS.md) | ameaças, populações, grupos, hordas, ataques, incursões, defesas e consequências; não cria novas entidades | criaturas, geografia, economia, sociedade, magia, NPCs, eventos e conflitos | concluído |
| [GITHUB_DERIVED_WORLD_GENERATION.md](GITHUB_DERIVED_WORLD_GENERATION.md) | modos de criação, snapshot público opcional, fórmula, agrupamento, mapa, saves, reinício e velocidade; não cria entidades | todos os contratos anteriores e GDD 1.4 | concluído |

## Ordem de dependência

1. contrato comum;
2. entidades fundamentais (`world`, calendário, idioma, cultura e reino);
3. geografia (região, assentamento, local e rota);
4. economia material (recursos, profissões, itens e estruturas compartilhadas);
5. intervenção, percepção, conhecimento e causalidade;
6. sociedade, instituições, famílias e lei;
7. sistema mágico;
8. criaturas, doenças, saúde e condições relacionadas;
9. NPCs persistentes e seus subregistros incorporados;
10. eventos, rumores, história, causalidade e conflitos;
11. ameaças monstruosas, grupos agregados, ataques e incursões;
12. geração opcional de mundo derivada do GitHub, mapa, checkpoint inicial, reinício e velocidade, respeitando a [ordem de autoria](../AUTHORING_ORDER.md).

O contrato comum, as entidades fundamentais, as entidades geográficas, a economia material, o contrato conceitual de intervenção, os contratos de religião, facção, família e lei, o sistema mágico, os contratos de criaturas, doenças, saúde e condições relacionadas, o contrato completo de NPCs, os contratos de eventos, rumores, história, conflitos, ameaças e incursões e o contrato de geração opcional derivada do GitHub estão concluídos. Os templates correspondentes estão disponíveis, mas nenhuma entidade real foi criada. O contrato GitHub é conceitual, não executável, não possui template e não altera as contagens de Eldrath. A Fase 1 aguarda auditoria editorial final, consolidação e encerramento explícito.

## Regras de manutenção

- Um schema futuro deve ser criado nesta pasta antes de seu conteúdo especializado ou template correspondente.
- Todo novo schema deve declarar entidades, formatos, caminhos, dependências, referências e regras de ausência, e permanecer compatível com [`CONTENT_SCHEMA.md`](../CONTENT_SCHEMA.md).
- Templates materializam a estrutura de um schema para autoria, mas não são conteúdo real, não contam como entidades e nunca podem ser carregados como tal.
- Placeholders pertencem somente a templates e são proibidos em conteúdo `approved`.
- Nenhum schema editorial pode contradizer o GDD canônico local.
- Contratos transversais de estado da campanha não criam pasta, template, entidade ou meta de conteúdo inicial.

Os templates relacionados ficam em [`content/worlds/eldrath/_templates/`](../../../content/worlds/eldrath/_templates/). Eles devem ser atualizados quando uma alteração aprovada de schema tornar sua estrutura incompatível.
