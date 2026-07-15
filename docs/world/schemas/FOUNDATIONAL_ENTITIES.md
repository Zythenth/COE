# Entidades fundamentais — schemas editoriais

Este documento especializa o [contrato editorial comum](../CONTENT_SCHEMA.md), versão `1.0.0`, para as cinco entidades fundamentais. Ele define representação editorial, não conteúdo de Eldrath nem validação executável. Em conflito, o GDD canônico local prevalece.

## Regras compartilhadas

Todos os tipos usam os campos comuns `schema_version`, `id`, `name`, `content_status`, `tags`, `aliases`, `summary`, `references`, `art` e `notes`, com os tipos e a semântica definidos no contrato comum. `schema_version` é a string `"1.0.0"`; `id` usa o prefixo indicado; `name` não é referência; `content_status` é `draft`, `in_review`, `approved` ou `deprecated`; `tags` e `references` são listas.

Campo omitido significa que é opcional ou não se aplica; `null` significa que o dado se aplica, mas é desconhecido; `[]` significa que se sabe não haver itens; string vazia é proibida. Placeholders existem exclusivamente em templates e são proibidos em conteúdo `approved`. Referências usam IDs completos, não nomes ou caminhos, e referências de conteúdo `approved` precisam estar resolvidas.

## `world`

**Finalidade.** Define o ponto de entrada autoral do pacote: a identidade do mundo e as referências para seu contexto inicial. Não substitui o reino, o calendário, idiomas ou culturas referenciados.

| Aspecto | Regra |
|---|---|
| Formato | YAML puro |
| Localização futura | `content/worlds/eldrath/world.yaml` |
| Prefixo e arquivo | `world.{slug}`; o pacote possui somente `world.yaml` |
| Dependências | contrato comum; calendário, idiomas, culturas e reino somente depois de existirem |

**Campos obrigatórios.** Além dos campos comuns obrigatórios: `identity` (mapa), `primary_calendar_id` (ID `calendar.*` ou `null` em rascunho), `initial_date` (string de data do mundo ou `null`), `initial_era_id` (ID interno de era ou `null`), `language_ids` (lista de IDs `language.*`), `culture_ids` (lista de IDs `culture.*`), `initial_kingdom_id` (ID `kingdom.*` ou `null`), `unit_system` (mapa), `unit_definitions` (lista de mapas) e `references` (lista).

`identity` possui `world_name` (string não vazia) e pode incluir `native_name` (string). `unit_system` possui `system_key`, `name` e `notes`. Cada entrada de `unit_definitions` possui `key`, `quantity_type`, `name`, `symbol`, `base_unit_key`, `conversion_factor` e `notes`. `quantity_type` usa uma chave conceitual entre `mass`, `volume`, `length`, `time`, `count` e `area`; nenhum valor concreto é criado por este schema.

`key` é única no mundo. Uma unidade-base usa `base_unit_key: null` e `conversion_factor: null`; uma unidade derivada aponta diretamente para a unidade-base do mesmo `quantity_type` e usa fator numérico positivo quando conhecido. Ciclos são proibidos. Outros arquivos usam somente `unit_key` e não repetem a definição. Moeda não é unidade e não aparece em `unit_definitions`. O contrato completo está em [MATERIAL_ECONOMY_ENTITIES.md](MATERIAL_ECONOMY_ENTITIES.md).

**Campos opcionais.** `aliases`, `summary`, `art`, `notes` e metadados editoriais adicionais documentados pelo contrato comum. Não há campos narrativos obrigatórios porque o formato não possui corpo Markdown.

**Referências permitidas.** `primary_calendar_id` aponta para `calendar.*`; `language_ids` para `language.*`; `culture_ids` para `culture.*`; `initial_kingdom_id` para `kingdom.*`; `references` pode registrar somente IDs completos relevantes e resolvidos quando aprovado. `initial_era_id` é um ID interno definido pelo calendário referenciado, não uma entidade independente.

**Invariantes e validação manual.** Deve existir exatamente um `world.yaml` por pacote. O arquivo referencia documentos, nunca incorpora suas estruturas completas; não duplica dados de reino, não armazena estado gerado pela simulação e não armazena saves. Chaves de unidade são únicas; tipos e unidades-base são compatíveis; fatores conhecidos são positivos; não há ciclos. Em `approved`, identidade e referências obrigatórias estão preenchidas, existem e concordam entre si; nenhum placeholder permanece. A revisão confere a unicidade do arquivo, prefixo do ID, sistema de unidades e ausência de dados de estado.

**Decisões adiadas.** Valores de Eldrath, unidades concretas e formato da data aguardam as entidades reais. Placeholders são permitidos apenas em `world.template.yaml`.

## `calendar`

**Finalidade.** Descreve a cronologia legível do mundo: época, eras, meses, semana, estações, regras anuais e formato de data.

| Aspecto | Regra |
|---|---|
| Formato | Markdown com front matter YAML |
| Localização futura | `content/worlds/eldrath/calendars/{slug}.md` |
| Prefixo e arquivo | `calendar.{slug}`; arquivo `{slug}.md` |
| Dependências | contrato comum e identidade do mundo |

**Campos obrigatórios.** Além dos campos comuns obrigatórios: `epoch` (mapa), `eras` (lista de mapas), `months` (lista de mapas), `weekdays` (lista de mapas), `seasons` (lista de mapas), `year_rules` (mapa), `date_format` (string ou `null` em rascunho), `abbreviations` (mapa) e `recurring_events` (lista de mapas).

Cada item de `eras` tem `id` interno estável, `name` e `order`; cada mês tem `id` interno estável, `name`, `order`, `days` e `season_id` (`null` quando não aplicável); cada dia da semana tem `id`, `name` e `order`; cada estação tem `id`, `name` e `order`. `year_rules` declara explicitamente a regra comum, a regra excepcional quando houver e como os dias são calculados. `recurring_events` registra somente estruturas de eventos recorrentes quando existirem; uma lista vazia afirma que não há nenhum conhecido.

**Campos opcionais.** `summary`, `aliases`, `art`, `notes`, `epoch.description`, observações estruturadas de períodos e seções Markdown explicativas. O corpo Markdown pode usar `Funcionamento`, `Uso cultural` e `Observações editoriais`; não substitui os campos estruturados.

**Referências permitidas.** `season_id` aponta somente para um ID interno presente em `seasons`; `references` usa IDs completos de entidades externas relevantes. Não há dependência de código ou referência por nome.

**Invariantes e validação manual.** Ordens não se repetem em uma mesma lista; IDs internos de meses e dias são estáveis; `days` é inteiro positivo; a soma de `months[].days` é verificável com as regras de ano. Regras excepcionais precisam ser explícitas. A revisão calcula a soma, confere ordens, IDs internos, referência de estação e que o formato final de data esteja definido antes de aprovar o calendário real.

**Decisões adiadas.** Nenhuma era, mês, estação, abreviação ou regra concreta é definida aqui.

## `language`

**Finalidade.** Registra uma língua como entidade editorial independente de seu estado de revisão e de uma cultura específica.

| Aspecto | Regra |
|---|---|
| Formato | Markdown com front matter YAML |
| Localização futura | `content/worlds/eldrath/languages/{slug}.md` |
| Prefixo e arquivo | `language.{slug}`; arquivo `{slug}.md` |
| Dependências | contrato comum; culturas e regiões são referências futuras opcionais |

**Campos obrigatórios.** Além dos campos comuns obrigatórios: `native_name` (string não vazia), `language_status` (enum), `writing_systems` (lista de mapas), `culture_ids` (lista de IDs `culture.*`), `region_ids` (lista de IDs `region.*`), `speaker_groups` (lista de mapas), `official_uses` (lista de mapas), `religious_uses` (lista de mapas), `magical_uses` (lista de mapas), `intelligibility` (lista de mapas), `naming_conventions` (mapa), `phonetic_notes` (string ou `null`) e `references` (lista).

`language_status` descreve a língua, nunca sua revisão, e pode ser `active`, `declining`, `ceremonial` ou `extinct` quando aplicável. `content_status` mantém separadamente o estado editorial. Os mapas de usos, grupos, inteligibilidade e escrita precisam explicitar seus tipos e referências quando o conteúdo existir.

**Campos opcionais.** `summary`, `aliases`, `art`, `notes` e seções Markdown: `Visão geral`, `Escrita`, `Uso`, `Convenções de nomes` e `História`.

**Referências permitidas.** `culture_ids` usam `culture.*`; `region_ids` usam `region.*`; relações de inteligibilidade apontam para `language.*`; usos institucionais ou religiosos usam os IDs de categorias que os schemas posteriores autorizarem. `references` permanece uma lista de IDs completos.

**Invariantes e validação manual.** Não se usa nome visível como chave; status da língua não substitui `content_status`; sistemas de escrita e convenções de nomes não são vocabulário inventado. A revisão confere prefixo, arquivo, separação de estados e resolução das referências no conteúdo aprovado.

**Decisões adiadas.** Idiomas, palavras, alfabetos, nomes próprios e os conjuntos concretos de usos permanecem sem definição.

## `culture`

**Finalidade.** Descreve padrões sociais compartilhados sem reduzir pessoas, idiomas ou territórios a uma identidade única.

| Aspecto | Regra |
|---|---|
| Formato | Markdown com front matter YAML |
| Localização futura | `content/worlds/eldrath/cultures/{slug}.md` |
| Prefixo e arquivo | `culture.{slug}`; arquivo `{slug}.md` |
| Dependências | contrato comum; idiomas e regiões quando existirem |

**Campos obrigatórios.** Além dos campos comuns obrigatórios: `region_ids` (lista de IDs `region.*`), `language_ids` (lista de IDs `language.*`), `values` (lista de mapas), `customs` (lista de mapas), `family_structure` (mapa ou `null`), `social_positions` (lista de mapas), `traditions` (lista de mapas), `taboos` (lista de mapas), `magic_view` (mapa ou `null`), `religion_relations` (lista de mapas), `profession_relations` (lista de mapas), `naming_conventions` (mapa), `clothing` (lista de mapas), `foodways` (lista de mapas), `festivals` (lista de IDs ou mapas referenciáveis), `rites` (lista de mapas), `internal_conflicts` (lista de mapas) e `references` (lista).

**Campos opcionais.** `summary`, `aliases`, `art`, `notes` e seções Markdown: `Valores`, `Cotidiano`, `Família`, `Magia`, `Religião`, `Tradições`, `Conflitos internos` e `Diversidade`.

**Referências permitidas.** Regiões usam `region.*`; idiomas usam `language.*`; relações religiosas, profissionais, festivais e ritos usam IDs completos quando as respectivas entidades existirem e seus schemas forem definidos. `religion_relations` registra a perspectiva cultural direcionada a uma tradição; não é lista inversa de religiões originadas e não duplica relações doutrinárias de `religion.*`. Não se registram nomes como referências.

**Invariantes e validação manual.** Cultura não equivale a região ou idioma: uma cultura pode ocorrer em várias regiões e uma região pode conter várias culturas. Os dados devem admitir divergências internas e não determinam automaticamente valores, comportamento ou destino de NPCs. Estereótipos absolutos são proibidos. A revisão confere esses limites, referências e que a prosa não generalize indivíduos como regras inevitáveis.

**Decisões adiadas.** Não há cultura, valor, costume, religião, vestimenta, alimento ou rito real definido nesta tarefa.

## `kingdom`

**Finalidade.** Registra o estado inicial autoral de uma unidade política sem incorporar entidades relacionadas nem estado produzido por campanha.

| Aspecto | Regra |
|---|---|
| Formato | YAML puro |
| Localização futura | `content/worlds/eldrath/kingdom.yaml` |
| Prefixo e arquivo | `kingdom.{slug}`; arquivo único `kingdom.yaml` para o reino inicial |
| Dependências | contrato comum; mundo, calendário, culturas e schemas posteriores para referências políticas, sociais e econômicas |

**Campos obrigatórios.** Além dos campos comuns obrigatórios: `demonym` (string ou `null`), `symbol` (mapa ou `null`), `colors` (lista de strings), `motto` (string ou `null`), `foundation` (mapa ou `null`), `political_system` (mapa ou `null`), `succession` (mapa ou `null`), `capital_id` (ID `settlement.*` ou `null`), `primary_currency_key` (chave interna ou `null`), `currencies` (lista de mapas), `calendar_id` (ID `calendar.*` ou `null`), `language_ids` (lista de IDs `language.*`), `initial_state` (mapa) e `founding_event_ids` (lista de IDs `event.*`).

`initial_state` contém `era_id` (ID interno de era ou `null`), `ruler_id` (ID `npc.*` ou `null`), `council_faction_ids` (lista de IDs `faction.*`), `external_relations` (lista de mapas), `metrics` (mapa), `treasury` (mapa monetário), `administrative_capacity` (número na escala aplicável ou `null`) e `crisis_ids` (lista de IDs). Esses valores semeiam a campanha e não representam estado atual permanente.

`initial_state.metrics` contém `stability`, `legitimacy`, `prosperity`, `security`, `cohesion`, `freedom`, `inequality`, `magical_tension`, `trust_in_crown` e `religious_influence`, como números de `0` a `100` ou `null`. `foundation`, `political_system`, `succession`, `symbol` e cada relação externa usam mapas estruturados, com referências por ID quando apontarem a outra entidade.

Cada entrada de `currencies` possui `key`, `name`, `symbol`, `subdivisions`, `exchange_reference`, `legal_tender` e `notes`. Cada subdivisão possui `key`, `name`, `symbol`, `conversion_factor` e `notes`. `exchange_reference`, quando aplicável, possui `reference_currency_key`, `ratio`, `effective_date`, `source` e `notes`; documenta somente uma relação inicial ou de referência, nunca câmbio atual. `primary_currency_key` precisa corresponder a uma entrada da lista. Nome e símbolo podem mudar sem alterar a chave. Moeda não é entidade independente nem recurso nesta versão; outros arquivos usam somente `currency_key`.

`initial_state.treasury` registra somente um valor inicial no formato `money: { amount, currency_key }`. Saldo atual, câmbio atual, inflação e dívida pertencem ao estado futuro. Os contratos monetários completos estão em [MATERIAL_ECONOMY_ENTITIES.md](MATERIAL_ECONOMY_ENTITIES.md).

São campos derivados, nunca listas mantidas manualmente: `region_ids`, consultando `region.kingdom_id`; leis gerais e mágicas aplicáveis, consultando `law.jurisdiction`; dominância religiosa, consultando `religion.initial_state.diffusion`; e tolerância ou proibição jurídica de religiões, consultando as leis aplicáveis.

**Campos opcionais.** `summary`, `aliases`, `art`, `notes` e campos internos dos mapas que só se apliquem quando seus sistemas especializados forem definidos.

**Referências permitidas.** Capital, governante inicial, facções de conselho iniciais, calendário, idiomas, crises e eventos fundadores usam IDs completos. `initial_state.era_id` é interno ao calendário. Moedas usam chaves internas estáveis do próprio reino, não IDs de entidade. Leis, regiões e condições religiosas são derivadas por suas referências canônicas. O reino não incorpora documentos completos de outras entidades.

**Invariantes e validação manual.** Métricas usam a escala `0`–`100` definida no GDD; métrica desconhecida é `null`, nunca `0`. Chaves de moedas e subdivisões são únicas; a moeda principal existe na lista; fatores conhecidos são positivos; `currency_key` monetária resolve no reino aplicável. Capital e referências iniciais não incorporam entidades. Regiões, leis e condições religiosas são consultas derivadas, não listas inversas. O estado inicial fica sob `initial_state`; mutações posteriores pertencem ao estado da simulação. Sucessores políticos são entidades ou relações posteriores e não sobrescrevem a história do reino original. A revisão confere intervalos, ausência correta, chaves, referências resolvidas no aprovado e ausência de saves ou estado derivado.

**Decisões adiadas.** Gentílico, símbolo, cores, lema, fundação, capital, governante inicial, facções de conselho, religião, moedas, subdivisões, relações monetárias, leis, métricas e crises reais não são definidos neste schema.
