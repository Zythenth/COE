# Criaturas, saúde e doenças — schemas editoriais

**Versão do contrato especializado:** `1.0.0`

**Contrato comum:** [`CONTENT_SCHEMA.md`](../CONTENT_SCHEMA.md), versão `1.0.0`

**Estado:** contratos de `creature`, `disease` e das estruturas conceituais de saúde concluídos; entidades reais não iniciadas.

Este documento especializa o contrato editorial comum para espécies e tipos de criaturas, definições de doenças e estruturas compartilhadas de saúde. Ele define representação autoral, propriedade canônica, referências, separação entre conteúdo e campanha e validação manual. Não é schema executável, JSON Schema, DSL, código, conteúdo real, diagnóstico médico nem lore de Eldrath.

Em caso de conflito, [`Base/GDD.md`](../../../Base/GDD.md), versão `1.2`, permanece a fonte canônica. O núcleo futuro deve permanecer completo, determinístico e utilizável sem IA generativa.

## 1. Objetivo

Definir como representar:

- espécies, tipos e arquétipos de criatura;
- anatomia abstrata, comportamento e ecologia simplificada;
- definições estáticas de doença;
- estado geral de saúde e registros de condição;
- instâncias de doença, infecções, ferimentos, sintomas, dor e fadiga;
- deficiências, intoxicações e envenenamentos;
- imunidade, resistência, diagnóstico, prognóstico e tratamento;
- saúde verdadeira, saúde percebida, evidência e conhecimento limitado;
- integrações com geografia, economia, sociedade, magia, leis, eventos, intervenções e estado da campanha.

O contrato permite autoria verificável sem criar criaturas, doenças, condições, NPCs, eventos ou regras executáveis.

## 2. Escopo, limites e dependências

Dependências editoriais:

1. [contrato editorial comum](../CONTENT_SCHEMA.md), para formato, ausência, IDs, referências e revisão;
2. [entidades fundamentais](FOUNDATIONAL_ENTITIES.md), para mundo, tempo e unidades;
3. [entidades geográficas](GEOGRAPHY_ENTITIES.md), para regiões, assentamentos, locais, clima e habitat;
4. [economia material](MATERIAL_ECONOMY_ENTITIES.md), para `quantity`, recursos, itens e profissões;
5. [intervenção, percepção e conhecimento](INTERVENTION_PERCEPTION_AND_KNOWLEDGE.md), para causalidade, evidência, conhecimento limitado e replay;
6. [sociedade, instituições e lei](SOCIETY_INSTITUTIONS_AND_LAW_ENTITIES.md), para cultura, religião, facções, jurisdição e legalidade;
7. [sistema mágico](MAGIC_SYSTEM_ENTITIES.md), para escolas, magias, rituais, artefatos, efeitos e corrupção.

Não são criados nesta tarefa: entidades reais, pasta `conditions/`, template de condição, instâncias de doença, sintomas individuais, ferimentos individuais, venenos, infecções, saves, fórmulas, assets, banco, API, código ou validação automatizada.

## 3. Termos e separações obrigatórias

- **Criatura:** definição `creature.*` de espécie, tipo ou arquétipo; não é automaticamente um indivíduo.
- **Indivíduo agregado:** ocorrência comum acompanhada por população ou estado da campanha, sem identidade persistente completa.
- **Indivíduo persistente:** ocorrência com nome, memória, relações, objetivos, conhecimento, inventário, trajetória ou relevância histórica; usa futuramente `npc.*` e referencia sua espécie ou tipo.
- **Doença:** definição estática `disease.*`, transmissível ou progressiva segundo regras próprias.
- **Instância de doença:** ocorrência concreta em um hospedeiro; pertence ao save.
- **Infecção:** instância de doença infecciosa ou parasitária; não é entidade de conteúdo independente.
- **Sintoma:** manifestação observável ou relatada; não revela automaticamente sua causa.
- **Ferimento:** dano produzido por evento, acidente, violência ou esforço; não é automaticamente doença.
- **Deficiência:** característica física, sensorial, cognitiva ou funcional persistente; não é automaticamente doença, corrupção ou falha moral.
- **Envenenamento ou intoxicação:** condição resultante de exposição a substância; não é doença contagiosa por padrão.
- **Corrupção mágica:** estado acumulável definido pelo contrato mágico; não é doença automaticamente.
- **Efeito mágico:** definição `magic_effect.*` e aplicação no save; pode produzir ou modificar saúde, mas não substitui este contrato.
- **Condição de saúde:** registro compartilhado no save; não é entidade de conteúdo nem condição lógica de regra.
- **Condição de regra:** precondição ou condição lógica usada por ações e contratos; não é sinônimo de condição de saúde.
- **Diagnóstico:** hipótese registrada por observador com confiança e evidências; não altera o estado verdadeiro.
- **Prognóstico:** expectativa sobre evolução ou desfecho; sua versão verdadeira pode divergir da conhecida.

## 4. Prefixos, caminhos e formatos

| Entidade | Prefixo | Diretório futuro | Arquivo |
|---|---|---|---|
| espécie, tipo ou arquétipo de criatura | `creature.` | `content/worlds/eldrath/creatures/` | `{slug}.md` |
| definição de doença | `disease.` | `content/worlds/eldrath/diseases/` | `{slug}.md` |

Ambas usam Markdown com front matter YAML, um arquivo por entidade, `schema_version: "1.0.0"` e `content_status: draft` ao iniciar a autoria.

Não existem nesta fase os prefixos `condition.`, `injury.`, `symptom.`, `poison.`, `infection.` ou `health.`. Também não existe pasta `conditions/`.

## 5. Regras compartilhadas

As duas entidades usam os campos comuns `schema_version`, `id`, `name`, `content_status`, `tags`, `aliases`, `summary`, `references`, `art` e `notes`. IDs completos referenciam entidades; chaves locais estáveis usam ASCII, minúsculas e `snake_case`.

Campo omitido significa opcional ou não aplicável; `null` significa aplicável, porém desconhecido; `[]` afirma ausência conhecida. String vazia é proibida. Placeholders só existem em `_templates/` e não podem permanecer em conteúdo `approved`.

Quantidades físicas usam sempre:

```yaml
quantity:
  value: null
  unit_key: null
```

Probabilidades usam exclusivamente a escala `0`–`1` já adotada pelo contrato mágico. Confiança de diagnóstico, intensidade, gravidade, dor e fadiga usam a escala comum `0`–`100`, na qual `0` significa ausência real e `100` o máximo representável. Valor desconhecido é `null`, nunca zero. Bandas textuais, quando necessárias à apresentação, são derivadas e não substituem o número.

Datas e momentos do mundo continuam sujeitos ao calendário futuro. Durações quantitativas usam `value` e `unit_key`; recorrência usa `period_key` somente quando for recorrência, não duração.

## 6. Propriedade canônica

| Informação | Proprietário canônico | Não deve ser duplicada em |
|---|---|---|
| identidade, anatomia abstrata, capacidades e compatibilidade ecológica da espécie | `creature.*` | NPC, região ou local |
| população e distribuição iniciais agregadas | `creature.initial_state` | listas inversas em regiões e locais |
| população, distribuição, migração e pressão de caça atuais | save da campanha | `creature.*` |
| indivíduo persistente | futuro `npc.*` | entidade `creature.*` concorrente |
| definição, transmissão, estágios e tratamentos possíveis da doença | `disease.*` | NPC, criatura ou tratamento atual |
| relações específicas de hospedeiro, vetor e reservatório | `disease.*` | listas inversas manuais em `creature.*` |
| instância, estágio, sintomas e transmissibilidade atuais | save da campanha | `disease.*` |
| ferimento, dor, fadiga, intoxicação, diagnóstico e tratamento atuais | save da campanha | conteúdo estático |
| efeitos mágicos possíveis | `magic_effect.*`, `spell.*` ou `ritual.*` | prosa de saúde |
| efeito mágico aplicado | save da campanha | doença ou criatura estática |
| legalidade efetiva de caça, tratamento, isolamento ou comércio | leis aplicáveis e save | campo global em criatura ou doença |
| obtenção potencial de recursos ou itens de criatura | `creature.*` | lista inversa geral em recurso ou item |
| estoque, acesso e aplicação concreta de tratamento | save da campanha | opção estática de tratamento |
| conhecimento, crença, suspeita e rumor sobre saúde | observadores e save | estado verdadeiro da doença |

## 7. `creature` — espécie, tipo ou arquétipo

### 7.1 Finalidade e fronteira

`creature.*` representa uma espécie, tipo ou arquétipo de criatura. A definição descreve propriedades compartilhadas e variação possível; não cria automaticamente um indivíduo, um NPC ou milhares de ocorrências persistentes.

Uma criatura inteligente não recebe automaticamente moralidade, hostilidade, fala, comportamento humano, direito político ou filiação. Inteligência, sensibilidade, comunicação, sociabilidade, agência política e relações institucionais são declaradas separadamente.

### 7.2 Identidade, classificação e origem

Campos especializados:

- `classification`: tipo, grupo taxonômico editorial, origem e chaves classificatórias;
- `origin`: descrição editorial, região, local, evento, fenômeno ou relação mágica quando conhecidos;
- `alternative_form_ids`: outras definições `creature.*` somente quando forem tipos distintos e não estados atuais;
- `deferred_decisions`: decisões editoriais específicas adiadas.

Classificação organiza a autoria e não determina comportamento, moralidade ou legalidade.

### 7.3 Anatomia abstrata

`anatomy` descreve somente o necessário para regras e autoria:

- `body_plan_key`;
- `body_regions`, cada uma com `body_region_key`, nome editorial, funções, vulnerabilidades e imunidades estruturais;
- `relevant_system_keys`;
- `sensory_capabilities`;
- `locomotion_modes`;
- `respiration_modes`;
- `anatomical_vulnerability_keys`;
- `structural_immunity_keys`.

`body_region_key` é estável no arquivo e pode ser referenciada por ferimentos no save. Anatomia humana nunca é padrão obrigatório. Não se modelam órgãos ou processos sem relevância sistêmica.

### 7.4 Tamanho, ciclo de vida e reprodução

`size_profile` usa chaves classificatórias e quantidades com unidades quando mensurável. `life_cycle` registra estágios por `life_stage_key`, ordem, desenvolvimento e duração possível. Longevidade usa faixa quantitativa temporal.

`reproduction_profile` permanece abstrato e configurável: modo, requisitos gerais, sazonalidade, cuidado e desenvolvimento. Não inclui conteúdo explícito. Fertilidade de indivíduos e nascimentos atuais pertencem ao save.

### 7.5 Cognição, sensibilidade, comunicação e sociabilidade

Estruturas independentes registram:

- `cognition_profile`: inteligência, aprendizagem, planejamento e memória possíveis;
- `sentience_profile`: sensibilidade, consciência e experiência subjetiva possíveis;
- `communication_profile`: modalidades, complexidade e capacidade linguística declarada;
- `social_profile`: sociabilidade, formas de grupo, cooperação e territorialidade;
- `political_agency_profile`: capacidades políticas possíveis, sem conceder direito ou pertencimento automático.

Uma capacidade possível não afirma que todo indivíduo a exerce da mesma forma.

### 7.6 Comportamento e atividade

`behavior_profile` pode registrar:

- atividade diária e sazonal;
- respostas a ameaça;
- caça, fuga, defesa, cuidado, curiosidade e cooperação;
- variação por estágio de vida;
- gatilhos ambientais;
- comportamento aprendido e treinável;
- limitações e exceções.

Comportamentos são tendências e capacidades, não ações atuais nem personalidade de cada indivíduo.

### 7.7 Dieta e relações ecológicas

`diet_profile` declara categorias alimentares, requisitos, fontes e restrições. Relações entre criaturas ficam em `ecological_relations`, com direção única, `relation_key`, `relation_type_key`, `target_creature_id`, condições, intensidade ou relevância e notas.

Predação é registrada no consumidor ou predador como relação dirigida ao alvo. A lista de predadores de uma espécie é derivada consultando relações que a apontam; não se mantêm listas inversas concorrentes. Relações com recursos alimentares usam `resource.*` quando a definição existir.

### 7.8 Habitat, clima e distribuição

`habitat_compatibility` descreve compatibilidade por:

- `region_ids` e `location_ids` quando entidades específicas existirem;
- `biome_keys`, `climate_keys` e altitude por quantidade;
- disponibilidade de água, abrigo e alimento;
- presença ou ausência de fenômenos mágicos;
- condições de assentamento ou expansão urbana;
- requisitos e fatores limitantes.

Compatibilidade não afirma presença atual. Regiões e locais não mantêm lista inversa manual de criaturas.

`migration_profile` e `territoriality_profile` descrevem capacidade, gatilhos, padrões e limites possíveis. Migração e território atuais pertencem ao save.

### 7.9 População inicial agregada

`initial_state.population_distribution` pode semear distribuição agregada. Cada entrada aponta para exatamente um `region_id`, `settlement_id` ou `location_id` e registra `quantity`, `unit_key`, capacidade ambiental inicial opcional, tendência inicial, data e fundamento.

Depois da inicialização, o save possui quantidade atual, capacidade ambiental, tendência, nascimentos e mortes agregados, migração, caça, predação, doença, expansão, extinção local e eventos ambientais. População nunca fica negativa.

Indivíduos comuns permanecem agregados até adquirirem relevância. Um indivíduo persistente usa `npc.*` e referencia `creature.*`; não há duas identidades concorrentes.

### 7.10 Ecologia simplificada

`ecological_pressures` acompanha apenas pressões relevantes:

- alimento;
- água;
- clima;
- habitat;
- caça;
- expansão urbana;
- magia;
- predadores;
- presas;
- doenças;
- migração.

Cada pressão define chave, fonte, condições, direção do efeito e relevância editorial. Não é cadeia alimentar completa, fórmula nem estado atual.

### 7.11 Relação com magia

`magic_relation` pode registrar afinidades, resistências, vulnerabilidades, dependências, manifestações, escolas relacionadas, efeitos possíveis e evidências. Afinidade não concede automaticamente magia conhecida, domínio, moralidade ou status legal.

Corrupção atual e efeitos aplicados pertencem ao save. Relações mecânicas usam `magic_school.*` e `magic_effect.*`; prosa não substitui aplicações estruturadas.

### 7.12 Saúde estrutural da espécie

`species_health_profile` pode registrar:

- resistência basal e imunidade estrutural da espécie;
- vulnerabilidades anatômicas ou fisiológicas;
- fatores gerais de suscetibilidade;
- necessidades de cuidado;
- tolerâncias ambientais;
- interação geral com dor, fadiga, toxinas e magia.

Relações específicas com uma doença — hospedeiro possível, vetor, reservatório, suscetibilidade ou imunidade específica — pertencem a `disease.*` e são derivadas na visão da criatura. Imunidade individual ou adquirida nunca fica neste arquivo.

### 7.13 Perigo, defesa, domesticação e treinamento

`danger_profile` descreve riscos possíveis, gatilhos e alvos, sem reputação universal. `defense_profile` registra evasão, proteção, resistência, ataque ou outra capacidade defensiva.

`domestication_profile` e `training_profile` declaram possibilidade, requisitos, limites, riscos, bem-estar, competências e profissões relacionadas. Possibilidade de domesticação não concede propriedade, obediência ou legalidade.

### 7.14 Recursos e itens potencialmente obtidos

`yield_profiles` pode registrar obtenção por coleta não letal, queda natural, criação, domesticação, caça, morte, processamento ou evento especial. Cada entrada possui:

- `yield_key`;
- exatamente um `resource_id` ou `item_id`;
- método e condição;
- quantidade com `value` e `unit_key`;
- ferramentas e profissões exigidas;
- riscos e consequências ecológicas;
- categorias regulatórias e leis potencialmente relacionadas.

A definição declara possibilidade, não concessão automática. A obtenção concreta exige evento, condições, competência, ferramenta, quantidade disponível, legalidade e consequência, todos no estado da campanha.

### 7.15 Profissões, cultura, sinais e evidências

`profession_interactions` registra capacidades ou riscos direcionados a `profession.*`, sem listar trabalhadores atuais.

`cultural_perceptions` guarda perspectivas iniciais por cultura, religião, facção, região ou profissão. Cada entrada usa exatamente um observador coletivo por ID, fundamento, percepção, confiança editorial e possíveis fontes. Não existe reputação, medo ou moralidade universal; percepções atuais podem mudar no save por experiência e rumor.

`presence_signals` e `evidence_profiles` registram rastros, sons, marcas, restos, padrões e requisitos de identificação. Evidência de presença não concede identificação automática, causa, hostilidade ou número atual.

## 8. `disease` — definição estática

### 8.1 Finalidade e natureza

`disease.*` define uma doença transmissível ou progressiva com regras estáticas. `nature_key` pode usar as categorias estruturais `infectious`, `parasitic`, `environmental`, `hereditary`, `degenerative`, `magical`, `epidemiological_curse` ou `unknown`. Essas chaves classificam o contrato; não são doenças reais de Eldrath.

Uma maldição individual sem propagação ou progressão epidemiológica permanece efeito mágico ou condição de saúde, não `disease.*`.

### 8.2 Identidade, origem e classificação

Campos especializados abrangem:

- `classification` e `nature_key`;
- `origin`, com descrição editorial, fonte, região, local, evento, criatura, recurso, item ou fenômeno quando conhecidos;
- `host_profiles`;
- `vector_profiles` e `reservoir_profiles`;
- transmissão, exposição, incubação, estágios e progressão;
- sintomas, gravidade, recaída, recorrência e sequelas;
- imunidade, resistência e vulnerabilidades;
- fatores ambientais e sociais;
- diagnóstico, prevenção, isolamento e tratamento;
- mortalidade, resultados possíveis, lore, assets e decisões adiadas.

Origem desconhecida é `null` no dado verdadeiro, não lore inventada.

### 8.3 Hospedeiros, vetores e reservatórios

`host_profiles` registra categorias de hospedeiro, IDs `creature.*` específicos quando aplicável, estágios de vida, condições, suscetibilidade, resistência e possíveis resultados. Um futuro `npc.*` pode ser hospedeiro conforme sua espécie ou condições, sem precisar ser listado individualmente.

`vector_profiles` e `reservoir_profiles` são as direções canônicas das relações epidemiológicas específicas. Elas apontam para `creature.*`, recursos, itens, locais ou categorias ambientais aplicáveis e registram papel, condições, estágios, capacidade e evidências. A criatura não mantém lista inversa concorrente.

Vetor transmite; reservatório mantém ou abriga o agente ou processo. Uma mesma entidade pode cumprir ambos os papéis somente quando duas funções forem explicitamente justificadas.

### 8.4 Exposição e transmissão

`transmission_modes` pode classificar:

- contato direto;
- contato indireto;
- ar;
- água;
- alimento;
- sangue;
- vetor;
- ambiente;
- magia;
- herança;
- outra via estruturada.

Cada modo possui `transmission_key`, fonte e alvo possíveis, `exposure_profile_keys`, estágios transmissores, condições ambientais, proteções, resistência, imunidade, `base_probability` de `0`–`1`, modificadores estruturados e `random_stream_key` nomeado.

Uma resolução futura considera fonte, alvo, intensidade ou dose, proximidade, duração, proteção, resistência, imunidade, ambiente, estágio e semente. Este documento não define fórmula. Toda transmissão probabilística precisa ser reproduzível por versão, estado, semente, ordem e fluxo nomeado.

`exposure_profiles` registra via, fonte, dose ou intensidade quando aplicável, duração, proximidade, proteção, condições e evidências. Itens e recursos podem declarar perigos genéricos em seus próprios contratos; a relação específica capaz de causar esta doença pertence aqui.

### 8.5 Incubação, janela de transmissão e duração

`incubation` e `typical_duration` usam faixas quantitativas temporais. `transmission_windows` associa estágios, início, fim e condições. Valor desconhecido é `null`.

Incubação não implica ausência de transmissão. Janela de transmissão e sintomas observáveis são dimensões separadas.

### 8.6 Estágios e progressão

Cada item de `stages` possui:

- `stage_key` estável;
- `order` inteiro positivo e único;
- nome editorial;
- duração possível;
- transmissibilidade;
- `symptom_keys`;
- gravidade de `0`–`100`;
- aplicações de `magic_effect.*` quando houver efeito mecânico;
- sinais, riscos e evidências;
- transições possíveis;
- condições editoriais de recuperação, agravamento e morte.

Transições usam chaves e condições declarativas; não formam máquina de estados executável. A instância atual guarda o estágio resolvido no save.

`progression_profiles` registra direção, fatores, probabilidades, intervalos e fluxo nomeado. Recaída, recorrência e sequelas possuem estruturas próprias e não são deduzidas apenas da prosa.

### 8.7 Sintomas

`symptom_definitions` define sintomas locais reutilizáveis dentro da doença. Cada item possui:

- `symptom_key`;
- nome editorial;
- intensidade possível de `0`–`100`;
- observabilidade e subjetividade;
- duração possível;
- efeitos funcionais por aplicações ou modificadores estruturados;
- sinais e evidências;
- possíveis causas ou estágios;
- limitações e notas.

O mesmo conceito de sintoma pode aparecer em doenças diferentes, mas não existe arquivo ou ID global `symptom.*`. Um sintoma ativo no save registra sua chave, fonte e intensidade. Sintoma nunca revela automaticamente a doença.

### 8.8 Gravidade, sequelas e resultados

`severity_profile` define faixa e fatores estruturados. `sequela_profiles` registra condições persistentes possíveis, limitações, evidências e efeitos, sem afirmar ocorrência atual.

`outcome_profiles` pode representar recuperação, estabilização, cronicidade, recaída, recorrência, sequela, morte ou outro resultado estruturado. O resultado concreto pertence ao save e gera eventos.

Impacto em fertilidade, quando aplicável, é abstrato, configurável e representado como efeito ou modificador estruturado. Conteúdo explícito é proibido.

### 8.9 Imunidade, resistência e vulnerabilidade

O contrato distingue:

- **imunidade da espécie:** relação estrutural específica declarada em `disease.host_profiles` ou imunidade geral estrutural da criatura;
- **imunidade individual:** estado do save;
- **imunidade adquirida:** estado resultante de exposição, recuperação, tratamento ou magia;
- **resistência:** redução de probabilidade, intensidade ou progressão, sem garantia de imunidade.

`immunity_profiles` pode declarar origem possível, escopo, duração, perda, transferência permitida e efeitos. `resistance_profiles` e `vulnerability_profiles` registram fontes, condições, estágios e resultados possíveis. Nenhum arquivo de doença contém a imunidade atual de um NPC.

### 8.10 Fatores ambientais e sociais

`environmental_factors` pode referenciar clima, bioma, água, abrigo, fenômeno mágico, região, assentamento ou local. `social_factors` pode referenciar densidade, saneamento, cuidado, trabalho, deslocamento, isolamento, prática cultural, instituição ou desigualdade de acesso.

Esses fatores alteram exposição, transmissão, progressão ou acesso; não armazenam estado atual de um lugar. Saúde e saneamento iniciais agregados permanecem no assentamento; valores atuais pertencem ao save.

### 8.11 Diagnóstico e diferenciais

`diagnostic_profiles` descreve possibilidades de investigação, não diagnósticos atuais. Cada perfil pode exigir:

- profissão e competências;
- observação, exame, teste, magia, documento ou investigação;
- sinais, sintomas e evidências;
- recursos, itens, magias, rituais, artefatos e locais;
- tempo, risco, limitações e margem de erro;
- resultados possíveis e diagnósticos diferenciais por `disease.*` ou categorias de condição.

Um diagnóstico concreto pertence ao save e registra observador, alvo, hipótese, confiança, evidências, testes, competência, data, alternativas, resultado e visibilidade. Diagnóstico incorreto pode produzir tratamento inadequado, rumor, medo, estigma, atraso ou investigação; ele nunca altera o estado verdadeiro.

### 8.12 Prognóstico

`prognosis_profiles` descreve resultados possíveis por estágio, gravidade, saúde, tratamento, resistência e condições. O save mantém separadamente:

- prognóstico verdadeiro;
- prognósticos conhecidos por observador;
- confiança, fonte, data, evidências e alternativas de cada versão conhecida.

Conhecer o diagnóstico não concede automaticamente prognóstico correto.

### 8.13 Prevenção, isolamento e tratamento

`prevention_options` e `isolation_options` registram medidas possíveis, requisitos, alcance, duração, riscos, evidências, efeitos e limites. Isolamento efetivo depende de lei, local, capacidade, acesso e aplicação no save.

Cada `treatment_options` pode referenciar:

- `profession.*`;
- `item.*`;
- `resource.*`;
- `spell.*`;
- `ritual.*`;
- `artifact.*`;
- `location.*`;
- `faction.*`;
- repouso, isolamento ou procedimento por chave estruturada.

Uma opção declara estágio aplicável, requisitos, duração, competência, risco, contraindicações, efeitos esperados, efeitos colaterais, probabilidade `0`–`1`, fluxo nomeado, custos, materiais e limitações. Materiais distinguem `resource_id` de `item_id`, usam `quantity` e declaram consumo. Cada entrada de custo usa exatamente uma representação principal entre `money`, quantidade de `resource.*` ou quantidade de `item.*`; várias entradas podem compor um tratamento. Existência não significa disponibilidade nem acesso.

Acesso concreto depende de distância, rota, custo, conhecimento, reputação, religião, lei, facção, materiais, profissionais, capacidade do local e urgência. Aplicação concreta pertence ao save e gera evento.

### 8.14 Cura mágica

Cura mágica é uma opção de tratamento estruturada. Pode tratar sintomas, reduzir gravidade, remover doença, impedir transmissão, conceder resistência, causar efeitos colaterais, produzir corrupção ou falhar.

Toda consequência mecânica referencia `magic_effect.*` ou outro contrato estruturado. Descrição narrativa nunca é suficiente. A existência de cura mágica não elimina custo, acesso, escassez, lei, conhecimento, desigualdade ou risco.

### 8.15 Mortalidade

`mortality_profile` registra condições, estágios, gravidade, fatores, probabilidade, mitigação e fluxo pseudoaleatório nomeado. A doença não remove diretamente um NPC.

Quando a progressão futura resultar em morte:

1. resolve a progressão de modo reproduzível;
2. produz evento de morte com causa;
3. atualiza o estado;
4. aciona herança, cargos, luto e sucessão;
5. preserva cadeia causal, evidência, percepção e replay.

Desaparecimento não é doença. Ressurreição não é simples tratamento e permanece sistema separado.

## 9. Estado geral de saúde

O estado de saúde de uma entidade pertence ao save e compõe:

- ferimentos ativos;
- instâncias de doença e infecções;
- sintomas ativos;
- dor e fadiga;
- deficiências;
- intoxicações e envenenamentos;
- efeitos mágicos;
- resistências e imunidades individuais;
- necessidades de cuidado;
- prognóstico verdadeiro;
- diagnósticos e prognósticos conhecidos.

`overall_condition` é sempre derivada desses componentes. Não se mantém manualmente um valor geral capaz de contradizer os registros detalhados. Um resumo pode ser cache futuro, desde que recalculável e invalidado quando os componentes mudarem.

## 10. Estrutura compartilhada de condição de saúde

Uma condição de saúde é registro no save, não entidade de conteúdo. A estrutura conceitual considera, quando aplicável:

```yaml
condition_key: null
category_key: null
source:
  entity_id: null
  condition_key: null
  event_id: null
target_id: null
body_region_key: null
severity:
  value: null
  scale_key: health_0_100
intensity:
  value: null
  scale_key: health_0_100
started_at: null
duration:
  value: null
  unit_key: null
progression_key: null
state_key: null
symptom_keys: []
modifier_keys: []
limitation_keys: []
evidence_ids: []
perception_record_ids: []
treatment_record_ids: []
true_prognosis_key: null
causing_event_id: null
resolution_event_id: null
```

Chaves são ASCII em `snake_case`. O registro não é linguagem executável; condições, modificadores e progressão apontarão para vocabulários e regras futuras aprovadas. Estado atual, início, duração e resolução nunca ficam em `creature.*` ou `disease.*`.

## 11. Instância de doença e infecção

Uma instância no save considera:

- `disease_id`;
- hospedeiro;
- fonte, evento e momento da exposição;
- estágio e gravidade atuais;
- sintomas e transmissibilidade atuais;
- progresso e próxima avaliação;
- tratamentos, resposta e efeitos colaterais;
- imunidade adquirida;
- prognóstico verdadeiro;
- diagnósticos e prognósticos conhecidos;
- evidências e eventos produzidos;
- estado final.

Infecção é uma instância cuja doença possui natureza infecciosa ou parasitária. Não há pasta, template ou prefixo de instância.

## 12. Ferimentos

Um ferimento no save contém:

- chave local e tipo;
- alvo e `body_region_key` válido para sua anatomia;
- gravidade de `0`–`100`;
- causa e evento causador;
- sangramento, dor e limitação estruturados;
- risco de infecção;
- tratamentos aplicados;
- cicatrização e sequela possíveis;
- evidências e estado;
- evento de resolução.

Ferimento pode causar infecção por regras futuras, mas não vira automaticamente doença. Não há arquivo ou template de ferimento.

## 13. Dor e fadiga

Dor e fadiga são estados graduais no save, usando a escala comum `0`–`100`. Cada registro guarda fonte, intensidade, início, duração, progressão, alvo, modificadores, limitações, evidências perceptíveis e tratamento.

Podem afetar ação, deslocamento, atenção, percepção, descanso, Utility AI, risco e recuperação. Não podem existir apenas como texto narrativo. Seus efeitos mecânicos futuros permanecem estruturados e determinísticos.

## 14. Deficiências

Deficiência é representada com respeito e sem pressupor doença, corrupção, inferioridade, falha moral ou necessidade obrigatória de cura. Uma deficiência pode ser permanente, variável ou contextual e pode existir no estado inicial de um NPC futuro.

O registro conceitual pode considerar:

- capacidades afetadas;
- variação e contexto;
- adaptações e recursos auxiliares;
- barreiras ambientais;
- suporte social e profissional;
- experiência e conhecimento da própria pessoa;
- necessidades de acessibilidade;
- efeitos de ferramentas e magia, quando escolhidos e aplicáveis.

Deficiência não define personalidade, inteligência, moralidade ou objetivos. Não há entidade, pasta ou template de deficiência.

## 15. Envenenamento e intoxicação

Um registro no save pode conter fonte, substância por `resource.*` ou `item.*`, dose, via, início, sintomas, progressão, duração, tratamento, antídoto, efeitos e evidências.

Exposição pode ser declarada pela doença, recurso, item, criatura, magia ou evento conforme propriedade canônica. A condição atual pertence ao alvo no save. Veneno não é doença contagiosa por padrão e não recebe prefixo próprio.

## 16. Imunidade e resistência individuais

Registros individuais no save distinguem fonte, escopo, intensidade ou eficácia, início, duração, perda possível, doença ou condição alcançada, evento originador e evidência. Imunidade adquirida pode vir de exposição, recuperação, tratamento ou magia.

Resistência reduz probabilidade, intensidade ou progressão; imunidade impede o resultado dentro de seu escopo e condições. Nenhuma das duas concede conhecimento médico automático.

## 17. Diagnóstico, prognóstico e tratamento concretos

Um diagnóstico no save registra:

- observador e alvo;
- hipótese de doença ou condição;
- confiança `0`–`100`;
- evidências e testes;
- competência e profissão usadas;
- data;
- alternativas;
- resultado e visibilidade.

Um tratamento aplicado registra opção, responsável, alvo, requisitos verificados, recursos e itens consumidos, local, início, duração, custo, riscos, resultado, eventos e efeitos. Um prognóstico conhecido aponta para observador, fonte, confiança e data.

Nenhum desses registros modifica retroativamente a verdade. Diagnóstico e tratamento incorretos permanecem causalmente rastreáveis.

## 18. Saúde verdadeira, percepção e conhecimento

O sistema preserva:

1. estado verdadeiro;
2. sinais e sintomas observáveis;
3. evidências;
4. percepção individual;
5. interpretação;
6. conhecimento, crença ou suspeita;
7. diagnóstico e prognóstico conhecidos;
8. memória e rumor;
9. consequências posteriores.

Um NPC não recebe automaticamente causa, diagnóstico, gravidade real, transmissibilidade, prognóstico ou tratamento ideal. Conhecimento surge por sensação, observação, exame, teste, experiência, profissão, magia válida, documento, comunicação ou investigação.

Sintoma não prova causa. Teste pode falhar. Autoridade profissional aumenta a qualidade possível, não garante verdade. Rumor de doença não cria instância e instância sem percepção não cria rumor.

## 19. Intervenções do Arquiteto

Uma intervenção autorizada pode causar exposição, aplicar condição permitida, mover vetor, disponibilizar tratamento, produzir evidência, remover efeito removível ou alterar ambiente dentro das regras.

Ela não pode editar silenciosamente diagnóstico, conceder conhecimento médico automático, ocultar sua causa administrativa do log, ignorar imunidade, matar sem evento ou violar determinismo. NPCs percebem somente efeitos e evidências por vias válidas.

O fluxo permanece comando → validação → evento → condição ou efeito → evidência → percepção → conhecimento possível → consequência. Resultados probabilísticos usam fluxo nomeado e entram no replay.

## 20. Integrações canônicas

### Geografia e assentamentos

Criatura define compatibilidade ecológica e distribuição inicial; região e local não mantêm listas inversas. Doença define fatores ambientais e sociais; saúde e saneamento agregados iniciais permanecem no assentamento. População, prevalência, surtos e condições ambientais atuais pertencem ao save.

### Recursos e itens

Criatura pode declarar obtenção potencial de `resource.*` ou `item.*`. Doença pode referenciar fontes de exposição, prevenção, testes e tratamentos. Itens e recursos não recebem automaticamente condição atual nem lista inversa de todas as doenças.

### Profissões e instituições

Criatura e doença podem referenciar `profession.*` como competência, risco, treinamento, manejo, diagnóstico ou tratamento. Facções podem fornecer acesso institucional futuro. Profissão ou facção existente não significa profissional disponível no local ou no momento.

### Magia

Afinidades, resistências e vulnerabilidades usam escolas e efeitos estruturados. `magic_effect.*` pode aplicar ou remover condição, modificar sintoma, resistência, imunidade ou doença quando seu contrato autorizar. Corrupção permanece separada. Cura mágica não substitui diagnóstico, acesso ou causalidade.

### Leis

Caça, criação, comércio, transporte, sacrifício, domesticação, uso de partes, proteção, extermínio, isolamento e tratamento são avaliados por `law.*`, jurisdição, vigência, condições, exceções e licenças. Criatura e doença não possuem `legal: true` ou enum global equivalente.

### Eventos, memória e rumor

Exposição, diagnóstico, tratamento, agravamento, recuperação, sequela e morte produzem eventos quando relevantes. Evidências alimentam percepções; percepções podem produzir memórias, crenças e rumores sem revelar a causa verdadeira.

### NPCs futuros

O NPC persistente referencia sua espécie ou tipo `creature.*` quando aplicável e mantém saúde, imunidade, deficiências, diagnósticos, conhecimento e tratamentos no estado inicial ou save conforme o futuro contrato. Nenhum NPC acessa metadados administrativos.

## 21. Conteúdo estático, estado inicial, campanha e derivados

### Conteúdo estático

Define espécie, corpo abstrato, comportamento, habitat compatível, pressões, doença, transmissão possível, sintomas possíveis, tratamentos possíveis, regras e limites.

### Estado inicial

`creature.initial_state` pode semear população agregada. Instâncias iniciais de doença, ferimentos, diagnósticos e condições não ficam na definição `disease.*`; serão registradas pelo futuro contrato de NPC, evento ou estado inicial da campanha, preservando a separação entre definição e ocorrência.

### Estado atual da campanha

Possui população e distribuição atuais, indivíduos, ferimentos, infecções, sintomas, diagnósticos, tratamentos, dor, fadiga, imunidade individual, efeitos, mortes, evidências, conhecimento e rumores.

### Campos derivados

São derivados, não mantidos manualmente:

- indivíduos e NPCs de uma espécie;
- predadores de uma criatura;
- criaturas presentes em região ou local;
- papéis de vetor, reservatório e hospedeiro específicos de uma criatura;
- população e distribuição atuais;
- condição geral de saúde;
- doença por sintoma isolado;
- legalidade efetiva;
- disponibilidade e acesso a tratamento;
- diagnóstico verdadeiro para um observador;
- prognóstico conhecido;
- mortalidade ocorrida.

## 22. Crianças e conteúdo sensível

Reprodução e fertilidade permanecem abstratas. Crianças priorizam cuidado, educação, saúde e desenvolvimento. Detalhes gráficos, conteúdo explícito e sofrimento infantil usado apenas como decoração narrativa são proibidos. Configurações futuras de conteúdo sensível devem ser respeitadas.

## 23. Determinismo e IA generativa

Transmissão, progressão, diagnóstico probabilístico, tratamento, resistência, recuperação e mortalidade dependem somente de dados validados, versão, configuração, estado, semente, ordem e fluxos pseudoaleatórios nomeados.

IA generativa pode propor ou apresentar texto sujeito a revisão, mas não determina doença, diagnóstico, transmissão, efeito, tratamento, sucesso, mortalidade, percepção ou conhecimento. Texto opcional não participa da resolução.

## 24. Invariantes

1. `creature.*` representa espécie, tipo ou arquétipo.
2. Indivíduo persistente usa futuramente `npc.*` e referencia a criatura.
3. População atual pertence ao save.
4. Doença estática difere de instância de doença.
5. Sintoma não revela automaticamente a doença.
6. Ferimento não é automaticamente doença.
7. Deficiência não é automaticamente doença.
8. Envenenamento não é automaticamente doença.
9. Corrupção não é automaticamente doença.
10. Efeito mágico não é condição de saúde; pode produzir ou modificar uma.
11. Condição atual pertence ao save.
12. Diagnóstico não altera o estado verdadeiro.
13. Prognóstico conhecido pode divergir do verdadeiro.
14. Conhecimento médico precisa de fonte válida.
15. Imunidade individual pertence ao save.
16. Tratamento existente não significa tratamento acessível.
17. Morte sempre produz evento e cadeia causal.
18. População nunca fica negativa.
19. Transmissão probabilística é reproduzível.
20. Legalidade é derivada de leis aplicáveis.
21. Ausência de arte não invalida conteúdo.
22. Nenhum dado de saúde atual fica no arquivo estático.
23. Relações de habitat, ecologia e epidemiologia não possuem listas inversas concorrentes.
24. Quantidades usam `value` e `unit_key`; probabilidades usam `0`–`1`.
25. Condição geral de saúde é derivada dos componentes.
26. Nenhuma mecânica de saúde existe somente na prosa.

## 25. Validação manual

Antes de encaminhar conteúdo futuro para revisão:

- conferir caminho, slug, prefixo, `schema_version`, `content_status` e campos comuns;
- validar YAML, tipos, `null`, listas vazias, números, booleanos e ausência de strings vazias;
- confirmar chaves locais ASCII em `snake_case`;
- validar referências por categoria e ausência de nomes usados como chaves;
- distinguir espécie, indivíduo agregado e NPC persistente;
- conferir anatomia abstrata sem pressupor corpo humano;
- confirmar habitat compatível separado de presença atual;
- validar população inicial agregada, unidade e alvo geográfico único;
- confirmar ausência de população, migração ou caça atuais no conteúdo;
- conferir direção única das relações ecológicas e ausência de listas inversas;
- validar obtenção potencial sem concessão automática de recurso ou item;
- confirmar ausência de legalidade global simples;
- distinguir doença de instância, sintoma, ferimento, deficiência, veneno, corrupção e efeito mágico;
- validar transmissão, exposição, estágio, sintomas, progressão e resultados estruturados;
- validar probabilidades `0`–`1` e fluxo pseudoaleatório nomeado;
- confirmar que doença não remove NPC diretamente;
- conferir diagnóstico, prognóstico e tratamento como possibilidades estáticas ou registros do save, nunca verdade automática;
- confirmar que tratamento possível não implica acesso;
- validar imunidade da espécie separada de imunidade individual e adquirida;
- conferir percepção, evidência e conhecimento sem metaconhecimento;
- confirmar condição geral derivada e ausência de saúde atual em conteúdo estático;
- confirmar representação respeitosa de deficiências;
- confirmar ausência de conteúdo explícito ou sofrimento infantil decorativo;
- confirmar corpo Markdown coerente e sem mecânica concorrente;
- confirmar ausência de placeholders em conteúdo `approved`;
- confirmar funcionamento editorial completo sem IA e sem arte;
- confirmar que nenhuma entidade real, pasta `conditions/`, template adicional, save, asset, DSL, código ou schema executável foi criado por este contrato.

## 26. Decisões adiadas

Permanecem deliberadamente adiados:

- criaturas, doenças, nomes, lore, classificações e vocabulários reais de Eldrath;
- quantidades de criaturas e doenças, ambas `a definir`;
- anatomias, estágios de vida, habitats, dietas e populações reais;
- enum final de categorias de criatura, doença, condição, sintoma, ferimento, deficiência, toxina, risco e resultado;
- unidades, valores, doses, durações, probabilidades e faixas concretas;
- fórmulas de transmissão, progressão, resistência, imunidade, diagnóstico, tratamento, recuperação e mortalidade;
- contrato futuro de `npc.*`, eventos, memórias, rumores, relações e inventário;
- formato persistente de saúde, instância de doença, condição, diagnóstico, tratamento e população;
- autoria de instâncias iniciais de doença e condições no futuro pacote de estado inicial;
- regras executáveis de ecologia, migração, domesticação, treinamento, acessibilidade e cuidado;
- políticas concretas de conteúdo sensível;
- validação automatizada, JSON Schema, banco, API, interface e implementação;
- assets, direção visual e arte.
