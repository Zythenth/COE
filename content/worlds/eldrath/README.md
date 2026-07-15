# Conteúdo do mundo de Eldrath

Esta pasta reunirá o pacote autoral que define as condições iniciais de Eldrath. Na Fase 0 ela contém somente esta orientação e a estrutura vazia das categorias; nenhuma entidade, lore nova, schema, template, `world.yaml` ou `kingdom.yaml` foi criada.

## Conteúdo inicial e estado simulado

O conteúdo inicial descreve entidades, relações, regras editoriais, fatos históricos e condições existentes antes do avanço de uma campanha. Ele será escrito em arquivos versionados e auditáveis.

O estado produzido pela simulação registrará acontecimentos e mutações de uma campanha: tempo transcorrido, decisões, eventos, relações alteradas, mortes, rumores e outras consequências. Esse estado será responsabilidade futura da programação e da persistência. A simulação não deverá reescrever os arquivos autorais a cada tick.

## Responsabilidade das pastas

| Pasta | Responsabilidade futura | Estado na Fase 0 |
|---|---|---|
| `_templates/` | Modelos editoriais aprovados para autoria consistente. | aguardando definição na Fase 1 |
| `calendars/` | Calendário, eras e representação de datas. | não iniciado |
| `languages/` | Idiomas relevantes do mundo. | não iniciado |
| `cultures/` | Culturas, normas, valores e contextos sociais. | não iniciado |
| `regions/` | Regiões, biomas, clima, fronteiras e propriedades territoriais. | não iniciado |
| `settlements/` | Capital, cidades, vilas e suas estruturas sociais e materiais. | não iniciado |
| `locations/` | Locais especiais, naturais, urbanos, ocultos e sistêmicos. | não iniciado |
| `routes/` | Conexões entre lugares, deslocamento, custos e riscos. | não iniciado |
| `npcs/` | Fichas dos NPCs-semente e suas condições iniciais. | não iniciado |
| `families/` | Famílias, casas, parentesco, herança e memória coletiva. | não iniciado |
| `factions/` | Facções, instituições, cargos, recursos e objetivos coletivos. | não iniciado |
| `religions/` | Tradições religiosas, cultos e seus contextos sociais. | não iniciado |
| `professions/` | Profissões, tarefas, competências, status e progressão. | não iniciado |
| `creatures/` | Espécies, habitat, comportamento, ecologia e relação com magia. | não iniciado |
| `resources/` | Recursos materiais e arcanos relevantes para a vida do reino. | não iniciado |
| `items/` | Itens relevantes, propriedades, uso e proveniência. | não iniciado |
| `laws/` | Leis gerais, mágicas e detalhadas por jurisdição. | não iniciado |
| `diseases/` | Doenças, transmissão, sintomas, gravidade e tratamentos. | não iniciado |
| `events/` | Eventos históricos e eventos-base que compõem o estado inicial. | não iniciado |
| `rumors/` | Rumores iniciais ou gatilhos, origens e referências causais. | não iniciado |
| `magic/schools/` | Escolas mágicas, relações, acesso e status. | não iniciado |
| `magic/spells/` | Magias com requisitos, custos, efeitos, riscos e lore complementar. | não iniciado |
| `magic/rituals/` | Rituais e suas regras estruturadas. | não iniciado |
| `magic/artifacts/` | Artefatos, efeitos, proveniência e história. | não iniciado |
| `magic/effects/` | Efeitos mágicos estruturados e referenciáveis. | não iniciado |

`_templates/` não deve receber modelos improvisados. Seus arquivos serão definidos na Fase 1 depois das convenções definitivas, schemas editoriais e regras de referências cruzadas.

## IDs e referências

- Cada entidade persistente terá um ID estável no formato `tipo.nome_estavel`.
- IDs usam minúsculas, ASCII, underscore e prefixo de tipo.
- Nomes visíveis podem mudar e nunca funcionam como chave permanente.
- Referências entre entidades usam IDs, não nomes.
- Uma referência ausente é erro; não deve ser resolvida por suposição.
- IDs removidos não são reciclados e um ID representa apenas uma entidade.

As regras organizadas estão em [`docs/world/ID_CONVENTIONS.md`](../../../docs/world/ID_CONVENTIONS.md).

## Dados estruturados e lore

Markdown estruturado e YAML serão usados futuramente conforme o tipo de entidade. Front matter YAML poderá armazenar dados conhecidos pelo sistema, enquanto o corpo Markdown poderá registrar lore e explicações. Os formatos definitivos pertencem à Fase 1.

Dados mecânicos e lore devem permanecer distinguíveis:

- custos, condições, efeitos, duração, referências e demais informações necessárias ao funcionamento pertencem à parte estruturada;
- contexto histórico, interpretação e texto de apresentação pertencem à prosa;
- prosa nunca substitui dados necessários nem altera silenciosamente uma regra estruturada;
- o conteúdo deve permanecer completo e utilizável sem IA generativa.

Assets são complementares: nenhuma entidade ou regra depende de imagem, e a ausência de arte não invalida conteúdo. A pasta `design/` trata do processo visual futuro e não faz parte dos dados do mundo.

## Ordem de leitura

1. [`Base/GDD.md`](../../../Base/GDD.md), fonte canônica atual;
2. instruções locais não versionadas, regras persistentes e limites da fase;
3. [`docs/world/AUTHORING_ORDER.md`](../../../docs/world/AUTHORING_ORDER.md), sequência obrigatória de construção;
4. [`docs/world/ID_CONVENTIONS.md`](../../../docs/world/ID_CONVENTIONS.md), convenções iniciais de IDs;
5. [`docs/world/CONTENT_MAP.md`](../../../docs/world/CONTENT_MAP.md), finalidade e dependências das categorias;
6. [`docs/world/CONTENT_STATUS.md`](../../../docs/world/CONTENT_STATUS.md), metas e progresso real;
7. este README, para as regras locais do pacote de Eldrath;
8. templates e contratos editoriais, somente depois que forem criados e aprovados na Fase 1.

## Fase e estado atuais

A fase atual é a **Fase 0 — Fundação editorial**. A estrutura foi criada, mas todos os grupos de conteúdo estão não iniciados; `_templates/` aguarda a definição dos contratos editoriais. Nenhuma pasta deve ser preenchida apenas para parecer completa.
