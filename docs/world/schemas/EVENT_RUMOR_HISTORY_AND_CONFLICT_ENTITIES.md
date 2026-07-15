# Eventos, rumores, história e conflitos — schemas editoriais

**Versão do contrato especializado:** `1.0.0`

**Contrato comum:** [`CONTENT_SCHEMA.md`](../CONTENT_SCHEMA.md), versão `1.0.0`

**Estado:** contratos de `event`, `rumor`, `conflict`, causalidade, gatilhos, arcos e projeções históricas concluídos; entidades reais não iniciadas.

Este documento especializa o contrato editorial comum para eventos de conteúdo, rumores iniciais e conflitos latentes. Também define os contratos conceituais de eventos de campanha, cadeias causais, gatilhos, arcos, timeline, crônicas, resumos, eras e lendas. Não é schema executável, JSON Schema, DSL, código, save, evento ocorrido, rumor real, conflito real ou lore de Eldrath.

Em caso de conflito, [`Base/GDD.md`](../../../Base/GDD.md), versão `1.3`, permanece a fonte canônica.

## 1. Objetivo

Permitir que autores representem acontecimentos iniciais, possibilidades editoriais, afirmações transmissíveis e tensões latentes sem:

- confundir definição estática com fato ocorrido durante a campanha;
- produzir eventos sem causa;
- converter percepção ou interpretação em verdade;
- apagar genealogia de rumor;
- determinar previamente o desfecho de um conflito;
- inventar história em timeline, crônica, resumo, arco ou lenda;
- depender de IA generativa ou prosa livre para regras.

## 2. Escopo, dependências e limites

Dependências editoriais:

1. [contrato editorial comum](../CONTENT_SCHEMA.md);
2. [entidades fundamentais](FOUNDATIONAL_ENTITIES.md), para calendário, eras, mundo e reino;
3. [geografia](GEOGRAPHY_ENTITIES.md), para locais, assentamentos, regiões e rotas;
4. [economia material](MATERIAL_ECONOMY_ENTITIES.md), para recursos, itens, quantidades e capacidades;
5. [intervenção, percepção e conhecimento](INTERVENTION_PERCEPTION_AND_KNOWLEDGE.md), para causa restrita, evidência e conhecimento limitado;
6. [sociedade, instituições e lei](SOCIETY_INSTITUTIONS_AND_LAW_ENTITIES.md), para facções, famílias, religiões e consequências jurídicas;
7. [sistema mágico](MAGIC_SYSTEM_ENTITIES.md), para efeitos, rituais, sinais e causas mágicas;
8. [criaturas, saúde e doenças](CREATURE_HEALTH_AND_DISEASE_ENTITIES.md), para espécies, populações, saúde e ameaças;
9. [NPCs](NPC_SYSTEM_ENTITIES.md), para agentes, observadores, crenças, memórias e relações.

O contrato posterior de [ameaças monstruosas e incursões](MONSTROUS_THREATS_AND_INCURSIONS.md) aplica estas regras causais a ataques, hordas, defesas e consequências.

Não são criados por este contrato: entidades reais, fatos históricos, ataques, rumores, conflitos, eras, lendas, arcos, saves, linguagem executável, fórmulas, banco, API, testes ou código.

## 3. Prefixos, caminhos e formatos

| Entidade de conteúdo | Prefixo | Diretório | Arquivo |
|---|---|---|---|
| evento histórico inicial, evento-base ou possibilidade editorial | `event.` | `content/worlds/eldrath/events/` | `{slug}.md` |
| rumor inicial ou afirmação transmissível de conteúdo | `rumor.` | `content/worlds/eldrath/rumors/` | `{slug}.md` |
| conflito latente | `conflict.` | `content/worlds/eldrath/conflicts/` | `{slug}.md` |

As três entidades usam Markdown com front matter YAML, um arquivo por entidade, `schema_version: "1.0.0"` e `content_status: draft` ao iniciar a autoria.

Não existem pastas ou templates separados para gatilho, timeline, crônica, resumo histórico, era, arco, lenda, ataque, incursão ou horda. Esses conceitos são subestruturas, projeções, agrupamentos, estado da campanha ou entidades de outros contratos conforme sua propriedade.

## 4. Propriedade canônica

| Informação | Proprietário canônico | Não deve ser duplicada em |
|---|---|---|
| definição estática de evento | `event.*` | evento concreto do save |
| fato concreto ocorrido | evento imutável de campanha | `event.*` reescrito |
| cadeia causal concreta | eventos e estado da campanha | crônica ou prosa narrativa |
| afirmação transmissível inicial | `rumor.*` | crença ou memória individual |
| transmissão, alcance e mutação atuais de rumor | save da campanha | `rumor.*` estático |
| crença ou suspeita individual | NPC e save | rumor como se fosse estado mental universal |
| memória individual | NPC e save | evento verdadeiro ou rumor |
| conflito latente e suas possibilidades | `conflict.*` | resultado predeterminado |
| estado atual e resultado do conflito | save e eventos | arquivo `conflict.*` |
| verdade histórica | eventos | timeline, crônica, resumo, arco ou lenda |
| versão cultural lendária | projeção derivada com genealogia | evento verdadeiro sobrescrito |
| origem real de Intervenção do Arquiteto | metadado restrito | conhecimento, rumor ou memória de NPC |

## 5. Evento de conteúdo e evento de campanha

### 5.1 Evento de conteúdo

`event.*` representa uma definição autoral estática. `content_event_role_key` distingue:

- `historical_seed`: fato anterior ao início da campanha, com data e causalidade editoriais;
- `base_event`: modelo ou possibilidade de acontecimento futuro;
- `configurable_trigger`: possibilidade editorial centrada em gatilhos e resultados permitidos.

Essas chaves são vocabulário estrutural. Um evento histórico inicial precisa estar explicitamente marcado como ocorrido antes da campanha. Um evento-base não pode ser apresentado como fato já ocorrido.

O namespace `event.seed.*` continua permitido para eventos-semente. Outros segmentos estáveis podem ser aprovados sem substituir o prefixo `event.`.

### 5.2 Evento de campanha

Evento de campanha é um fato concreto produzido pela simulação. Ele:

- possui ID técnico próprio, separado de `event.*`;
- é imutável, datado e ordenado;
- integra o log e o replay;
- registra versão do motor e hash de conteúdo aplicáveis;
- aponta para definição `event.*` quando houver uma origem estática;
- preserva cadeia causal para trás e para frente;
- registra efeitos, evidências, observadores e consequências;
- mantém origem administrativa restrita quando aplicável;
- pode existir sem ter sido percebido por ninguém.

O formato técnico definitivo do evento de campanha será criado somente nas fases de programação autorizadas.

### 5.3 Campos de `event.*`

Além dos campos comuns:

| Campo | Regra |
|---|---|
| `content_event_role_key` | papel estático da definição |
| `event_type_key`, `event_subtype_key` | classificações controladas |
| `temporal_scope` | data inicial, data final, precisão e relação com início da campanha |
| `location_scope` | locais, assentamentos, regiões e rotas por ID |
| `actors` | agentes possíveis ou históricos e papéis locais |
| `targets` | alvos possíveis ou históricos por ID e categoria |
| `participants` | participantes adicionais e papéis |
| `observer_scope` | observadores históricos conhecidos ou condições de observação possíveis |
| `causality` | classificação de raiz, causas, precondições, agentes, motivos, capacidades, oportunidades e correlações |
| `evidence_profiles` | sinais e evidências possíveis ou históricas |
| `parent_event_id` | composição ou continuidade com outro `event.*` |
| `related_events` | relações não causais explicitamente classificadas |
| `triggers` | gatilhos incorporados |
| `effect_profiles` | efeitos diretos permitidos ou históricos |
| `consequence_profiles` | eventos posteriores permitidos ou históricos |
| `visibility` | classificação pública, privada, secreta ou restrita |
| `importance` | perfil e fatores de importância, sem valor arbitrário obrigatório |
| `sources` | documentos, entidades, eventos ou fundamentos editoriais |
| `restricted_origin` | origem real protegida quando aplicável; nunca conhecimento automático |
| `integration_links` | relações com rumores, conflitos, criaturas e fontes possíveis de memória, conhecimento e crença |
| `fallback_text_template` | texto parametrizado determinístico |
| `optional_narrative` | apresentação opcional que não cria fatos |
| `campaign_projection` | tipo técnico esperado e requisitos de rastreabilidade futura |
| `deferred_decisions` | decisões específicas adiadas |

### 5.4 Integrações com memória, rumor, conhecimento, crença, conflitos e ameaças

O evento concreto fornece experiência, comunicação, evidência e contexto capazes de originar memória, conhecimento, crença ou rumor, mas não escreve esses estados automaticamente. Cada observador precisa de via perceptiva ou informacional válida. `integration_links` registra somente relações editoriais e fontes possíveis; memórias, conhecimentos, crenças e transmissões efetivas pertencem aos NPCs e ao save.

Rumores apontam ao evento ou à evidência de origem quando aplicável. Conflitos apontam aos eventos históricos e incidentes que os sustentam. Ataques e etapas de incursão são eventos de campanha e podem referenciar `creature.*`, grupo agregado, ameaça e `conflict.*` sem transformar ameaça atual em entidade de conteúdo. Origem administrativa ou verdade restrita permanece fora da visão pública.

## 6. Causalidade

### 6.1 Termos distintos

- **Causa:** acontecimento ou estado que contribuiu para produzir o evento.
- **Precondição:** estado necessário, mas não necessariamente causador.
- **Gatilho:** condição que iniciou avaliação ou processo.
- **Agente:** entidade que realizou ou dirigiu a ação.
- **Motivo:** razão do agente.
- **Capacidade:** meios que tornaram a ação realizável.
- **Oportunidade:** circunstância que permitiu agir naquele contexto.
- **Evento pai:** vínculo de composição ou continuidade, não sinônimo de causa.
- **Consequência:** evento posterior produzido.
- **Correlação:** associação que não afirma causalidade.
- **Evidência:** sinal capaz de sustentar investigação.
- **Interpretação:** explicação subjetiva formada por observador.

### 6.2 Evento-raiz

Todo evento relevante possui causa anterior, condição inicial legítima ou classificação explícita como evento-raiz. Um evento-raiz registra `root_basis_key`, escopo, fundamento editorial e razão de não possuir causa anterior. Marcar um evento como raiz não autoriza aleatoriedade desconectada.

### 6.3 Consequências e inspeção

Uma consequência relevante é outro evento. Alteração silenciosa de estado é proibida. A cadeia concreta da campanha precisa permitir:

- navegar das causas ao evento;
- navegar do evento às consequências;
- distinguir fatores contribuintes de causa necessária;
- localizar decisões, objetivos, rumores, regras e intervenções relacionadas;
- identificar evidências e interpretações sem confundi-las com verdade.

## 7. Gatilhos incorporados

Cada gatilho possui:

- `trigger_key` estável dentro do arquivo;
- `trigger_type_key`;
- `scope_key`;
- condição editorial estruturada;
- limiar e janela temporal, quando aplicáveis;
- precondições;
- entidades observadas;
- repetição e uso único;
- cooldown;
- prioridade;
- atraso;
- chance controlada de `0` a `1` ou `null`;
- `random_stream_key` nomeado;
- causas atribuídas;
- resultados permitidos;
- bloqueios;
- expiração;
- campos de rastreabilidade.

Gatilhos não usam código, expressões arbitrárias, linguagem executável ou prosa como condição mecânica. Uma chance desconhecida usa `null`; zero significa impossibilidade real. A execução futura exige vocabulário aprovado, ordem determinística e log do resultado.

## 8. Eventos atômicos, compostos e arcos

- **Evento atômico:** fato único indivisível para a finalidade do log.
- **Evento composto:** agrupamento de eventos atômicos relacionados; não os substitui.
- **Arco:** agrupamento interpretativo de eventos que forma trajetória consultável.
- **Marco:** evento relevante dentro de um arco.

Um arco conceitual registra chave estável no estado, participantes, eventos, tensão, estado, marcos, conclusões possíveis, conclusão efetiva, abandono, fusão e divisão. Possíveis conclusões pertencem à definição; conclusão efetiva pertence aos eventos e ao save. Arco não cria fatos nem decide vencedor.

## 9. Rumor, fato, crença, memória e lenda

### 9.1 Fronteiras

- **Fato:** verdade conhecida pelo motor.
- **Evento:** registro imutável de um fato ocorrido.
- **Evidência:** sinal observável ou investigável.
- **Percepção:** parte acessível a um observador.
- **Interpretação:** explicação subjetiva.
- **Afirmação:** conteúdo proposicional comunicável.
- **Suspeita:** possibilidade considerada.
- **Crença:** afirmação aceita como verdadeira.
- **Mentira:** afirmação sabidamente falsa para o emissor.
- **Segredo:** fato de acesso restrito.
- **Rumor:** afirmação transmissível com origem e genealogia.
- **Correção:** afirmação concorrente apoiada por fonte ou evidência.
- **Memória:** registro subjetivo de experiência ou comunicação.
- **Lenda:** versão cultural derivada, preservada com suas fontes e crenças coletivas.

Nenhuma dessas estruturas substitui outra.

### 9.2 Campos de `rumor.*`

Além dos campos comuns:

- `claim`, com sujeito, propriedade, valor alegado, certeza expressa e resumo editorial;
- `subject_entity_ids`;
- `version` e `genealogy`;
- `origin`, com evento ou evidência, primeiro emissor, canal, local e momento;
- `restricted_engine_truth`, visível somente a ferramentas autorizadas;
- `initial_reach`;
- credibilidade, carga emocional e novidade iniciais;
- fontes intermediárias editoriais conhecidas;
- grupos e lugares inicialmente alcançados;
- mutações editoriais já existentes;
- validade e estado inicial;
- versões anteriores e derivadas;
- contestações e correções;
- consequências possíveis;
- regras de transmissão e distorção;
- gatilhos incorporados;
- decisões adiadas.

### 9.3 Genealogia e transmissão

A genealogia nunca é apagada. Uma transmissão exige portador, receptor ou canal, oportunidade, local, momento, relação ou acesso e alcance plausível. Um rumor não aparece simultaneamente na mente de todo o reino.

Distorções permitidas por regras podem incluir perda de detalhe, exagero, troca de agente, atribuição de intenção, inclusão de elemento mágico, inversão de causa, fusão com outro rumor e aumento indevido de certeza. Correção compete com versões anteriores e não apaga crenças automaticamente.

Rumores sobre ameaças podem exagerar números, inventar espécie, atribuir comando, confundir migração com invasão, transformar criatura comum em demônio, ocultar causa mágica e provocar pânico, caça, evacuação ou culto. A versão não altera o estado verdadeiro.

## 10. História, timeline, crônicas, resumos, eras e lendas

Eventos são a única fonte factual histórica.

| Projeção | Regra |
|---|---|
| timeline | consulta ordenada de eventos |
| crônica | apresentação derivada que cita os eventos usados |
| resumo histórico | condensação derivada, sem fatos extras |
| arco | agrupamento interpretativo de eventos |
| lenda | versão cultural com origem, versões, crenças e verdade restrita |
| era | divisão histórica confirmável e nomeável pelo Cronista |

Perspectivas permitidas: administrativa, onisciente, pública, institucional, local e individual. A visão pública não revela origem restrita, segredo, verdade desconhecida ou metadado administrativo. Uma lenda pode divergir da verdade, mas preserva origem, versões, grupos que acreditam, símbolos, locais, eventos relacionados, efeitos culturais e verdade histórica restrita.

Não existe pasta `history/` nesta fase. A ausência é intencional.

## 11. `conflict` — conflito latente

### 11.1 Finalidade e tipos

`conflict.*` define uma oposição inicial capaz de produzir eventos. Tipos podem ser pessoais, familiares, sociais, econômicos, políticos, religiosos, mágicos, jurídicos, territoriais, militares, ecológicos, monstruosos, demoníacos ou assimétricos.

O arquivo separa definição estática, `initial_state`, estado atual, eventos produzidos e resultado efetivo. Estado atual e resultado pertencem ao save. Nenhum conflito determina vencedor.

### 11.2 Campos

Além dos campos comuns:

- `conflict_type_key` e `subject`;
- `origin`, com evento, condição inicial e fundamento;
- `sides`, com chaves locais, entidades, populações ou categorias participantes;
- `participant_entity_ids`;
- interesses e objetivos incompatíveis por lado;
- queixas;
- riscos;
- recursos e capacidades disponíveis inicialmente;
- relações relevantes;
- território e escopo espacial;
- visibilidade;
- `initial_state`, com tensão inicial e condições conhecidas;
- limiares;
- gatilhos de escalada e redução;
- incidentes e marcos possíveis;
- resoluções possíveis;
- condições de encerramento;
- consequências possíveis;
- eventos históricos, rumores e segredos relacionados;
- decisões adiadas.

### 11.3 Escalada

A referência conceitual admite tensão, incidente, acusação, mobilização, ultimato, confronto, guerra ou incursão, negociação/caça/contenção, cessar-fogo/retirada/dispersão e tratado/vitória/ocupação/colapso/transformação. Nem todo conflito percorre todas as etapas.

Conflitos monstruosos podem ter lados compostos por população `creature.*`, grupo agregado, horda, NPC único, facção, assentamento, força defensora, culto ou invocador. Não se exige simetria.

## 12. Conteúdo, estado inicial e campanha

### Conteúdo estático

Define evento, rumor e conflito iniciais, capacidades, gatilhos, possibilidades, limites e relações editoriais.

### Estado inicial

Semeia fatos anteriores, alcance inicial de rumores e tensão inicial de conflitos. Todo valor mutável fica identificado como inicial.

### Estado da campanha

Possui eventos concretos, percepções, transmissões, mutações, crenças adquiridas, memórias, arcos, alcance de rumor, tensão, incidentes, mobilizações, resultados, ataques e consequências atuais.

### Derivados

São derivados: timeline, crônicas, resumos, perspectivas, alertas, arcos detectados, importância contextual, visão pública, reputações históricas, lendas e estado agregado de conflitos.

## 13. Intervenções do Arquiteto

Uma intervenção pode iniciar evento permitido, introduzir rumor por origem válida ou alterar condições de conflito e ameaça somente por comando validado. Ela:

- gera evento;
- registra origem administrativa restrita;
- cria evidências quando aplicável;
- resolve percepção individual;
- participa de determinismo e replay;
- não escreve crença, memória ou conhecimento silenciosamente;
- não determina vencedor de conflito;
- não insere rumor em todas as mentes.

## 14. IA generativa, texto fallback e determinismo

Todo evento possui texto fallback por template parametrizado. Texto narrativo opcional pode reescrever apresentação, mas não cria nomes, participantes, causas, datas, efeitos ou consequências. Crônicas e rumores funcionam sem IA.

Chances usam fluxo pseudoaleatório nomeado. Mesma versão, conteúdo, semente, configuração, estado e ordem de comandos produz o mesmo resultado. IA generativa nunca resolve gatilho, transmissão, crença, conflito ou evento.

## 15. Invariantes

1. `event.*` não é ID de evento concreto de campanha.
2. Evento de campanha é imutável e versionado.
3. Evento relevante possui causa, condição inicial legítima ou classificação de raiz.
4. Consequência relevante é outro evento.
5. Causa, precondição, gatilho, agente, motivo, capacidade, oportunidade, evidência e interpretação permanecem distintos.
6. Gatilho não é código nem expressão arbitrária.
7. Arco não substitui eventos.
8. Timeline, crônica e resumo não inventam fatos.
9. Rumor não é crença, memória ou lenda.
10. Genealogia de rumor não é apagada.
11. Rumor exige origem e transmissão plausível.
12. Visão pública não revela dados restritos.
13. Conflito não determina vencedor.
14. Estado atual não reescreve conteúdo.
15. Origem do Arquiteto não vira conhecimento de NPC.
16. Texto opcional não participa da resolução.
17. Nenhuma entidade real é criada por schema ou template.

## 16. Validação manual

Antes de encaminhar conteúdo futuro para revisão:

- conferir caminho, prefixo, slug, `schema_version`, `content_status` e campos comuns;
- validar YAML, tipos, `null`, listas vazias e ausência de string vazia;
- validar IDs por categoria e referências existentes em conteúdo aprovado;
- distinguir evento de conteúdo de evento de campanha;
- conferir causalidade, raiz legítima, evento pai e consequências;
- conferir gatilhos sem linguagem executável;
- confirmar texto fallback e narrativa sem fatos extras;
- validar origem, portador, canal, local, momento e genealogia do rumor;
- confirmar que rumor não surge em todo o reino;
- conferir verdade restrita separada da afirmação pública;
- validar conflito estático separado do estado e resultado;
- confirmar ausência de vencedor predeterminado;
- conferir escalada, redução e encerramento como possibilidades;
- validar visibilidade e ausência de metaconhecimento;
- confirmar que história derivada aponta para eventos;
- remover placeholders antes de `content_status: approved`;
- confirmar ausência de entidade real, save, DSL, código ou schema executável.

## 17. Decisões adiadas

Permanecem para fases posteriores:

- eventos, rumores, conflitos, datas, nomes e lore reais de Eldrath;
- vocabulários finais de tipo, subtipo, canal, estado, visibilidade, tensão, escalada e resolução;
- formato técnico de IDs e registros de eventos de campanha;
- representação persistente de evidências, transmissões, arcos e conflitos atuais;
- fórmulas de importância, transmissão, credibilidade, distorção, tensão e resolução;
- operadores executáveis de gatilhos e condições;
- política detalhada de agregação de eventos irrelevantes;
- interface de timeline, crônica, causalidade, rumor e conflito;
- validação automatizada, banco, API e implementação.
