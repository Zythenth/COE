# Conteúdo do mundo de Eldrath

Esta pasta reúne o pacote autoral que definirá as condições iniciais de Eldrath. Na Fase 1 ela contém o manifesto editorial e a estrutura vazia das categorias, apoiados pelo contrato comum, pelos contratos especializados fundamentais, geográficos, de economia material e de sociedade, instituições e lei, além do contrato conceitual de intervenção, percepção e conhecimento; nenhuma entidade, lore nova, `world.yaml` ou `kingdom.yaml` foi criada.

O pacote é identificado por [`manifest.yaml`](manifest.yaml). As regras compartilhadas de formato, IDs, referências, valores ausentes e revisão estão em [`docs/world/CONTENT_SCHEMA.md`](../../../docs/world/CONTENT_SCHEMA.md).

## Conteúdo inicial e estado simulado

O conteúdo inicial descreve entidades, relações, regras editoriais, fatos históricos e condições existentes antes do avanço de uma campanha. Ele será escrito em arquivos versionados e auditáveis.

O estado produzido pela simulação registrará acontecimentos e mutações de uma campanha: tempo transcorrido, decisões, eventos, relações alteradas, mortes, rumores e outras consequências. Intervenções do Arquiteto, comandos, `item_instance`, quantidades atuais de recursos, evidências, percepções, crenças adquiridas, memórias e rumores derivados também pertencerão a esse estado. Esse estado será responsabilidade futura da programação e da persistência. A simulação não deverá reescrever os arquivos autorais a cada tick.

O conteúdo estático poderá definir capacidades, limites e condições permitidas, mas não haverá pasta, template, entidade ou quantidade planejada de “intervenções iniciais”. Fatos, percepções, interpretações, crenças e conhecimento permanecem conceitos distintos conforme o [contrato de intervenção, percepção e conhecimento](../../../docs/world/schemas/INTERVENTION_PERCEPTION_AND_KNOWLEDGE.md).

Na economia, os arquivos autorais poderão registrar propriedades estáveis, valores e relações iniciais, capacidades, métodos permitidos e referências. Estoque, preço, produção, consumo, salário, riqueza e tráfego atuais, além de escassez, inflação, dívida e contratos ativos, pertencerão ao estado futuro.

## Responsabilidade das pastas

| Pasta | Responsabilidade futura | Estado atual |
|---|---|---|
| `_templates/` | Modelos editoriais aprovados para autoria consistente. | template genérico, cinco templates fundamentais, quatro geográficos, três de economia material e quatro de sociedade, instituições e lei disponíveis; não são conteúdo real |
| `calendars/` | Calendário, eras e representação de datas. | não iniciado |
| `languages/` | Idiomas relevantes do mundo. | não iniciado |
| `cultures/` | Culturas, normas, valores e contextos sociais. | não iniciado |
| `regions/` | Regiões, biomas, clima, fronteiras e propriedades territoriais. | schema e template disponíveis; pasta real vazia |
| `settlements/` | Capital, cidades, vilas e suas estruturas sociais e materiais. | schema e template disponíveis; pasta real vazia |
| `locations/` | Locais especiais, naturais, urbanos, ocultos e sistêmicos. | schema e template disponíveis; pasta real vazia |
| `routes/` | Conexões entre lugares, deslocamento, custos e riscos. | schema e template disponíveis; pasta real vazia |
| `npcs/` | Fichas dos NPCs-semente e suas condições iniciais. | não iniciado |
| `families/` | Famílias, linhagens, casas dinásticas, herança familiar e legado. | schema e template disponíveis; pasta real vazia; zero famílias |
| `factions/` | Facções, instituições, cargos, autoridade, presença inicial e objetivos coletivos. | schema e template disponíveis; pasta real vazia; zero facções |
| `religions/` | Tradições religiosas, cultos como crença, doutrinas, práticas e diversidade. | schema e template disponíveis; pasta real vazia; zero religiões |
| `professions/` | Profissões, tarefas, competências, status e progressão. | schema e template disponíveis; pasta real vazia; zero profissões |
| `creatures/` | Espécies, habitat, comportamento, ecologia e relação com magia. | não iniciado |
| `resources/` | Recursos materiais e arcanos relevantes para a vida do reino. | schema e template disponíveis; pasta real vazia; zero recursos |
| `items/` | Definições de itens relevantes, propriedades, uso e proveniência. | schema e template disponíveis; pasta real vazia; zero itens |
| `laws/` | Leis gerais, mágicas e detalhadas por jurisdição, vigência e autoridade. | schema e template disponíveis; pasta real vazia; zero leis |
| `diseases/` | Doenças, transmissão, sintomas, gravidade e tratamentos. | não iniciado |
| `events/` | Eventos históricos e eventos-base que compõem o estado inicial. | não iniciado |
| `rumors/` | Rumores iniciais ou gatilhos, origens e referências causais. | não iniciado |
| `magic/schools/` | Escolas mágicas, relações, acesso e status. | não iniciado |
| `magic/spells/` | Magias com requisitos, custos, efeitos, riscos e lore complementar. | não iniciado |
| `magic/rituals/` | Rituais e suas regras estruturadas. | não iniciado |
| `magic/artifacts/` | Artefatos, efeitos, proveniência e história. | não iniciado |
| `magic/effects/` | Efeitos mágicos estruturados e referenciáveis. | não iniciado |

`_templates/` contém o template genérico [`base_entity.md`](_templates/base_entity.md), que reúne apenas os campos comuns. Um template especializado futuro parte dele e adiciona somente os campos documentados para uma categoria. A pasta nunca é conteúdo real e deve ser excluída pelo futuro carregador. Quando uma pasta-folha recebe conteúdo real, seu `.gitkeep` deve ser removido; por isso `_templates/.gitkeep` foi removido ao receber seus arquivos reais de template.

## IDs e referências

- Cada entidade persistente terá um ID estável no formato `tipo.nome_estavel`.
- IDs usam minúsculas, ASCII, underscore e prefixo de tipo.
- Nomes visíveis podem mudar e nunca funcionam como chave permanente.
- Referências entre entidades usam IDs, não nomes.
- Uma referência ausente é erro; não deve ser resolvida por suposição.
- IDs removidos não são reciclados e um ID representa apenas uma entidade.

As regras organizadas estão em [`docs/world/ID_CONVENTIONS.md`](../../../docs/world/ID_CONVENTIONS.md) e no [contrato editorial comum](../../../docs/world/CONTENT_SCHEMA.md).

## Dados estruturados e lore

Entidades com lore usarão Markdown com front matter YAML; YAML puro é reservado a manifestos, índices e estruturas sem corpo narrativo. O front matter armazena dados estruturados do conteúdo, enquanto o corpo Markdown registra lore e explicações; isso não significa que todo campo estruturado seja conhecimento de um NPC. Os schemas fundamentais, geográficos, de economia material e de sociedade, instituições e lei e o contrato transversal de intervenção estão no [índice de schemas](../../../docs/world/schemas/README.md); o contrato econômico compartilhado está em [`MATERIAL_ECONOMY_ENTITIES.md`](../../../docs/world/schemas/MATERIAL_ECONOMY_ENTITIES.md) e o contrato social e jurídico em [`SOCIETY_INSTITUTIONS_AND_LAW_ENTITIES.md`](../../../docs/world/schemas/SOCIETY_INSTITUTIONS_AND_LAW_ENTITIES.md).

Dados mecânicos e lore devem permanecer distinguíveis:

- custos, condições, efeitos, duração, referências e demais informações necessárias ao funcionamento pertencem à parte estruturada;
- contexto histórico, interpretação e texto de apresentação pertencem à prosa;
- prosa nunca substitui dados necessários nem altera silenciosamente uma regra estruturada;
- o conteúdo deve permanecer completo e utilizável sem IA generativa.

Assets são complementares: nenhuma entidade ou regra depende de imagem, e a ausência de arte não invalida conteúdo. A pasta `design/` trata do processo visual futuro e não faz parte dos dados do mundo.

## Recurso, item, artefato e instância

- **Recurso** é fungível, mensurável e tratado economicamente por quantidade.
- **Item** é a definição de um tipo de objeto discreto, possivelmente agregável ou durável; seu arquivo não representa cada cópia.
- **Artefato** será uma entidade do sistema mágico para objeto relevante, único ou historicamente importante, com origem, poderes, riscos e história próprios; poderá referenciar um item-base sem ser reduzido a item comum.
- **Instância de item** será uma cópia pertencente ao estado da simulação e poderá guardar proprietário, localização, quantidade, condição, durabilidade, proveniência e modificadores.

Os templates [`resource.template.md`](_templates/resource.template.md), [`profession.template.md`](_templates/profession.template.md) e [`item.template.md`](_templates/item.template.md) materializam somente os contratos de autoria. As pastas `resources/`, `professions/` e `items/` continuam contendo apenas seus arquivos `.gitkeep`.

## Religião, instituição, família e lei

- **Religião** define tradição de crença, doutrina e prática; uma organização religiosa é `faction.*`, e a facção referencia a religião.
- **Facção** define organização, cargos, autoridade, políticas e presença territorial inicial; membros e ocupantes atuais pertencerão a NPCs e ao save.
- **Família** define identidade, linhagem conceitual, tradição e herança familiar; parentesco concreto pertencerá às relações de NPCs. Uma casa política usa também `faction.*`, com referência da facção para a família.
- **Lei** define regra pública reconhecida, jurisdição, vigência, condições, exceções e sanções; crimes, processos, evidências e julgamentos pertencerão a eventos e ao estado.
- **Profissão** permanece atividade econômica; **cargo** é uma chave estável dentro de `faction.roles`.

Os templates [`religion.template.md`](_templates/religion.template.md), [`faction.template.md`](_templates/faction.template.md), [`family.template.md`](_templates/family.template.md) e [`law.template.md`](_templates/law.template.md) não são entidades e não alteram as quantidades existentes, que permanecem em zero.

## Ordem de leitura

1. [`Base/GDD.md`](../../../Base/GDD.md), fonte canônica atual;
2. instruções locais não versionadas, regras persistentes e limites da fase;
3. [`docs/world/AUTHORING_ORDER.md`](../../../docs/world/AUTHORING_ORDER.md), sequência obrigatória de construção;
4. [`docs/world/ID_CONVENTIONS.md`](../../../docs/world/ID_CONVENTIONS.md), convenções iniciais de IDs;
5. [`docs/world/CONTENT_MAP.md`](../../../docs/world/CONTENT_MAP.md), finalidade e dependências das categorias;
6. [`docs/world/CONTENT_STATUS.md`](../../../docs/world/CONTENT_STATUS.md), metas e progresso real;
7. este README, para as regras locais do pacote de Eldrath;
8. [`docs/world/CONTENT_SCHEMA.md`](../../../docs/world/CONTENT_SCHEMA.md), contrato comum da Fase 1;
9. [`manifest.yaml`](manifest.yaml) e os templates, conforme a categoria.

## Fase e estado atuais

A Fase 0 está concluída e a **Fase 1 — Contratos editoriais e templates** está em andamento. O contrato comum, o manifesto editorial, os schemas fundamentais, geográficos, de economia material e de sociedade, instituições e lei, seus templates e o contrato conceitual de intervenção, percepção e conhecimento foram concluídos. A hierarquia geográfica canônica é reino → região → assentamento/local, com local regional opcional; rotas apontam aos dois extremos e relações inversas serão derivadas por consulta. Presença institucional inicial parte de `faction.*`, leis partem de sua jurisdição e difusão religiosa parte de `religion.*`. O mundo definirá unidades e o reino definirá moedas internas, sem unidades ou moedas reais nesta etapa. `world.yaml` e `kingdom.yaml` continuam inexistentes. Templates definem estruturas de autoria e não são conteúdo aprovado; o ciclo editorial é `draft → in_review → approved → deprecated`, e `approved` exige revisão explícita, referências resolvidas e ausência de placeholders. Todas as categorias de entidade permanecem vazias. A próxima etapa documental cobre escolas de magia, magias, rituais, efeitos e artefatos.
