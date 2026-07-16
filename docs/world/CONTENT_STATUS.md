# Estado do conteúdo

Fase 0 concluída. Fase 1 concluída e encerrada após auditoria editorial final aprovada. A Fase 2 está em andamento: existe 1 mundo planejado e 1 mundo real, `world.eldrath`, agora `approved`; existe também 1 calendário real, `calendar.marco`, atualmente `in_review`. O contrato conceitual de geração opcional por projetos públicos do GitHub permanece concluído. Objetivos, medos, segredos, memórias, crenças, conhecimento e relações usam subregistros incorporados; eventos concretos, transmissões, grupos, hordas, ataques, incursões e demais estados atuais pertencem ao save. As quantidades existentes contam entidades reais nos arquivos de conteúdo, não menções, schemas ou templates. Todas as outras categorias continuam com quantidade existente igual a zero. A próxima atividade é aprovar o calendário e criar os idiomas.

Estado das subetapas recentes da Fase 1:

- economia material: concluída;
- contrato de intervenção, percepção e conhecimento: concluído;
- contratos e templates de religião, facção, família e lei: concluídos;
- entidades reais de religião, facção, família e lei: não iniciadas;
- contratos de escolas mágicas, magias, rituais, efeitos e artefatos: concluídos;
- templates de escola mágica, magia, ritual, efeito mágico e artefato: concluídos;
- entidades reais do sistema mágico: não iniciadas;
- contratos de criaturas e doenças: concluídos;
- templates de criatura e doença: concluídos;
- contrato conceitual de saúde e condições relacionadas: concluído;
- entidades reais de criatura e doença: não iniciadas;
- contrato de NPCs, personalidade, valores, necessidades, emoções, objetivos, relações, memória, conhecimento, reputação, inventário, afinidade e domínio mágico: concluído;
- template de NPC persistente: concluído;
- entidades reais de NPC: não iniciadas;
- contratos de eventos, rumores, história, cadeias causais, arcos e gatilhos: concluídos;
- templates de evento, rumor e conflito: concluídos;
- contrato de ameaças monstruosas, grupos, hordas, ataques e incursões: concluído;
- contrato de geração opcional derivada do GitHub, mapa conceitual, funcionamento offline, saves, checkpoints, ramificações, reinício e velocidade: concluído;
- consulta a perfil, snapshot real, mapa visual e implementação: não iniciados; implementação continua proibida;
- conteúdo real de eventos, rumores, conflitos, criaturas e ameaças: não iniciado;
- auditoria editorial final e consolidação: concluídas;
- Fase 1: concluída e encerrada;
- identidade geral de Eldrath: `world.eldrath` aprovado;
- calendários: `calendar.marco` criado e em revisão; quantidade existente igual a 1;
- Fase 2: em andamento; próxima atividade é a aprovação do calendário e a criação dos idiomas.

| Categoria | Quantidade planejada | Quantidade existente | Estado | Dependências | Fase responsável | Documento responsável | Observações | Última atualização |
|---|---:|---:|---|---|---|---|---|---|
| Mundo | 1 | 1 | aprovado | contratos editoriais fundamentais | Fase 2 | `content/worlds/eldrath/world.yaml` | `world.eldrath` preserva a identidade geral e referencia `calendar.marco`; data inicial, era inicial, idiomas, culturas, reino e geografia permanecem fora do escopo atual. | 2026-07-16 |
| Reino | 1 | 0 | não iniciado | identidade, calendário, culturas e contratos editoriais | Fase 2 | `content/worlds/eldrath/kingdom.yaml` (futuro) | O arquivo não deve ser criado nesta atividade. | 2026-07-15 |
| Regiões | 4 | 0 | não iniciado | reino, culturas, geografia e contratos editoriais | Fase 3 | `content/worlds/eldrath/regions/` | Schema e template concluídos; nenhuma região foi criada. | 2026-07-15 |
| Capital | 1 | 0 | não iniciado | reino e região correspondente | Fase 3 | `content/worlds/eldrath/settlements/` | É papel administrativo de assentamento; nenhuma capital foi criada. | 2026-07-15 |
| Cidades | 3 | 0 | não iniciado | regiões, rotas, recursos e economia | Fase 3 | `content/worlds/eldrath/settlements/` | Schema e template concluídos; não inclui a capital na contagem canônica. | 2026-07-15 |
| Vilas | 4 | 0 | não iniciado | regiões, rotas, recursos e economia | Fase 3 | `content/worlds/eldrath/settlements/` | Schema e template concluídos; nenhuma vila foi criada. | 2026-07-15 |
| Locais especiais | 12 | 0 | não iniciado | regiões e assentamentos | Fase 3 | `content/worlds/eldrath/locations/` | Schema e template concluídos; nenhum local foi criado. | 2026-07-15 |
| Facções principais | 8 | 0 | não iniciado | reino, religiões, economia e culturas | Fase 4 | `content/worlds/eldrath/factions/` | Schema e template concluídos; instituições usam `faction.*`; nenhuma facção foi criada. | 2026-07-15 |
| Famílias relevantes | 6 | 0 | não iniciado | culturas, assentamentos, facções e leis | Fase 4 | `content/worlds/eldrath/families/` | Schema e template concluídos; nenhuma família ou casa foi criada. | 2026-07-15 |
| Tradições religiosas | 3 | 0 | não iniciado | cosmologia necessária e culturas | Fases 2 e 4 | `content/worlds/eldrath/religions/` | Schema e template concluídos; culto como organização usa `faction.*`; nenhuma tradição foi criada. | 2026-07-15 |
| Instituições mágicas | 5 | 0 | não iniciado | reino, leis, facções e sistema mágico | Fase 4 | `content/worlds/eldrath/factions/` | Instituições mágicas são facções, não escolas; o GDD não resolve se as cinco integram as oito facções principais, e a sobreposição continua adiada. | 2026-07-15 |
| NPCs-semente | 30 | 0 | não iniciado | mundo macro, sociedade, magia e planejamento de NPCs | Fase 5 | `content/worlds/eldrath/npcs/` | Schema e template concluídos; o GDD contém âncoras canônicas, mas ainda não há fichas de conteúdo. | 2026-07-15 |
| NPCs persistentes | até 150 | 0 | não iniciado | NPCs-semente e futura simulação | Fases 5 e 12 | `content/worlds/eldrath/npcs/` | Schema e template concluídos; a pasta contém somente `.gitkeep`; estado simulado será responsabilidade futura. | 2026-07-15 |
| Magias | 60 | 0 | não iniciado | escolas, efeitos, instituições e leis mágicas | Fase 4 | `content/worlds/eldrath/magic/spells/` | Schema e template concluídos; nenhuma magia foi criada. | 2026-07-15 |
| Artefatos | 12 | 0 | não iniciado | escolas, efeitos, itens e história | Fase 4 | `content/worlds/eldrath/magic/artifacts/` | Schema e template concluídos; nenhum artefato foi criado. | 2026-07-15 |
| Profissões | 20 | 0 | não iniciado | produção, comércio, instituições e assentamentos | Fase 3 | `content/worlds/eldrath/professions/` | Schema e template concluídos; a meta continua em 20 e a quantidade existente continua zero. | 2026-07-15 |
| Eventos-base | 40 | 0 | não iniciado | entidades do mundo, causalidade e cronologia | Fase 5 | `content/worlds/eldrath/events/` | Contrato e template concluídos; `event.*` é conteúdo estático e evento concreto de campanha usa identidade técnica separada; a pasta contém somente `.gitkeep`. | 2026-07-15 |
| Rumores iniciais ou gatilhos | 20 | 0 | não iniciado | eventos, NPCs, facções e lugares | Fase 5 | `content/worlds/eldrath/rumors/` | Contrato e template concluídos; a pasta contém somente `.gitkeep`; nenhum rumor ou gatilho foi criado. | 2026-07-15 |
| Conflitos latentes | 8 | 0 | não iniciado | NPCs, facções, eventos, rumores, relações e ameaças | Fase 5 | `content/worlds/eldrath/conflicts/` | Contrato e template concluídos; a pasta contém somente `.gitkeep`; estado atual e resultado pertencem ao save. | 2026-07-15 |
| Calendários | a definir | 1 | em revisão | identidade geral e contratos editoriais | Fase 2 | `content/worlds/eldrath/calendars/` | `calendar.marco` define duas eras, dez períodos, seis dias semanais, cinco estações e ano fixo de 360 dias; não foi aprovado nesta tarefa. | 2026-07-16 |
| Idiomas | a definir | 0 | não iniciado | identidade geral e contratos editoriais | Fase 2 | `content/worlds/eldrath/languages/` | O GDD não fixa quantidade. | 2026-07-15 |
| Culturas | a definir | 0 | não iniciado | identidade, calendário e idiomas | Fase 2 | `content/worlds/eldrath/cultures/` | O GDD não fixa quantidade. | 2026-07-15 |
| Rotas | a definir | 0 | não iniciado | regiões, assentamentos e locais | Fase 3 | `content/worlds/eldrath/routes/` | Schema e template concluídos; nenhuma rota foi criada. | 2026-07-15 |
| Recursos | a definir | 0 | não iniciado | regiões, clima e economia | Fase 3 | `content/worlds/eldrath/resources/` | Schema e template concluídos; a lista conceitual do GDD não é uma contagem de arquivos aprovados. | 2026-07-15 |
| Itens | a definir | 0 | não iniciado | recursos, profissões, economia e magia | Fase 4 | `content/worlds/eldrath/items/` | Schema e template concluídos; o GDD não fixa quantidade e nenhum item foi criado. | 2026-07-15 |
| Escolas mágicas | 15 | 0 | não iniciado | princípios mágicos, instituições e leis | Fase 4 | `content/worlds/eldrath/magic/schools/` | Schema e template concluídos; escolas e subescolas usam `magic_school.*`; nenhuma escola foi criada. | 2026-07-15 |
| Rituais | a definir | 0 | não iniciado | escolas, magias, efeitos e instituições | Fase 4 | `content/worlds/eldrath/magic/rituals/` | Schema e template concluídos; o GDD não fixa quantidade e nenhum ritual foi criado. | 2026-07-15 |
| Efeitos mágicos | a definir | 0 | não iniciado | contratos editoriais e regras de magia | Fase 4 | `content/worlds/eldrath/magic/effects/` | Schema e template concluídos; o GDD não fixa quantidade e nenhuma definição de efeito foi criada. | 2026-07-15 |
| Criaturas | a definir | 0 | não iniciado | geografia, ecologia, economia, magia e saúde | Fase 4 | `content/worlds/eldrath/creatures/` | Schema e template concluídos; `creature.*` representa espécie ou tipo; o GDD não fixa quantidade e nenhuma criatura foi criada. | 2026-07-15 |
| Doenças | a definir | 0 | não iniciado | ambiente, criaturas, saúde, recursos, profissões, magia, leis e percepção | Fase 4 | `content/worlds/eldrath/diseases/` | Schema e template concluídos; instâncias pertencem ao save; o GDD não fixa quantidade e nenhuma doença foi criada. | 2026-07-15 |
| Leis | a definir | 0 | não iniciado | reino, política, culturas e magia | Fases 2 e 4 | `content/worlds/eldrath/laws/` | Schema e template concluídos; abrange leis gerais, mágicas e detalhadas; quantidade não definida e nenhuma lei foi criada. | 2026-07-15 |

O estado `não iniciado` significa que a pasta foi reservada, mas não contém entidades. Existem duas entidades reais: `world.eldrath`, aprovado, e `calendar.marco`, em revisão; todas as outras metas canônicas continuam com quantidade existente igual a zero. Schemas e templates concluídos, inclusive os de criaturas, doenças, NPCs, eventos, rumores e conflitos, não alteram essas quantidades. O contrato GitHub não cria categoria contável, não altera as contagens de Eldrath e não substitui o cenário canônico. Saúde e condições são estruturas compartilhadas; objetivos, medos, segredos, memórias, crenças, conhecimento e relações do NPC são subregistros incorporados. Hordas, ataques e incursões concretos são estado da campanha, não categorias contáveis de conteúdo inicial. Alterações posteriores devem atualizar quantidade existente, estado, documento responsável e data somente depois que o conteúdo real for criado e validado.
