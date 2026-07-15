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

## Ordem de dependência

1. contrato comum;
2. entidades fundamentais (`world`, calendário, idioma, cultura e reino);
3. geografia (região, assentamento, local e rota);
4. economia material (recursos, profissões, itens e estruturas compartilhadas);
5. intervenção, percepção, conhecimento e causalidade;
6. sociedade, instituições, famílias e lei;
7. demais conjuntos especializados, respeitando a [ordem de autoria](../AUTHORING_ORDER.md).

O contrato comum, as entidades fundamentais, as entidades geográficas, a economia material, o contrato conceitual de intervenção e os contratos de religião, facção, família e lei estão concluídos. A próxima categoria documental é escolas de magia, magias, rituais, efeitos e artefatos; NPCs, narrativa e saúde ainda não foram iniciados.

## Regras de manutenção

- Um schema futuro deve ser criado nesta pasta antes de seu conteúdo especializado ou template correspondente.
- Todo novo schema deve declarar entidades, formatos, caminhos, dependências, referências e regras de ausência, e permanecer compatível com [`CONTENT_SCHEMA.md`](../CONTENT_SCHEMA.md).
- Templates materializam a estrutura de um schema para autoria, mas não são conteúdo real, não contam como entidades e nunca podem ser carregados como tal.
- Placeholders pertencem somente a templates e são proibidos em conteúdo `approved`.
- Nenhum schema editorial pode contradizer o GDD canônico local.
- Contratos transversais de estado da campanha não criam pasta, template, entidade ou meta de conteúdo inicial.

Os templates relacionados ficam em [`content/worlds/eldrath/_templates/`](../../../content/worlds/eldrath/_templates/). Eles devem ser atualizados quando uma alteração aprovada de schema tornar sua estrutura incompatível.
