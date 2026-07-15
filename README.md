# Chronicles of Eldrath

Chronicles of Eldrath é um simulador local de reino mágico vivo, simulação social e narrativa emergente. Seu mundo deve avançar por regras reproduzíveis: personagens com conhecimento limitado tomam decisões coerentes, acontecimentos preservam causas e consequências, rumores alteram crenças e instituições, e a história permanece consultável. O usuário assume os papéis complementares de Arquiteto, Observador e Cronista, sem controlar um herói e sem precisar comandar continuamente o reino.

Além de observar a evolução do reino, o usuário poderá realizar intervenções controladas. Os personagens perceberão somente os efeitos e evidências disponíveis no mundo, formando interpretações próprias sobre suas causas.

O núcleo planejado será determinístico, local-first, predominantemente single-player e completo sem IA generativa. IA poderá futuramente atuar apenas como acabamento opcional de apresentação, nunca como fundamento lógico da simulação.

Também está prevista a geração opcional de mundos a partir de projetos públicos do GitHub, com mapa leve e funcionamento local depois da geração.

## Estado atual

O projeto está na **Fase 1 — Contratos editoriais e templates**. Os contratos editoriais e conceituais previstos para a fase foram concluídos; a auditoria editorial final, a consolidação e o encerramento explícito permanecem pendentes. A construção do mundo precede a programação. Ainda não existe aplicação executável, frontend, backend, banco de dados, framework, dependência instalada ou código-fonte.

Eldrath será construído, auditado e congelado antes das especificações de produto e interface, da preparação visual e da programação.

## Mapa da raiz

| Caminho | Finalidade atual |
|---|---|
| `docs/world/` | Reúne mapa, ordem de autoria, convenções iniciais de IDs, contratos editoriais e controle de estado. |
| `content/worlds/eldrath/` | Reserva o pacote autoral que definirá o estado inicial do mundo. |
| `assets/` | Reserva a organização de artes futuras associadas a entidades. |
| `design/` | Reserva documentação e artefatos futuros do processo visual. |
| `design/stitch/` | Reserva organizacional para uma etapa visual futura. |

Detalhes públicos da organização editorial estão no [mapa de conteúdo](docs/world/CONTENT_MAP.md), na [ordem de autoria](docs/world/AUTHORING_ORDER.md), nas [convenções de IDs](docs/world/ID_CONVENTIONS.md) e no [controle de estado](docs/world/CONTENT_STATUS.md).

## Conteúdo, assets e design

- `content/` guardará entidades, regras editoriais, dados estruturados e lore que definem o mundo inicial. O estado alterado por uma campanha será responsabilidade futura da simulação e não será regravado nesses arquivos a cada avanço de tempo.
- `assets/` guardará imagens e outros recursos complementares. Nenhuma funcionalidade dependerá de imagens, e a ausência de arte não poderá impedir o uso do conteúdo.
- `design/` guardará referências, briefings, capturas, exportações, auditorias e versões do trabalho visual futuro. Essa pasta não integra os dados canônicos do mundo.

`design/stitch/` está vazia por intenção e serve apenas como reserva para uma etapa visual futura.

## Política de assets

- Cada imagem futura deverá estar associada a uma entidade por ID.
- Metadados, direção artística, formatos finais e critérios de revisão serão definidos em etapas posteriores.
- Artes de NPCs, facções, magias, regiões, cidades e demais assentamentos serão produzidas em tarefas próprias, depois dos respectivos conteúdos e IDs.
- `assets/ui/` não deve receber botões, inputs, tabelas ou componentes de interface gerados como imagens.
- Não há imagens provisórias ou referências baixadas nesta fase.
