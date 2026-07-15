# Entidades geográficas — schemas editoriais

Este documento especializa o [contrato editorial comum](../CONTENT_SCHEMA.md), versão `1.0.0`, para `region`, `settlement`, `location` e `route`. É um contrato editorial legível, não um schema executável, JSON Schema, tipo de programação ou implementação. Não cria geografia, lore, vocabulários concretos nem entidades de Eldrath.

## Regras compartilhadas e hierarquia canônica

Todas as entidades usam os campos comuns `schema_version`, `id`, `name`, `content_status`, `tags`, `aliases`, `summary`, `references`, `art` e `notes`. `schema_version` é a string `"1.0.0"`; `content_status` é editorial e independente de qualquer estado do mundo; `tags` e `references` são listas. `null` significa que um dado aplicável ainda é desconhecido; `[]` afirma que se sabe não haver itens; strings vazias são proibidas. Placeholders são exclusivos dos templates e jamais podem permanecer em conteúdo `approved`.

```text
Mundo
└── Reino
    └── Região
        ├── Assentamento
        │   └── Local
        └── Local regional
```

A direção única de pertencimento é obrigatória: `region.kingdom_id` aponta para o reino; `settlement.region_id` aponta para a região; `location.region_id` aponta para a região; `location.settlement_id` e `location.parent_location_id` são opcionais. Uma rota aponta somente para seus dois extremos, `origin_id` e `destination_id`.

São fontes canônicas: o reino de uma região, a região de um assentamento, a região/assentamento/local pai de um local e os extremos de uma rota. São consultas derivadas futuras, e não campos duplicados: assentamentos de uma região, locais de um assentamento, locais filhos, rotas ligadas a um lugar, reino de assentamentos e locais. O futuro carregador ou consulta deverá derivá-los pelos IDs; a prosa não deve reintroduzir essas relações como dados mecânicos.

Referências de entidade usam IDs completos, como `kingdom_id`, `region_id`, `settlement_id`, `parent_location_id`, `controller_faction_id`, `resource_id`, `origin_id` e `destination_id`. Chaves controladas usam valores de vocabulário futuro, nunca IDs inventados: `biome_key`, `climate_key`, `terrain_keys`, `settlement_type`, `location_type`, `route_type` e `access_modes`. Onde este schema mencionar uma chave controlada, o vocabulário de valores permanece decisão adiada, salvo as categorias mínimas expressamente listadas.

## `region`

**Finalidade e posição.** Representa uma divisão territorial pertencente a um reino e concentra condições geográficas, sociais e ambientais iniciais. Não incorpora assentamentos, locais, rotas ou recursos como documentos internos.

| Aspecto | Regra |
|---|---|
| Formato | Markdown com front matter YAML |
| Diretório futuro | `content/worlds/eldrath/regions/{slug}.md` |
| Prefixo e arquivo | `region.{slug}`; arquivo `{slug}.md` |
| Dependências | contrato comum; reino; vocabulários geográficos e entidades futuras referenciadas |

**Campos obrigatórios.** Além dos campos comuns aplicáveis: `kingdom_id` (ID `kingdom.*`), `biome_key` (chave controlada), `climate_key` (chave controlada), `terrain_keys` (lista de chaves controladas), `initial_state` (mapa), `magical_traditions` (lista de chaves controladas), `faction_influence` (lista de mapas), `resource_presence` (lista de mapas), `borders` (lista de mapas), `reputation` (número ou `null`, com escala adiada) e `references` (lista).

`initial_state` contém `population_estimate` (inteiro não negativo ou `null`), `prosperity`, `security`, `tension`, `danger_level` e `magical_tension` (indicadores ou `null`). `prosperity`, `security` e `magical_tension` usam `0`–`100` quando o indicador correspondente estiver estabelecido pelo GDD; `tension` e `danger_level` aguardam escala controlada. A população é uma estimativa inicial. Esses dados não são atualizados a cada tick: mutações pertencem ao estado futuro da simulação.

Cada entrada de `faction_influence` possui `faction_id` (`faction.*`), `influence` (número na escala aplicável ou `null`), `visibility` (chave controlada) e `notes` opcional. Cada entrada de `resource_presence` possui `resource_id` (`resource.*`), `abundance`, `accessibility` e `seasonality` (chaves controladas) e `notes` opcional. Uma entrada de `borders` declara exatamente um alvo: `adjacent_region_id` (`region.*`), `external_boundary_key` ou `natural_obstacle_key`; também possui `boundary_type` (chave controlada) e `notes` opcional. A mesma fronteira não pode ser repetida sob outra descrição.

**Campos opcionais, corpo e proibições.** `aliases`, `summary`, `art` e `notes` seguem o contrato comum. O corpo Markdown usa `Visão geral`, `Geografia`, `Clima`, `População`, `Economia`, `Tradição mágica`, `Influência política`, `Perigos`, `Reputação`, `História` e `Observações editoriais`. Ele explica dados já estruturados, sem criar métricas concorrentes. São proibidos: listas manuais de assentamentos, locais ou rotas; reino duplicado; estado simulado; valores de recurso, população, bioma, economia ou conflito não estruturados.

**Validação manual.** Conferir prefixo, arquivo, `kingdom_id`, chaves controladas, métricas e exclusividade de cada fronteira. Em `approved`, todas as referências existem, não há placeholders e `null` não encobre valor conhecido. Decisões adiadas: vocabulários de bioma, clima, terreno, tradição, fronteira, influência, abundância, acesso, sazonalidade e as escalas ainda não fixadas.

## `settlement`

**Finalidade e posição.** Representa um assentamento situado em uma região. `settlement_type` classifica a forma do assentamento; `administrative_roles` registra papéis políticos aplicáveis e não cria outra categoria de entidade.

| Aspecto | Regra |
|---|---|
| Formato | Markdown com front matter YAML |
| Diretório futuro | `content/worlds/eldrath/settlements/{slug}.md` |
| Prefixo e arquivo | `settlement.{slug}`; arquivo `{slug}.md` |
| Dependências | contrato comum; região; futuros schemas político, religioso, econômico, de recursos e de rotas |

**Campos obrigatórios.** Além dos comuns: `region_id` (`region.*`), `settlement_type` (chave controlada), `administrative_roles` (lista de chaves controladas), `ruler_id` (`npc.*` ou `null`), `governing_faction_ids`, `local_law_ids`, `dominant_religion_ids`, `tolerated_religion_ids`, `institution_ids` (listas de IDs completos nas categorias autorizadas pelos respectivos schemas), `initial_state` (mapa), `production`, `consumption`, `trade`, `initial_stocks`, `initial_prices`, `faction_presence`, `local_problems` (listas de mapas) e `references` (lista).

Nesta etapa `settlement_type` admite ao menos `city` e `village`; nenhum tipo adicional é aprovado sem justificativa documental. `administrative_roles` pode incluir `kingdom_capital` e `regional_seat` quando aplicável. Um papel não altera o tipo do assentamento e capital não é entidade separada.

`initial_state` contém `population`, `housing_capacity`, `wealth`, `security`, `health`, `sanitation`, `literacy`, `openness_to_outsiders`, `acceptance_of_magic`, `prosperity` e `tension`. `population` e `housing_capacity` são inteiros não negativos ou `null`; os demais são indicadores de `0`–`100` ou `null`. Nenhuma dessas métricas é repetida como valor mecânico na prosa. São condições iniciais imutáveis do pacote; o estado mutável é da simulação futura.

Cada entrada de `production` ou `consumption` é um fluxo do contrato de [economia material](MATERIAL_ECONOMY_ENTITIES.md): `flow_id` estável e único no arquivo; exatamente um `resource_id` ou `item_id`; `quantity: { value, unit_key }`; `period_key`; `required_profession_ids`; `required_location_type_keys`; `required_item_ids`; `input_refs`; `output_refs`; `condition_keys`; `waste_outputs`; e `notes`. `input_refs` e `output_refs` apontam somente para `flow_id` irmãos no mesmo arquivo. Cada resíduo declara exatamente um `resource_id` ou `item_id`, `quantity` e `notes`.

Cada entrada de `trade` possui `trade_id` estável no arquivo, exatamente um `resource_id` ou `item_id`, `quantity`, `period_key`, `direction`, `counterparty_id`, `initial_price`, `condition_keys` e `notes`. Quantidade por período descreve o fluxo inicial; `initial_price` usa `money`, `quantity_basis`, `quality_key`, `settlement_id`, `effective_date` e `source` do contrato de preço. Não se usa dinheiro como quantidade.

`initial_stocks` usa exatamente um `resource_id` ou `item_id`, `quantity`, `quality_key`, `storage_location_id` opcional, `reserved_quantity` opcional e `notes`. `initial_prices` usa exatamente um `resource_id` ou `item_id` e um mapa `price` completo. `reserved_quantity` não pode ser negativa, usa unidade compatível e não supera o estoque inicial conhecido. `faction_presence` contém `faction_id`, `presence`, `visibility` e `notes`. `local_problems` contém `problem_key`, `severity`, `visibility`, `related_entity_ids` e `notes`; quando problemas se tornarem entidades próprias, a relação deve usar seus IDs.

`production`, `consumption` e `trade` descrevem capacidades e relações econômicas iniciais, não atividade corrente. Estoques e preços iniciais podem iniciar uma campanha. Produção, consumo, estoque, preço, salários, riqueza, vagas e contratos atuais pertencem exclusivamente ao estado futuro da simulação; os arquivos não são atualizados a cada tick.

**Corpo, dados derivados e validação.** O corpo usa `Visão geral`, `Posição regional`, `Governo`, `População`, `Bairros e organização`, `Economia`, `Comércio`, `Instituições`, `Religião`, `Magia`, `Cotidiano`, `Problemas locais`, `Eventos recentes`, `História` e `Observações editoriais`. Bairros, edifícios, instituições, locais, rotas, reino e população calculada não são listas de pertencimento manuais; são referências existentes ou consultas derivadas. A revisão confere região, distinção entre tipo e papel administrativo, faixas, não negatividade, exclusividade entre recurso e item, compatibilidade de unidades, resolução monetária, categorias de ID, ausência de estado atual, ausência de placeholders e referências aprovadas existentes. Vocabulários de períodos, presença, problema e comércio permanecem adiados.

## `location`

**Finalidade e posição.** Representa um lugar urbano, regional, natural ou especial. Todo local pertence a uma região; pode pertencer a um assentamento e pode ter um local pai, sem transferir a fonte canônica para a prosa.

| Aspecto | Regra |
|---|---|
| Formato | Markdown com front matter YAML |
| Diretório futuro | `content/worlds/eldrath/locations/{slug}.md` |
| Prefixo e arquivo | `location.{slug}`; arquivo `{slug}.md` |
| Dependências | contrato comum; região; assentamento, facções, recursos, segredos e eventos quando existirem |

**Campos obrigatórios.** Além dos comuns: `region_id` (`region.*`), `settlement_id` (`settlement.*` ou `null`), `parent_location_id` (`location.*` ou `null`), `location_type` (chave controlada), `controller_faction_id` (`faction.*` ou `null`), `access` (mapa), `capacity` (inteiro não negativo ou `null`), `resource_presence` (lista de mapas), `danger_keys` (lista de chaves controladas), `secret_ids`, `event_ids` (listas de IDs), `magical_properties` (lista de mapas), `initial_visibility` (mapa) e `references` (lista).

`location_type` admite, no mínimo, as categorias `building`, `district`, `natural_site`, `ruin`, `sanctuary`, `academy`, `mine`, `river`, `battlefield`, `prison`, `hideout`, `portal` e `market`. São categorias controladas, não entidades criadas. Um local não pode ser seu próprio pai; ciclos de `parent_location_id` são proibidos. Se `settlement_id` existir, seu assentamento precisa ter a mesma `region_id`; um local regional usa `settlement_id: null`.

`access` contém `access_level` (`public`, `restricted`, `forbidden` ou `hidden`), `requirements` (lista de chaves ou IDs controlados), `authority_ids` (lista de IDs), `schedule` (mapa ou `null`) e `notes` opcional. `resource_presence` usa `resource_id`, `abundance`, `accessibility`, `seasonality` e `notes`. Cada item de `magical_properties` possui `property_key`, `intensity` e `notes`, com escalas e vocabulários adiados. `initial_visibility` contém `discovery_state_key` e `interface_visibility_key`, ambos controlados, e `notes` opcional.

**Quatro dimensões distintas.** `content_status` é a maturidade editorial do arquivo; `access.access_level` é acesso físico; `initial_visibility.discovery_state_key` é descoberta no mundo; `secret_ids` aponta a segredos como entidades próprias; `initial_visibility.interface_visibility_key` orientará a futura apresentação. Nenhum desses campos substitui outro.

**Corpo, proibições e validação.** O corpo usa `Visão geral`, `Função`, `Localização`, `Acesso`, `Controlador`, `Características`, `Recursos`, `Perigos`, `Propriedades mágicas`, `Segredos`, `Acontecimentos relacionados`, `História` e `Observações editoriais`. São proibidos parentesco espacial em listas invertidas, ciclos, estado simulado e a revelação de segredo só pela prosa. A revisão confere região, consistência de assentamento, cadeia de pais, acesso, separação das quatro dimensões e referências resolvidas. Vocabulários de descoberta, interface, perigo, propriedade, agenda e requisitos ficam adiados.

## `route`

**Finalidade e posição.** Representa uma ligação explícita do grafo sistêmico entre lugares, sem pertencer por duplicação a uma região, assentamento ou local.

| Aspecto | Regra |
|---|---|
| Formato | Markdown com front matter YAML |
| Diretório futuro | `content/worlds/eldrath/routes/{slug}.md` |
| Prefixo e arquivo | `route.{slug}`; arquivo `{slug}.md` |
| Dependências | contrato comum; assentamentos, locais, unidades e futuros vocabulários de viagem |

**Campos obrigatórios.** Além dos comuns: `origin_id`, `destination_id`, `directionality`, `route_type`, `distance`, `base_travel_time`, `access_modes`, `initial_state`, `controller_faction_id`, `toll`, `seasonal_access`, `risk_profile` e `references`.

`origin_id` e `destination_id` aceitam somente IDs `settlement.*` ou `location.*`; ambos devem existir em conteúdo `approved` e não podem ser iguais. `directionality` é explícita e controla como a ligação é interpretada. Uma rota bidirecional usa um único arquivo, nunca um arquivo por sentido. Rotas diferentes entre o mesmo par só são válidas quando `route_type` ou a função documentada forem materialmente distintos.

`route_type` e `access_modes` são chaves controladas; `access_modes` é lista. `distance` e `base_travel_time` são mapas `{ value, unit_key }`: `value` é número positivo ou `null` em rascunho; `unit_key` resolve em `world.unit_definitions` e é compatível com comprimento ou tempo. Esta etapa não calcula duração. `initial_state` contém `safety`, `capacity`, `condition`, `traffic` e `magical_instability`, cada um como indicador `0`–`100` ou `null`.

`toll` contém `money: { amount, currency_key }`, `collector_id` (ID completo ou `null`), `exemptions` (lista de IDs ou chaves controladas) e `notes`. `currency_key` resolve na lista interna de moedas do reino aplicável e é a única forma de referência monetária. `seasonal_access` é lista de mapas com `season_key`, `access_state`, `travel_modifier`, `risk_modifier` e `notes`; não cria estações nem modificadores concretos. `risk_profile` contém `danger_keys` (lista), `risk_level` (indicador ou `null`) e `notes`.

Distância e duração-base são propriedades estáveis de referência. Segurança, capacidade, condição, tráfego, instabilidade e pedágio do arquivo são condições iniciais que podem iniciar uma campanha. Carga, tráfego, risco, controle e pedágio atuais pertencem ao estado futuro e não reescrevem a rota autoral.

**Corpo, dados derivados e validação.** O corpo usa `Visão geral`, `Origem e destino`, `Percurso`, `Terreno`, `Meios de viagem`, `Controle`, `Pedágios`, `Perigos`, `Variações sazonais`, `Importância comercial`, `Acontecimentos`, `História` e `Observações editoriais`. Listas de rotas por extremo são derivadas, assim como região dos extremos. A revisão confere prefixo, extremos aprovados e permitidos, desigualdade entre eles, direção, positividade quando conhecida, compatibilidade de `unit_key`, resolução de `currency_key`, ausência de estado atual, ausência de duplicação bidirecional, referências e placeholders. Vocabulários de tipo, direção, acesso, estação, risco, unidade, moeda e pedágio permanecem adiados.

## Revisão conjunta

Antes de aprovar qualquer entidade geográfica, conferir campos comuns, caminho, prefixo, nome de arquivo, referências por ID, chaves controladas, `null`, listas vazias, corpo Markdown e ausência de placeholders. A aprovação exige que a hierarquia seja navegável apenas pelas referências canônicas, sem duplicar consultas derivadas, e que nenhum dado inicial se passe por estado da simulação.
