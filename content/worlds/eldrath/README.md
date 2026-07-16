# Conteúdo do mundo de Eldrath

Esta pasta reúne o pacote autoral que definirá as condições iniciais de Eldrath. A Fase 1 foi concluída após auditoria e consolidação do manifesto, dos contratos e dos templates. A Fase 2 foi iniciada com [`world.yaml`](world.yaml), primeira entidade real do pacote, identificada como `world.eldrath` e atualmente `in_review`. As demais categorias continuam vazias; calendário, idiomas, culturas, reino e geografia ainda não foram iniciados.

O pacote é identificado por [`manifest.yaml`](manifest.yaml). Para autoria, leia nesta ordem o [checklist de validação manual](../../../docs/world/MANUAL_VALIDATION_CHECKLIST.md), o [contrato comum](../../../docs/world/CONTENT_SCHEMA.md), o [registro de vocabulários](../../../docs/world/CONTROLLED_VOCABULARY.md), o schema especializado aplicável e o template correspondente.

`world.eldrath` define somente a identidade geral: mundo vivo, causalidade, conhecimento limitado, magia sistêmica, instituições relevantes, vida cotidiana, conflito consequente, transformação histórica, variedade de trajetórias e ausência de protagonista obrigatório. Os campos de calendário, data inicial, era, idiomas, culturas e reino permanecem sem referências porque suas entidades ainda não existem. Nenhuma unidade concreta foi definida nesta atividade.

## Conteúdo inicial e estado simulado

O conteúdo inicial descreve entidades, relações, regras editoriais, fatos históricos e condições existentes antes do avanço de uma campanha. Ele será escrito em arquivos versionados e auditáveis.

O estado produzido pela simulação registrará acontecimentos e mutações de uma campanha: tempo transcorrido, decisões, eventos, relações alteradas, mortes, rumores e outras consequências. Intervenções do Arquiteto, comandos, `item_instance`, quantidades atuais de recursos, evidências, percepções, crenças adquiridas, memórias, rumores derivados, populações, grupos, hordas, forças, ataques e incursões em andamento também pertencerão a esse estado. Esse estado será responsabilidade futura da programação e da persistência. A simulação não deverá reescrever os arquivos autorais a cada tick.

O conteúdo estático poderá definir capacidades, limites e condições permitidas, mas não haverá pasta, template, entidade ou quantidade planejada de “intervenções iniciais”. Fatos, percepções, interpretações, crenças e conhecimento permanecem conceitos distintos conforme o [contrato de intervenção, percepção e conhecimento](../../../docs/world/schemas/INTERVENTION_PERCEPTION_AND_KNOWLEDGE.md).

Na economia, os arquivos autorais poderão registrar propriedades estáveis, valores e relações iniciais, capacidades, métodos permitidos e referências. Estoque, preço, produção, consumo, salário, riqueza e tráfego atuais, além de escassez, inflação, dívida e contratos ativos, pertencerão ao estado futuro.

## Eldrath e os modos de criação

Eldrath permanece o cenário canônico e será construído normalmente nas Fases 2 a 6. Os modos futuros de criação são Eldrath canônico, criação manual e mundo derivado de um snapshot confirmado de projetos públicos do GitHub.

O modo derivado reutiliza os contratos editoriais, mas produz outro pacote inicial e não escreve entidades nesta pasta, não altera o manifesto, não modifica as metas numéricas e não substitui o conteúdo oficial. Depois da criação, esse mundo usa snapshot, mapa-base e checkpoint locais e continua sem nova consulta externa. O contrato detalhado está em [GITHUB_DERIVED_WORLD_GENERATION.md](../../../docs/world/schemas/GITHUB_DERIVED_WORLD_GENERATION.md).

## Responsabilidade das pastas

| Pasta | Responsabilidade futura | Estado atual |
|---|---|---|
| `_templates/` | Modelos editoriais aprovados para autoria consistente. | template genérico, cinco templates fundamentais, quatro geográficos, três de economia material, quatro de sociedade, instituições e lei, cinco do sistema mágico, dois de criaturas e doenças, um de NPC e três de eventos, rumores e conflitos disponíveis; não são conteúdo real |
| `calendars/` | Calendário, eras e representação de datas. | não iniciado |
| `languages/` | Idiomas relevantes do mundo. | não iniciado |
| `cultures/` | Culturas, normas, valores e contextos sociais. | não iniciado |
| `regions/` | Regiões, biomas, clima, fronteiras e propriedades territoriais. | schema e template disponíveis; pasta real vazia |
| `settlements/` | Capital, cidades, vilas e suas estruturas sociais e materiais. | schema e template disponíveis; pasta real vazia |
| `locations/` | Locais especiais, naturais, urbanos, ocultos e sistêmicos. | schema e template disponíveis; pasta real vazia |
| `routes/` | Conexões entre lugares, deslocamento, custos e riscos. | schema e template disponíveis; pasta real vazia |
| `npcs/` | Fichas dos NPCs-semente, perfil, condições iniciais e subregistros incorporados. | schema e template disponíveis; contém somente `.gitkeep`; zero NPCs |
| `families/` | Famílias, linhagens, casas dinásticas, herança familiar e legado. | schema e template disponíveis; pasta real vazia; zero famílias |
| `factions/` | Facções, instituições, cargos, autoridade, presença inicial e objetivos coletivos. | schema e template disponíveis; pasta real vazia; zero facções |
| `religions/` | Tradições religiosas, cultos como crença, doutrinas, práticas e diversidade. | schema e template disponíveis; pasta real vazia; zero religiões |
| `professions/` | Profissões, tarefas, competências, status e progressão. | schema e template disponíveis; pasta real vazia; zero profissões |
| `creatures/` | Espécies e tipos, anatomia abstrata, habitat, comportamento, ecologia, saúde estrutural, capacidades de ameaça e relação com magia. | schema e template disponíveis; pasta real vazia; zero criaturas; quantidade a definir |
| `resources/` | Recursos materiais e arcanos relevantes para a vida do reino. | schema e template disponíveis; pasta real vazia; zero recursos |
| `items/` | Definições de itens relevantes, propriedades, uso e proveniência. | schema e template disponíveis; pasta real vazia; zero itens |
| `laws/` | Leis gerais, mágicas e detalhadas por jurisdição, vigência e autoridade. | schema e template disponíveis; pasta real vazia; zero leis |
| `diseases/` | Definições de doenças, transmissão, estágios, sintomas, diagnóstico e tratamentos possíveis. | schema e template disponíveis; pasta real vazia; zero doenças; quantidade a definir; instâncias pertencem ao save |
| `events/` | Eventos históricos e eventos-base de conteúdo, com causas, consequências, projeções e gatilhos autorais. | schema e template disponíveis; contém somente `.gitkeep`; zero eventos de 40 planejados |
| `rumors/` | Rumores iniciais de conteúdo, versões, genealogia, origens e referências causais. | schema e template disponíveis; contém somente `.gitkeep`; zero rumores de 20 planejados |
| `conflicts/` | Conflitos latentes, partes, interesses, pressões, escalada, gatilhos e resoluções possíveis. | schema e template disponíveis; contém somente `.gitkeep`; zero conflitos de 8 planejados |
| `magic/schools/` | Escolas e subescolas mágicas, princípios, taxonomia e relações. | schema e template disponíveis; pasta real vazia; zero escolas |
| `magic/spells/` | Magias com requisitos, custos, efeitos, riscos e lore complementar. | schema e template disponíveis; pasta real vazia; zero magias |
| `magic/rituals/` | Rituais, papéis, etapas, interrupções e resultados estruturados. | schema e template disponíveis; pasta real vazia; zero rituais |
| `magic/artifacts/` | Artefatos, efeitos, estado inicial, proveniência e história. | schema e template disponíveis; pasta real vazia; zero artefatos |
| `magic/effects/` | Definições de efeitos mágicos estruturadas e referenciáveis. | schema e template disponíveis; pasta real vazia; zero efeitos |

`_templates/` contém o template genérico [`base_entity.md`](_templates/base_entity.md), que reúne apenas os campos comuns. Um template especializado parte dele e adiciona somente os campos documentados para uma categoria. A pasta nunca é conteúdo real e deve ser excluída pelo futuro carregador. Quando uma pasta-folha recebe conteúdo real, seu `.gitkeep` deve ser removido; por isso `_templates/.gitkeep` foi removido ao receber seus arquivos reais de template.

## IDs e referências

- Cada entidade persistente terá um ID estável no formato `tipo.nome_estavel`.
- IDs usam minúsculas, ASCII, underscore e prefixo de tipo.
- Nomes visíveis podem mudar e nunca funcionam como chave permanente.
- Referências entre entidades usam IDs, não nomes.
- Uma referência ausente é erro; não deve ser resolvida por suposição.
- IDs removidos não são reciclados e um ID representa apenas uma entidade.

As regras organizadas estão em [`docs/world/ID_CONVENTIONS.md`](../../../docs/world/ID_CONVENTIONS.md) e no [contrato editorial comum](../../../docs/world/CONTENT_SCHEMA.md).

## Dados estruturados e lore

Entidades com lore usarão Markdown com front matter YAML; YAML puro é reservado a manifestos, índices e estruturas sem corpo narrativo. O front matter armazena dados estruturados do conteúdo, enquanto o corpo Markdown registra lore e explicações; isso não significa que todo campo estruturado seja conhecimento de um NPC. Os schemas fundamentais, geográficos, de economia material, de sociedade, instituições e lei, do sistema mágico, de criaturas, saúde e doenças, de NPCs, de eventos, rumores, história e conflitos, de ameaças monstruosas e incursões e de geração opcional de mundo, além do contrato transversal de intervenção, estão no [índice de schemas](../../../docs/world/schemas/README.md).

Dados mecânicos e lore devem permanecer distinguíveis:

- custos, condições, efeitos, duração, referências e demais informações necessárias ao funcionamento pertencem à parte estruturada;
- contexto histórico, interpretação e texto de apresentação pertencem à prosa;
- prosa nunca substitui dados necessários nem altera silenciosamente uma regra estruturada;
- o conteúdo deve permanecer completo e utilizável sem IA generativa.

Assets são complementares: nenhuma entidade ou regra depende de imagem, e a ausência de arte não invalida conteúdo. A pasta `design/` trata do processo visual futuro e não faz parte dos dados do mundo.

## Recurso, item, artefato e instância

- **Recurso** é fungível, mensurável e tratado economicamente por quantidade.
- **Item** é a definição de um tipo de objeto discreto, possivelmente agregável ou durável; seu arquivo não representa cada cópia.
- **Artefato** é uma entidade do sistema mágico para objeto único, nomeado, singular, historicamente significativo ou persistentemente relevante, com origem, poderes, riscos e história próprios; pode referenciar um item-base sem ser reduzido a item comum.
- **Instância de item** será uma cópia pertencente ao estado da simulação e poderá guardar proprietário, localização, quantidade, condição, durabilidade, proveniência e modificadores.

Os templates [`resource.template.md`](_templates/resource.template.md), [`profession.template.md`](_templates/profession.template.md) e [`item.template.md`](_templates/item.template.md) materializam somente os contratos de autoria. As pastas `resources/`, `professions/` e `items/` continuam contendo apenas seus arquivos `.gitkeep`.

## Religião, instituição, família e lei

- **Religião** define tradição de crença, doutrina e prática; uma organização religiosa é `faction.*`, e a facção referencia a religião.
- **Facção** define organização, cargos, autoridade, políticas e presença territorial inicial; membros e ocupantes atuais pertencerão a NPCs e ao save.
- **Família** define identidade, linhagem conceitual, tradição e herança familiar; parentesco concreto pertencerá às relações de NPCs. Uma casa política usa também `faction.*`, com referência da facção para a família.
- **Lei** define regra pública reconhecida, jurisdição, vigência, condições, exceções e sanções; crimes, processos, evidências e julgamentos pertencerão a eventos e ao estado.
- **Profissão** permanece atividade econômica; **cargo** é uma chave estável dentro de `faction.roles`.

Os templates [`religion.template.md`](_templates/religion.template.md), [`faction.template.md`](_templates/faction.template.md), [`family.template.md`](_templates/family.template.md) e [`law.template.md`](_templates/law.template.md) não são entidades e não alteram as quantidades existentes, que permanecem em zero.

## Escola, instituição, magia, ritual, efeito e artefato

- **Escola mágica** usa `magic_school.*` e define princípios, domínio, métodos e taxonomia; uma subescola usa a mesma entidade com `parent_school_id`.
- **Instituição mágica** é `faction.*` e define membros, cargos, ensino, pesquisa, segredo, licenciamento e poder social. Escola nunca possui membros, líder, professores atuais ou tesouro.
- **Magia** é técnica individual reproduzível; **ritual** é procedimento com preparação, papéis, etapas, condições e interrupções. Tempo longo sozinho não transforma magia em ritual.
- **Efeito mágico** `magic_effect.*` é definição reutilizável; sua aplicação atual pertence ao save e não possui template de conteúdo.
- **Artefato** tem identidade singular e pode apontar `base_item_id`; o item-base não mantém lista inversa e o mesmo objeto único não recebe `item_instance` concorrente.
- Custos, alcance, duração, alvos, riscos, falhas, corrupção, sinais e evidências usam estruturas verificáveis. Legalidade efetiva é derivada de leis por jurisdição e estado, nunca de um campo global simples.

Os templates [`magic_school.template.md`](_templates/magic_school.template.md), [`spell.template.md`](_templates/spell.template.md), [`ritual.template.md`](_templates/ritual.template.md), [`magic_effect.template.md`](_templates/magic_effect.template.md) e [`artifact.template.md`](_templates/artifact.template.md) não são entidades. As metas permanecem 15 escolas, 60 magias, 12 artefatos e 5 instituições mágicas; rituais e efeitos continuam `a definir`, e todas as quantidades existentes continuam em zero.

## Criatura, indivíduo, doença e condição de saúde

- **Criatura** `creature.*` é espécie, tipo ou arquétipo. População inicial pode ser agregada; população e distribuição atuais pertencem ao save.
- **Indivíduo persistente** usa futuramente `npc.*` e referencia sua espécie ou tipo. Uma entidade de criatura não concorre com um NPC para a mesma identidade.
- **Doença** `disease.*` é definição estática. A instância concreta, inclusive uma infecção, pertence ao save.
- **Sintoma**, **ferimento**, **dor**, **fadiga**, **deficiência**, **envenenamento** e **intoxicação** são estruturas ou estados compartilhados, não entidades com pasta e prefixo próprios.
- **Diagnóstico** e **prognóstico conhecido** pertencem ao observador e podem divergir da verdade. Conhecimento médico sempre exige fonte válida.
- **Condição geral de saúde** é derivada dos componentes detalhados; não é valor manual concorrente.
- **Legalidade** de caça, criação, comércio, isolamento ou tratamento é derivada das leis aplicáveis.

Os templates [`creature.template.md`](_templates/creature.template.md) e [`disease.template.md`](_templates/disease.template.md) materializam somente as definições estáticas. Não existe `conditions/`, template de condição ou prefixo para ocorrências de saúde. Criaturas e doenças continuam com quantidade planejada `a definir` e quantidade existente zero.

## NPC, perfil, estado inicial e campanha

- **Perfil do NPC** registra identidade, nascimento, origem, aparência-base, personalidade, valores, capacidades e sensibilidades.
- **Estado inicial** fica inteiramente sob `initial_state` e pode semear localização, afiliações, necessidades, emoções, saúde, inventário, magia, objetivos, conhecimento, memória, relações e rotina.
- **Estado da campanha** possui os valores atuais e todas as mudanças posteriores; o arquivo autoral não é reescrito a cada tick.
- Objetivos, medos, segredos, memórias, crenças, conhecimento e relações usam IDs incorporados `goal.*`, `fear.*`, `secret.*`, `memory.*`, `belief.*`, `knowledge.*` e `relationship.*`; não criam pastas.
- Família não mantém membros, facção não mantém ocupantes, profissão não é cargo nem competência e biografia não concede conhecimento.
- Inventário inicial materializa `item_instance` no save; artefatos preservam identidade única; domínio mágico sempre registra fonte.

O template [`npc.template.md`](_templates/npc.template.md) materializa o [contrato de NPCs](../../../docs/world/schemas/NPC_SYSTEM_ENTITIES.md), não é entidade e não altera as metas de 30 NPCs-semente e até 150 persistentes. A pasta `npcs/` continua contendo somente `.gitkeep`.

## Evento, rumor, conflito e ameaça monstruosa

- **Evento de conteúdo** `event.*` registra fato histórico ou evento-base autoral; **evento de campanha** é ocorrência técnica do save e não recebe arquivo na pasta `events/`.
- **Rumor** `rumor.*` é uma alegação transmissível com fonte e genealogia próprias; não é sinônimo de fato, crença, memória, lenda ou causa real.
- **Conflito** `conflict.*` descreve tensão latente, partes, interesses, pressões, escalada, gatilhos e resoluções possíveis sem predeterminar vencedor.
- **Criatura** `creature.*` continua sendo espécie, tipo ou arquétipo; indivíduo persistente usa `npc.*`, enquanto população, grupo, horda e força são representações agregadas do estado.
- **Ameaça** é uma condição capaz de produzir dano; **ataque** é uma ação delimitada; **incursão** é um processo causal com formação, aproximação, sinais, resposta, resolução e consequências.
- Ataques, incursões, ninhos ativos, portais ativos, ocupações e corrupções em curso pertencem ao save. O conteúdo estático define capacidades, limitações e sementes aprovadas, não resultados inevitáveis.

Os templates [`event.template.md`](_templates/event.template.md), [`rumor.template.md`](_templates/rumor.template.md) e [`conflict.template.md`](_templates/conflict.template.md) materializam o [contrato de eventos, rumores, história e conflitos](../../../docs/world/schemas/EVENT_RUMOR_HISTORY_AND_CONFLICT_ENTITIES.md). Capacidades de espécie e as fronteiras de ataques e incursões seguem o [contrato de ameaças monstruosas e incursões](../../../docs/world/schemas/MONSTROUS_THREATS_AND_INCURSIONS.md). Nenhum desses templates cria entidade real nem altera as metas de 40 eventos-base, 20 rumores iniciais ou gatilhos e 8 conflitos latentes.

## Ordem de leitura

1. [`docs/world/AUTHORING_ORDER.md`](../../../docs/world/AUTHORING_ORDER.md), sequência obrigatória de construção;
2. [`docs/world/ID_CONVENTIONS.md`](../../../docs/world/ID_CONVENTIONS.md), convenções iniciais de IDs;
3. [`docs/world/CONTENT_MAP.md`](../../../docs/world/CONTENT_MAP.md), finalidade e dependências das categorias;
4. [`docs/world/CONTENT_STATUS.md`](../../../docs/world/CONTENT_STATUS.md), metas e progresso real;
5. este README, para as regras locais do pacote de Eldrath;
6. [`docs/world/CONTENT_SCHEMA.md`](../../../docs/world/CONTENT_SCHEMA.md), contrato comum da Fase 1;
7. [`manifest.yaml`](manifest.yaml) e os templates, conforme a categoria.

## Fase e estado atuais

A Fase 0 e a **Fase 1 — Contratos editoriais e templates** estão concluídas. A auditoria editorial final aprovou e consolidou o contrato comum, o manifesto, os schemas especializados, os templates e os contratos conceituais transversais. A **Fase 2 — Fundamentos do mundo** foi iniciada. `world.yaml` existe como `world.eldrath`, está `in_review` e é a única entidade real do pacote. O reino definirá moedas internas; nenhuma unidade concreta foi criada nesta atividade. `kingdom.yaml` continua inexistente, e todas as categorias de entidade em subpastas permanecem vazias. Templates definem estruturas de autoria e não são conteúdo aprovado; o ciclo editorial é `draft → in_review → approved → deprecated`, e `approved` exige revisão explícita, referências resolvidas e ausência de placeholders. O contrato GitHub não altera o pacote nem suas contagens. A próxima atividade é revisar a identidade geral e, após sua aprovação, criar o calendário.
