# Templates editoriais de Eldrath

Esta pasta contém modelos para autoria consistente; ela não contém conteúdo real e deverá ser obrigatoriamente excluída pelo futuro carregador de conteúdo.

Os templates usam nomes em `snake_case` e descrevem sua finalidade, por exemplo `base_entity.md`, `npc.template.md` e `spell.template.md`. Placeholders usam a forma explícita `{{nome_do_valor}}`. Eles orientam a cópia para um arquivo de trabalho, mas nunca são dados e não podem chegar a um arquivo com `content_status: approved`.

[`base_entity.md`](base_entity.md) continua sendo a origem conceitual dos campos comuns definidos no [contrato editorial](../../../../docs/world/CONTENT_SCHEMA.md). Os templates especializados acrescentam somente os campos do [schema correspondente](../../../../docs/world/schemas/README.md); eles não são conteúdo real e não definem schemas por si só.

## Catálogo fundamental

| Template | Entidade | Formato | Destino futuro | Dependências | Estado |
|---|---|---|---|---|---|
| [`world.template.yaml`](world.template.yaml) | mundo | YAML puro | `../world.yaml` | contrato comum e entidades fundamentais | concluído |
| [`calendar.template.md`](calendar.template.md) | calendário | Markdown com front matter YAML | `../calendars/{slug}.md` | contrato comum e identidade do mundo | concluído |
| [`language.template.md`](language.template.md) | idioma | Markdown com front matter YAML | `../languages/{slug}.md` | contrato comum; culturas e regiões quando existirem | concluído |
| [`culture.template.md`](culture.template.md) | cultura | Markdown com front matter YAML | `../cultures/{slug}.md` | contrato comum; idiomas e regiões quando existirem | concluído |
| [`kingdom.template.yaml`](kingdom.template.yaml) | reino | YAML puro | `../kingdom.yaml` | contrato comum, mundo e entidades fundamentais relacionadas | concluído |

## Catálogo geográfico

| Template | Entidade | Formato | Destino futuro | Dependências | Estado |
|---|---|---|---|---|---|
| [`region.template.md`](region.template.md) | região | Markdown com front matter YAML | `../regions/{slug}.md` | contrato comum, reino e vocabulários geográficos | concluído |
| [`settlement.template.md`](settlement.template.md) | assentamento | Markdown com front matter YAML | `../settlements/{slug}.md` | contrato comum, região e schemas político, religioso e econômico futuros | concluído |
| [`location.template.md`](location.template.md) | local | Markdown com front matter YAML | `../locations/{slug}.md` | contrato comum, região, assentamento opcional e schemas futuros relacionados | concluído |
| [`route.template.md`](route.template.md) | rota | Markdown com front matter YAML | `../routes/{slug}.md` | contrato comum e extremos `settlement.*` ou `location.*` aprovados | concluído |

## Catálogo de economia material

| Template | Entidade | Formato | Destino futuro | Dependências | Estado |
|---|---|---|---|---|---|
| [`resource.template.md`](resource.template.md) | recurso | Markdown com front matter YAML | `../resources/{slug}.md` | contrato comum, unidades, geografia e economia material | concluído |
| [`profession.template.md`](profession.template.md) | profissão | Markdown com front matter YAML | `../professions/{slug}.md` | contrato comum, recursos, itens, assentamentos e instituições futuras | concluído |
| [`item.template.md`](item.template.md) | item | Markdown com front matter YAML | `../items/{slug}.md` | contrato comum, unidades, recursos, profissões, economia e magia futura | concluído |

## Catálogo de sociedade, instituições e lei

| Template | Entidade | Formato | Destino futuro | Dependências | Estado |
|---|---|---|---|---|---|
| [`religion.template.md`](religion.template.md) | religião ou tradição de crença | Markdown com front matter YAML | `../religions/{slug}.md` | contrato comum, culturas e contrato transversal | concluído |
| [`faction.template.md`](faction.template.md) | facção ou instituição | Markdown com front matter YAML | `../factions/{slug}.md` | contrato comum, geografia, economia, religiões e contrato transversal | concluído |
| [`family.template.md`](family.template.md) | família, linhagem ou casa dinástica | Markdown com front matter YAML | `../families/{slug}.md` | contrato comum, culturas, geografia, facções e leis | concluído |
| [`law.template.md`](law.template.md) | lei pública reconhecida | Markdown com front matter YAML | `../laws/{slug}.md` | contrato comum, geografia, facções, economia e contrato transversal | concluído |

## Catálogo do sistema mágico

| Template | Entidade | Formato | Destino futuro | Dependências | Estado |
|---|---|---|---|---|---|
| [`magic_school.template.md`](magic_school.template.md) | escola ou subescola mágica | Markdown com front matter YAML | `../magic/schools/{slug}.md` | contrato comum, sociedade, lei e sistema mágico | concluído |
| [`spell.template.md`](spell.template.md) | magia | Markdown com front matter YAML | `../magic/spells/{slug}.md` | escolas, efeitos, economia, instituições, percepção e leis | concluído |
| [`ritual.template.md`](ritual.template.md) | ritual | Markdown com front matter YAML | `../magic/rituals/{slug}.md` | escolas, magias, efeitos, itens, artefatos e instituições | concluído |
| [`magic_effect.template.md`](magic_effect.template.md) | definição reutilizável de efeito mágico | Markdown com front matter YAML | `../magic/effects/{slug}.md` | contrato comum, quantidade, percepção e regras mágicas | concluído |
| [`artifact.template.md`](artifact.template.md) | artefato | Markdown com front matter YAML | `../magic/artifacts/{slug}.md` | efeitos, itens, recursos, história, percepção e leis | concluído |

## Catálogo de criaturas, saúde e doenças

| Template | Entidade | Formato | Destino futuro | Dependências | Estado |
|---|---|---|---|---|---|
| [`creature.template.md`](creature.template.md) | espécie, tipo ou arquétipo de criatura | Markdown com front matter YAML | `../creatures/{slug}.md` | geografia, economia, ecologia, magia, percepção e saúde | concluído |
| [`disease.template.md`](disease.template.md) | definição estática de doença | Markdown com front matter YAML | `../diseases/{slug}.md` | criaturas, ambiente, economia, profissões, magia, leis e percepção | concluído |

## Catálogo de NPCs

| Template | Entidade | Formato | Destino futuro | Dependências | Estado |
|---|---|---|---|---|---|
| [`npc.template.md`](npc.template.md) | NPC persistente | Markdown com front matter YAML | `../npcs/{slug}.md` | todos os contratos fundamentais, geográficos, econômicos, sociais, mágicos, de saúde e percepção | concluído |

## Catálogo de eventos, rumores e conflitos

| Template | Entidade | Formato | Destino futuro | Dependências | Estado |
|---|---|---|---|---|---|
| [`event.template.md`](event.template.md) | evento histórico ou evento-base de conteúdo | Markdown com front matter YAML | `../events/{slug}.md` | entidades envolvidas, causalidade, cronologia e história | concluído |
| [`rumor.template.md`](rumor.template.md) | rumor inicial de conteúdo | Markdown com front matter YAML | `../rumors/{slug}.md` | fontes, eventos, pessoas, lugares, genealogia e conhecimento limitado | concluído |
| [`conflict.template.md`](conflict.template.md) | conflito latente | Markdown com front matter YAML | `../conflicts/{slug}.md` | partes, interesses, pressões, eventos, ameaças e gatilhos | concluído |

Copie somente o template da entidade que será autorizada para o destino indicado, preserve `schema_version: "1.0.0"` e `content_status: draft`, substitua todos os placeholders antes da revisão e mantenha `null` e listas vazias conforme o contrato. Quantidade, dinheiro, taxa, preço e faixa devem conservar as estruturas documentadas no [schema de economia material](../../../../docs/world/schemas/MATERIAL_ECONOMY_ENTITIES.md). Religião, facção, família e lei devem conservar as direções canônicas e fronteiras do [schema de sociedade, instituições e lei](../../../../docs/world/schemas/SOCIETY_INSTITUTIONS_AND_LAW_ENTITIES.md). Escolas, magias, rituais, efeitos e artefatos devem conservar as estruturas do [contrato do sistema mágico](../../../../docs/world/schemas/MAGIC_SYSTEM_ENTITIES.md), inclusive legalidade contextual, custos verificáveis, referências a efeitos e separação do estado da campanha. Criaturas e doenças devem conservar as fronteiras do [contrato de criaturas, saúde e doenças](../../../../docs/world/schemas/CREATURE_HEALTH_AND_DISEASE_ENTITIES.md): espécie não é indivíduo, doença não é instância e condição atual pertence ao save. NPCs devem conservar perfil separado de `initial_state`, relações direcionais, conhecimento limitado, fontes de memória e magia e a propriedade canônica definida no [contrato de NPCs](../../../../docs/world/schemas/NPC_SYSTEM_ENTITIES.md). Eventos, rumores e conflitos devem conservar causalidade, perspectivas, genealogia, conhecimento limitado, gatilhos e resultados não predeterminados conforme o [contrato correspondente](../../../../docs/world/schemas/EVENT_RUMOR_HISTORY_AND_CONFLICT_ENTITIES.md); capacidades monstruosas e incursões seguem o [contrato de ameaças](../../../../docs/world/schemas/MONSTROUS_THREATS_AND_INCURSIONS.md). Nenhum desses arquivos cria ou representa `world.yaml`, `kingdom.yaml`, pasta `conditions/` ou uma entidade real. Placeholders são exclusivos desta pasta e são proibidos em conteúdo `approved`.

## Ordem recomendada

1. `world.template.yaml`;
2. `calendar.template.md`;
3. `language.template.md`;
4. `culture.template.md`;
5. `kingdom.template.yaml`;
6. `region.template.md`;
7. `settlement.template.md`;
8. `location.template.md`;
9. `route.template.md`;
10. `resource.template.md`;
11. `profession.template.md`;
12. `item.template.md`;
13. `religion.template.md`;
14. `faction.template.md`;
15. `family.template.md`;
16. `law.template.md`;
17. `magic_school.template.md`;
18. `spell.template.md`;
19. `ritual.template.md`;
20. `magic_effect.template.md`;
21. `artifact.template.md`;
22. `creature.template.md`;
23. `disease.template.md`;
24. `npc.template.md`;
25. `event.template.md`;
26. `rumor.template.md`;
27. `conflict.template.md`.

Quando o contrato comum ou um schema especializado mudar de forma aprovada, os templates afetados deverão ser revisados antes de novos arquivos serem aprovados. O ciclo de revisão de um template é o mesmo do conteúdo: elaboração, revisão, aprovação explícita e eventual depreciação documentada.
