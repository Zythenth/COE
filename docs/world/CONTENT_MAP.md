# Mapa de conteúdo de Eldrath

Este mapa registra a estrutura editorial de Eldrath. A fundação da Fase 0, o contrato comum e os schemas e templates fundamentais da Fase 1 estão concluídos; as pastas de categorias continuam vazias e nenhum conteúdo real ou lore do mundo foi criado.

| Caminho | Categoria | Finalidade | Tipo de conteúdo futuro | Formato planejado | Dependências | Fase responsável | Estado atual |
|---|---|---|---|---|---|---|---|
| `content/worlds/eldrath/` | pacote do mundo | Reunir o estado inicial autoral de Eldrath. | manifesto, dados e lore do mundo | Markdown estruturado e YAML | GDD e contrato editorial comum | Fases 1–6 | manifesto criado; sem entidades |
| `content/worlds/eldrath/manifest.yaml` | manifesto editorial | Identificar o pacote, seus caminhos e categorias reconhecidas. | metadados do pacote, sem lore | YAML | GDD e contrato editorial comum | Fase 1 | criado |
| `content/worlds/eldrath/_templates/` | templates | Padronizar a autoria de cada tipo de entidade. | modelos editoriais | YAML puro e Markdown com front matter YAML | contrato comum e schemas especializados | Fase 1 | template comum e cinco templates fundamentais concluídos; sem conteúdo real |
| `docs/world/CONTENT_SCHEMA.md` | contrato comum | Definir regras compartilhadas de formato, IDs, referências e revisão. | contrato editorial documental | Markdown | GDD | Fase 1 | criado e concluído |
| `docs/world/schemas/` | schemas especializados | Definir contratos editoriais por conjunto de entidades. | contratos editoriais documentais | Markdown | GDD e contrato comum | Fase 1 | `FOUNDATIONAL_ENTITIES.md` concluído; schemas geográficos não iniciados |
| `content/worlds/eldrath/calendars/` | calendários | Representar calendário, eras e datas do mundo. | dados temporais e explicações | Markdown estruturado e/ou YAML, a definir | identidade geral e contratos editoriais | Fase 2 | não iniciado |
| `content/worlds/eldrath/languages/` | idiomas | Registrar idiomas relevantes de Eldrath. | dados linguísticos e lore | Markdown estruturado e/ou YAML, a definir | identidade geral e contratos editoriais | Fase 2 | não iniciado |
| `content/worlds/eldrath/cultures/` | culturas | Registrar culturas, valores, normas e contexto social. | dados culturais e lore | Markdown estruturado e/ou YAML, a definir | identidade, calendário e idiomas | Fase 2 | não iniciado |
| `content/worlds/eldrath/regions/` | regiões | Descrever as divisões territoriais e suas propriedades. | dados geográficos, ambientais e sociais | Markdown estruturado e/ou YAML, a definir | reino, culturas e contratos editoriais | Fase 3 | não iniciado |
| `content/worlds/eldrath/settlements/` | assentamentos | Representar capital, cidades e vilas. | dados urbanos, governança e vida material | Markdown estruturado e/ou YAML, a definir | regiões, reino, recursos e rotas | Fase 3 | não iniciado |
| `content/worlds/eldrath/locations/` | locais | Registrar locais especiais, naturais, urbanos e ocultos. | dados espaciais, acesso, perigos e lore | Markdown estruturado e/ou YAML, a definir | regiões e assentamentos | Fase 3 | não iniciado |
| `content/worlds/eldrath/routes/` | rotas | Conectar lugares no grafo sistêmico do mundo. | origem, destino, distância, custo e riscos | Markdown estruturado e/ou YAML, a definir | regiões, assentamentos e locais | Fase 3 | não iniciado |
| `content/worlds/eldrath/npcs/` | NPCs | Reunir NPCs-semente e suas relações iniciais. | fichas, objetivos, crenças, memórias e lore | Markdown com front matter YAML, a definir | todo o contexto macro, social e mágico | Fase 5 | não iniciado |
| `content/worlds/eldrath/families/` | famílias e casas | Registrar parentesco, casas, heranças e memória coletiva. | dados familiares, dinásticos e lore | Markdown estruturado e/ou YAML, a definir | culturas, reino, assentamentos e facções | Fase 4 | não iniciado |
| `content/worlds/eldrath/factions/` | facções e instituições | Registrar grupos, instituições, poder e objetivos coletivos. | dados institucionais, políticos e lore | Markdown com front matter YAML, a definir | reino, culturas, religiões e economia | Fase 4 | não iniciado |
| `content/worlds/eldrath/religions/` | religiões e cultos | Registrar tradições religiosas, cultos e princípios necessários. | dados religiosos, sociais e lore | Markdown estruturado e/ou YAML, a definir | cosmologia necessária e culturas | Fases 2 e 4 | não iniciado |
| `content/worlds/eldrath/professions/` | profissões | Definir tarefas, competências, status e progressão profissional. | dados mecânicos e contexto social | Markdown estruturado e/ou YAML, a definir | economia, assentamentos e instituições | Fase 3 | não iniciado |
| `content/worlds/eldrath/creatures/` | criaturas | Registrar espécies relevantes e pressões ecológicas. | dados de espécie, habitat, comportamento e lore | Markdown estruturado e/ou YAML, a definir | geografia, clima e magia | Fase 4 | não iniciado |
| `content/worlds/eldrath/resources/` | recursos | Representar recursos materiais e arcanos relevantes. | dados econômicos, origem e uso | Markdown estruturado e/ou YAML, a definir | regiões, clima e economia | Fase 3 | não iniciado |
| `content/worlds/eldrath/items/` | itens | Registrar itens relevantes e sua proveniência. | dados mecânicos e lore de objetos | Markdown estruturado e/ou YAML, a definir | recursos, profissões, economia e magia | Fase 4 | não iniciado |
| `content/worlds/eldrath/laws/` | leis | Representar leis gerais, mágicas e detalhadas. | jurisdição, comportamento, punição e exceções | Markdown estruturado e/ou YAML, a definir | reino, política, culturas e magia | Fases 2 e 4 | não iniciado |
| `content/worlds/eldrath/diseases/` | doenças | Registrar transmissão, sintomas, gravidade e tratamento. | dados de saúde e lore complementar | Markdown estruturado e/ou YAML, a definir | ambiente, assentamentos, recursos e magia | Fase 4 | não iniciado |
| `content/worlds/eldrath/events/` | eventos | Definir eventos históricos e eventos-base do estado inicial. | registros históricos, gatilhos e causalidade | Markdown estruturado e/ou YAML, a definir | entidades envolvidas e cronologia | Fase 5 | não iniciado |
| `content/worlds/eldrath/rumors/` | rumores | Definir rumores iniciais ou gatilhos e suas origens. | afirmações, fontes, alcance e vínculos causais | Markdown estruturado e/ou YAML, a definir | eventos, NPCs, lugares e facções | Fase 5 | não iniciado |
| `content/worlds/eldrath/magic/` | magia | Agrupar os tipos editoriais do sistema mágico. | dados mecânicos e lore mágico | Markdown estruturado e YAML, a definir | fundamentos do mundo e contratos editoriais | Fase 4 | estrutura criada |
| `content/worlds/eldrath/magic/schools/` | escolas mágicas | Registrar escolas, relações, acesso e status social. | dados taxonômicos, institucionais e lore | Markdown estruturado e/ou YAML, a definir | princípios mágicos, instituições e leis | Fase 4 | não iniciado |
| `content/worlds/eldrath/magic/spells/` | magias | Definir feitiços utilizáveis sem interpretação de prosa livre. | requisitos, custos, efeitos, riscos e lore | Markdown com front matter YAML | escolas, efeitos, leis e instituições | Fase 4 | não iniciado |
| `content/worlds/eldrath/magic/rituals/` | rituais | Registrar práticas mágicas prolongadas e suas regras. | requisitos, custos, duração, efeitos e lore | Markdown estruturado e/ou YAML, a definir | escolas, magias, efeitos e instituições | Fase 4 | não iniciado |
| `content/worlds/eldrath/magic/artifacts/` | artefatos | Registrar objetos mágicos únicos ou relevantes. | dados mecânicos, proveniência e lore | Markdown estruturado e/ou YAML, a definir | escolas, efeitos, itens e história | Fase 4 | não iniciado |
| `content/worlds/eldrath/magic/effects/` | efeitos mágicos | Padronizar efeitos mecânicos referenciáveis. | estados, alterações, duração e condições | Markdown estruturado e/ou YAML, a definir | contratos editoriais e regras de magia | Fase 4 | não iniciado |

## Formatos e limites da fase atual

- Markdown será usado para lore, contexto e explicações legíveis por pessoas.
- YAML ou front matter YAML será usado para dados estruturados que precisem ser lidos e validados futuramente.
- O contrato comum, o manifesto, o template genérico, o schema de entidades fundamentais e cinco templates especializados foram criados na Fase 1.
- `world.yaml` e `kingdom.yaml` ainda não foram criados; conteúdo real permanece inexistente.
- A próxima etapa é criar schemas e templates geográficos para região, assentamento, local e rota.
- Os arquivos de conteúdo representarão o estado inicial do mundo. O estado produzido pela simulação será tratado futuramente pela programação e não substituirá silenciosamente o conteúdo autoral.
