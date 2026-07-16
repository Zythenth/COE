# Ameaças monstruosas e incursões — contrato editorial e conceitual

**Versão do contrato especializado:** `1.0.0`

**Contratos-base:** [`CONTENT_SCHEMA.md`](../CONTENT_SCHEMA.md), versão `1.0.0`, e [`CREATURE_HEALTH_AND_DISEASE_ENTITIES.md`](CREATURE_HEALTH_AND_DISEASE_ENTITIES.md), versão `1.0.0`

**Estado:** contrato de ameaças, grupos, hordas, ataques, incursões, defesas e consequências concluído; entidades reais não iniciadas.

Este documento define como espécies e tipos de criatura podem originar ameaças vivas ou sobrenaturais e como a futura campanha representará populações, grupos, hordas, ataques e incursões. Não é entidade, template de horda, schema executável, JSON Schema, DSL, código, save, monstro real, demônio real, ataque histórico ou lore de Eldrath.

Em caso de conflito, [`Base/GDD.md`](../../../Base/GDD.md), versão `1.5`, permanece a fonte canônica.

## 1. Objetivo

Assegurar que fauna perigosa, feras, monstros, demônios, aberrações, criaturas corrompidas, mortos-vivos, enxames, invocações, criaturas colossais, criaturas lendárias e entidades únicas possam:

- agir por necessidades, instintos, objetivos, comando ou relações mágicas;
- formar grupos em escalas adequadas;
- selecionar alvos e deslocar-se de modo causal;
- produzir sinais detectáveis e interpretações imperfeitas;
- atacar pessoas, caravanas, rotas, recursos, assentamentos e instituições;
- enfrentar defesa, negociação, contenção, retirada ou dispersão;
- deixar perdas e consequências persistentes;
- participar de determinismo, replay, memória, rumor, conflito e história;
- funcionar sem mapa gráfico e sem IA generativa.

## 2. Dependências e limites

Este contrato depende de:

- [geografia](GEOGRAPHY_ENTITIES.md), para grafo de lugares e rotas;
- [economia material](MATERIAL_ECONOMY_ENTITIES.md), para alimento, recursos, itens, perdas e escassez;
- [intervenção, percepção e conhecimento](INTERVENTION_PERCEPTION_AND_KNOWLEDGE.md), para evidências e metaconhecimento;
- [sociedade, instituições e lei](SOCIETY_INSTITUTIONS_AND_LAW_ENTITIES.md), para cultos, exércitos, autoridades e respostas jurídicas;
- [sistema mágico](MAGIC_SYSTEM_ENTITIES.md), para invocação, corrupção, portais, rituais e efeitos;
- [criaturas, saúde e doenças](CREATURE_HEALTH_AND_DISEASE_ENTITIES.md), para espécie, comportamento, ecologia e saúde;
- [NPCs](NPC_SYSTEM_ENTITIES.md), para indivíduos persistentes, líderes e observadores;
- [eventos, rumores, história e conflitos](EVENT_RUMOR_HISTORY_AND_CONFLICT_ENTITIES.md), para causalidade, gatilhos, arcos e estado histórico.

Não são criadas pastas `demons/`, `monsters/`, `hordes/`, `invasions/`, `incursions/`, `undead/` ou `swarms/`. Não existem templates separados para ataque, horda, incursão, invasão, infestação, portal, ninho ou demônio.

## 3. Entidades e propriedade canônica

| Conceito | Representação | Propriedade |
|---|---|---|
| espécie, tipo ou arquétipo | `creature.*` | conteúdo estático |
| indivíduo comum | ocorrência agregada | save |
| indivíduo persistente | `npc.*` com `creature_id` | conteúdo inicial e save |
| população atual | registro agregado | save |
| pequeno grupo, bando, matilha ou enxame | grupo agregado | save |
| horda ou força de cerco | força agregada | save |
| ameaça | avaliação contextual de risco | save e consultas |
| ataque | ação concreta | evento de campanha |
| incursão | processo causal de eventos | save, eventos e arco derivado |
| infestação | presença nociva persistente | save e eventos |
| invasão | expansão ou entrada estratégica | conflito, save e eventos |
| conflito latente | `conflict.*` | conteúdo estático |
| conflito atual | save e eventos | campanha |
| arco | agrupamento derivado | consulta/save |
| definição geográfica de ninho, portal ou covil persistente | `location.*` | conteúdo estático; atividade, integridade, ocupação e descoberta atuais ficam no save |
| culto ou organização | `faction.*` | conteúdo e save |
| doutrina ou crença demoníaca | `religion.*` | conteúdo |

Nenhuma representação deve possuir dois proprietários concorrentes.

## 4. Taxonomia de ameaças

`creature.classification` pode expressar, por chaves controladas, categorias como:

- fauna perigosa;
- fera selvagem;
- monstro;
- demônio;
- aberração arcana;
- criatura corrompida;
- morto-vivo;
- enxame;
- criatura invocada;
- criatura colossal;
- criatura lendária;
- entidade única.

Essas classificações não definem automaticamente moralidade, hostilidade, irracionalidade, inteligência, legalidade, origem ou comportamento. Tags auxiliam busca; campos estruturados mantêm as propriedades mecânicas.

## 5. Origem

Uma ameaça pode derivar de:

- população natural;
- migração;
- fome ou escassez;
- perda de habitat;
- reprodução ou expansão;
- perturbação de ninho ou território;
- caça ou perseguição;
- corrupção;
- doença;
- invocação;
- portal;
- libertação;
- comando de líder, facção ou culto;
- intervenção do Arquiteto;
- evento-raiz legitimamente documentado.

Origem da espécie pertence a `creature.*`. Formação concreta de ameaça pertence ao save e gera eventos. Origem desconhecida por NPCs não significa ausência de causa no motor.

## 6. Inteligência, comportamento e organização

O contrato de criatura deve declarar separadamente:

- inteligência e capacidade de aprendizagem;
- instinto;
- fome e dieta;
- territorialidade;
- agressividade;
- medo e respostas a ameaça;
- sociabilidade e estruturas de grupo;
- hierarquia e liderança;
- disciplina e estratégia;
- comunicação;
- capacidades mágicas;
- negociação;
- relações possíveis com facções e cultos;
- vulnerabilidades e fraquezas;
- motivações e objetivos possíveis;
- reprodução e proteção de prole ou ninho;
- cerco, ocupação e corrupção;
- condições de retirada.

Nem todo demônio é irracional. Nem todo monstro é hostil. Uma criatura inteligente pode negociar, enganar, exigir tributo, formar alianças, comandar forças, fundar culto, ocupar território, infiltrar instituição ou iniciar guerra quando seus campos e o contexto permitirem.

## 7. Escalas de simulação

### 7.1 Escalas distintas

- **indivíduo comum:** ocorrência sem identidade persistente completa;
- **pequeno grupo:** poucas ocorrências com tarefa compartilhada;
- **bando ou matilha:** grupo social ou funcional;
- **enxame:** conjunto numeroso tratado por quantidade e comportamento agregado;
- **população agregada:** distribuição por contexto geográfico;
- **horda:** força móvel agregada;
- **força de cerco:** força com capacidade e objetivo de cerco;
- **indivíduo persistente:** NPC com identidade e trajetória;
- **criatura única:** indivíduo sem equivalentes funcionais no contexto;
- **criatura lendária:** condição histórica derivada, não simples tag promocional.

### 7.2 Agregação

Populações, grupos, hordas e forças de cerco atuais pertencem ao save. Um registro agregado conceitual considera:

- ID técnico;
- `creature_id` ou composição por espécies;
- quantidade ou faixa conhecida pelo motor;
- local e rota;
- líder ou controlador, quando houver;
- organização, coesão, disciplina e moral;
- capacidades;
- objetivo ou motivação atual;
- recursos e suprimento;
- saúde agregada;
- sinais produzidos;
- estado e eventos relacionados.

Não se materializa um NPC por integrante. Um campeão, líder, negociador, criatura única ou indivíduo historicamente relevante pode ser promovido a NPC persistente com proveniência e evento.

## 8. Formação e persistência de ameaça

Uma ameaça contextual possui:

- origem e eventos causadores;
- entidade, população ou grupo que a sustenta;
- motivação;
- capacidade;
- oportunidade;
- área ou alvos expostos;
- intensidade e escala;
- sinais e evidências;
- conhecimento verdadeiro do motor;
- percepção de facções e NPCs;
- possíveis respostas;
- estado de persistência, redução ou encerramento.

Uma espécie perigosa não é ameaça ativa em todo lugar. Uma ameaça cessa ou se transforma por eventos, não por remoção silenciosa.

## 9. Seleção de alvos

Alvos possíveis incluem viajantes, NPCs, caravanas, plantações, estoques, rotas, locais, vilas, cidades, facções, instituições, recursos, ninhos rivais e outras criaturas.

Seleção considera:

- fome, objetivo, ordem ou território;
- distância e rota acessível;
- sinais percebidos pela ameaça;
- valor do recurso ou do alvo;
- vulnerabilidade e defesa percebidas;
- risco e alternativas;
- inteligência, estratégia e memória possíveis;
- relação com invocador, líder, facção ou culto;
- condições ambientais e mágicas;
- ruído determinístico controlado.

O alvo não é escolhido somente porque a timeline precisa de um evento.

## 10. Movimentação e aproximação

Movimentação usa origem, destino, rota ou sequência de lugares, duração, modo de deslocamento, acessibilidade, clima, terreno, capacidade, carga e riscos. Uma ameaça pode mover-se fora de rota formal somente quando sua locomoção e a geografia permitirem, mantendo origem, destino, tempo e evidências.

O sistema não exige mapa gráfico. Fichas, grafo de rotas, tarefas, listas e eventos são suficientes para representar aproximação, desvio, perseguição, bloqueio e chegada.

## 11. Sinais, detecção e alerta

Sinais podem incluir rastros, sons, odor, restos, desaparecimentos, consumo de recursos, mudanças ecológicas, resíduos mágicos, corrupção, relatos, comportamento animal, dano em rota ou evidência de ninho.

Cada sinal declara modalidade, intensidade, persistência, alcance, condições de detecção e requisitos de identificação. Detectar sinal não concede automaticamente:

- espécie correta;
- quantidade correta;
- direção precisa;
- intenção;
- líder ou invocador;
- origem mágica;
- causa real de intervenção.

Detecção produz percepção, investigação, alerta, memória ou rumor somente por vias válidas.

## 12. Ataque

Todo ataque concreto registra:

- origem e evento causador;
- atacante ou força agregada;
- causa e motivação;
- capacidade usada;
- oportunidade;
- alvo;
- rota ou forma de aproximação;
- sinais e evidências;
- possibilidade e resultado de detecção;
- resposta defensiva;
- resolução;
- perdas;
- retirada, ocupação, destruição ou dispersão;
- efeitos diretos;
- eventos derivados e consequências.

Sem causa, capacidade, oportunidade e consequência, o ataque é inválido.

## 13. Incursão

Uma incursão é processo causal. Pode contemplar:

1. surgimento ou causa;
2. formação da ameaça;
3. escolha ou atração pelo alvo;
4. deslocamento ou aproximação;
5. sinais;
6. detecção;
7. alerta;
8. preparação;
9. defesa ou evacuação;
10. confronto;
11. retirada, ocupação, destruição ou dispersão;
12. consequências;
13. investigação;
14. reconstrução;
15. memória, rumor ou lenda.

Nem toda incursão percorre todas as etapas. Cada etapa concreta é evento ou estado sustentado por eventos. Um arco pode agrupá-las sem substituí-las.

## 14. Infestação e invasão

- **Infestação:** presença nociva persistente em local, rota, recurso, assentamento ou região; pode resultar de reprodução, ninho, portal, corrupção ou migração.
- **Invasão:** entrada, expansão ou ocupação estratégica em escala superior a ataque isolado; pode envolver múltiplas forças, alvos e conflitos.

Ambas exigem origem, persistência, capacidade, detecção, resposta e consequências. Nenhuma é pasta ou entidade estática própria.

## 15. Ninhos, covis e portais

Ninho, covil ou portal persistente e geograficamente consultável usa `location.*`, com acesso, descoberta, sinais, perigos, propriedades mágicas e eventos relacionados. Estado atual — ocupação, população, atividade, integridade, abertura ou corrupção — pertence ao save.

Estruturas temporárias podem existir somente como estado de campanha. Portal não implica automaticamente demônio, invasão ou conhecimento público.

## 16. Invocação, comando e liderança

Invocação concreta exige magia, ritual, artefato, evento ou intervenção autorizada. Ela registra invocador, alvo ou espécie, condições, custo, vínculo, limites, duração, comando, resistência, falha, evidência e consequências.

Comando pode vir de NPC, facção, culto, artefato, magia ou hierarquia própria. Obediência não é automática: espécie, indivíduo ou grupo pode possuir limites, resistência, interpretação, lealdade, medo ou objetivo conflitante.

Liderança agregada pode referenciar NPC persistente ou chave funcional temporária. Morte, fuga ou substituição de líder gera eventos e pode alterar coesão, estratégia ou retirada.

## 17. Negociação

Criaturas com capacidade podem comunicar termos, aceitar ou rejeitar proposta, exigir tributo, trocar informação, formar aliança, trair, recuar ou manter hostilidade. Negociação considera linguagem, interpretação, valores, objetivo, confiança, poder, risco, oferta, autoridade e conhecimento limitado.

Negociação não garante paz. Tributo não remove ameaça sem regra e evento.

## 18. Cerco, ocupação e corrupção

### Cerco

Exige capacidade de cerco, objetivo, força, acesso, suprimento, tempo, defesa alvo e condições ambientais. Pode interromper rotas, produção, água, comércio, comunicação e evacuação.

### Ocupação

Exige presença sustentada, capacidade, objetivo e controle material. Ocupação atual pertence ao save; mudança territorial ou institucional gera eventos.

### Corrupção

Pode afetar ambiente, criatura, recurso, item, magia, saúde ou percepção somente por efeitos e regras estruturadas. Corrupção atual e propagação pertencem ao save. Sinais não revelam automaticamente fonte ou responsável.

## 19. Defesa e resposta

Assentamentos e facções podem usar:

- guardas;
- milícias;
- exércitos;
- fortificações;
- caçadores;
- aventureiros ou especialistas;
- ordens mágicas;
- rituais;
- evacuação;
- bloqueios de rota;
- recompensas;
- alianças;
- negociação;
- tributo.

Cada resposta exige autoridade ou agente, capacidade, recursos, tempo, conhecimento e oportunidade. A existência de defesa não garante vitória.

## 20. Resolução, retirada e dispersão

Resolução considera quantidade agregada, força, liderança, inteligência, estratégia, moral, suprimento, terreno, clima, surpresa, magia, fortificação, informação, defesa, fuga, negociação, objetivo e ruído determinístico.

Resultados possíveis incluem sucesso parcial, fracasso, retirada, perseguição, dispersão, rendição, negociação, ocupação, destruição, contenção ou transformação. Condições de retirada podem vir de medo, perdas, objetivo cumprido, falta de suprimento, ordem, mudança ambiental, ferimento de líder ou resistência inesperada.

Perdas e resultados são eventos. Quantidades nunca ficam negativas.

## 21. Consequências

Ataques e incursões podem produzir:

- morte, ferimento, desaparecimento e trauma;
- perda, consumo ou roubo de recursos;
- destruição e incêndio;
- corrupção e doença;
- interrupção comercial e escassez;
- refugiados e migração;
- mudança política e mobilização militar;
- leis emergenciais;
- caça organizada e recompensas;
- novos cultos e conflitos;
- rumores, memórias, monumentos e lendas.

Cada consequência relevante aponta para evento anterior. Reconstrução, luto, investigação, retorno de rota, dispersão de refugiados e mudança institucional também geram eventos quando relevantes.

## 22. Rumores sobre ameaças

Rumores podem exagerar número, inventar espécie, atribuir líder, confundir migração com invasão, transformar criatura comum em demônio, ocultar causa mágica e gerar pânico, caça, evacuação ou culto.

Verdade do motor, evidência, percepção, interpretação, rumor e crença permanecem separados. Correção não apaga versões nem crenças imediatamente.

## 23. Integração com NPCs

NPC persistente pode ser líder, campeão, invocador, negociador, caçador, defensor, vítima, testemunha ou investigador. NPCs decidem com o que sabem e acreditam. Um indivíduo comum só é promovido quando adquire relevância persistente.

Nenhum NPC recebe número real da horda, espécie correta, causa mágica, objetivo ou origem do Arquiteto sem via válida.

## 24. Integração com facções, religiões e leis

- exército, culto, corte, organização demoníaca e força institucional usam `faction.*`;
- doutrina, crença e tradição usam `religion.*`;
- caça, captura, criação, invocação, comércio, extermínio, tributo, evacuação e poderes emergenciais dependem de `law.*` aplicável;
- decisões concretas são tomadas por membros autorizados e geram eventos.

Uma espécie não vira facção. Uma facção não substitui as espécies ou indivíduos que a compõem.

## 25. Integração com assentamentos, rotas e economia

Ataques podem afetar população, habitação, segurança, saúde, saneamento, produção, consumo, estoques, preços, comércio e problemas locais. Rotas podem ser bloqueadas, danificadas, evitadas ou tornadas inseguras.

Definições geográficas não armazenam ataque atual. Estado econômico atual e danos pertencem ao save. Escassez, preço, migração e resposta comercial são consequências, não valores arbitrariamente ajustados.

## 26. Integração com saúde e doenças

Ferimentos, exposição, doença, intoxicação, corrupção, dor, fadiga e morte usam os contratos de saúde. Uma criatura pode ser vetor, reservatório ou hospedeiro somente quando `disease.*` declarar a relação específica.

Ataque não mata ou adoece silenciosamente. O evento produz condição, evidência, percepção e consequência conforme as regras.

## 27. Intervenções do Arquiteto

Quando o modo permitir, o Arquiteto pode:

- despertar, introduzir ou deslocar criatura;
- fortalecer ou enfraquecer ameaça;
- formar ou mover horda;
- abrir portal ou criar ninho;
- libertar entidade aprisionada;
- atrair ameaça;
- iniciar incursão;
- fornecer sinais ou avisos;
- alterar condições ambientais relacionadas.

Cada intervenção:

- gera comando e evento;
- valida referências, alvo, local, capacidade e ponto seguro;
- registra causalidade e origem administrativa restrita;
- usa fluxo pseudoaleatório nomeado quando necessário;
- aparece no histórico administrativo;
- participa do replay;
- produz evidências compatíveis;
- resolve percepções individuais;
- não concede metaconhecimento.

NPCs podem interpretar a ameaça como acidente, migração, profecia, punição divina, conspiração, magia, invocação, corrupção ou evento natural.

## 28. Determinismo e IA generativa

Formação, seleção de alvo, movimento, detecção, ataque, defesa, retirada, perdas, corrupção e consequências dependem de dados validados, versão, semente, configuração, estado, ordem e fluxos nomeados.

IA generativa pode apresentar texto opcional, mas não escolhe alvo, forma horda, resolve combate, determina perda, inventa causa, altera ameaça ou decide consequência.

## 29. Invariantes

1. Toda espécie ou tipo usa `creature.*`.
2. Indivíduo persistente usa `npc.*` e referencia `creature.*`.
3. Horda, população, grupo e força de cerco atuais pertencem ao save.
4. Grandes grupos não exigem NPC por integrante.
5. Classificação não determina moralidade ou hostilidade.
6. Nem todo monstro ataca e nem todo demônio é irracional.
7. Ataque possui causa, motivação, capacidade, oportunidade, alvo e consequência.
8. Seleção de alvo não existe apenas para preencher timeline.
9. Sinal não concede identificação automática.
10. Defesa não garante vitória.
11. Perdas e resultados geram eventos.
12. Ninho, portal e covil persistentes usam `location.*`.
13. Estado atual não reescreve conteúdo estático.
14. Rumor não altera verdade da ameaça.
15. Origem do Arquiteto permanece restrita.
16. Replay reproduz a incursão.
17. Nenhuma funcionalidade depende de mapa gráfico ou IA.

## 30. Validação manual

Antes de aprovar conteúdo ou contrato relacionado:

- validar `creature.*` como espécie ou tipo, não indivíduo;
- conferir classificação separada de comportamento;
- validar inteligência, comunicação, negociação, organização e retirada;
- confirmar capacidade de grupo, horda, cerco e corrupção sem estado atual no arquivo;
- conferir líder persistente em `npc.*` quando necessário;
- validar ninho, portal ou covil persistente em `location.*`;
- confirmar agregação sem NPC por integrante;
- conferir origem, causa, motivação, capacidade, oportunidade e alvo;
- validar aproximação por lugar ou rota e sinais detectáveis;
- conferir defesa, resolução, perdas e consequências;
- validar eventos, rumores, memórias e conflitos por seus contratos;
- confirmar ausência de conhecimento automático;
- conferir determinismo, fluxo nomeado e replay;
- confirmar funcionamento sem mapa gráfico;
- confirmar ausência de entidade real, ataque histórico, save, template extra, DSL, código ou schema executável.

## 31. Decisões adiadas

Permanecem para fases posteriores:

- espécies, demônios, monstros, indivíduos, ataques, conflitos e lore reais;
- quantidades de criaturas e ameaças, que continuam `a definir`;
- vocabulários finais de classificação, organização, inteligência, motivação, alvo, ameaça, sinal, defesa e resultado;
- estruturas persistentes técnicas de população, grupo, horda, força de cerco e incursão;
- fórmulas de coesão, movimento, detecção, escolha de alvo, cerco, perdas, retirada e dispersão;
- regras de promoção de integrante agregado a NPC persistente;
- interface de ameaça, alerta, defesa, investigação e reconstrução;
- validação automatizada, banco, API e implementação.
