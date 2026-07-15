# Economia material — schemas editoriais

Este documento especializa o [contrato editorial comum](../CONTENT_SCHEMA.md), versão `1.0.0`, para as estruturas econômicas compartilhadas e para as entidades `resource`, `profession` e `item`. É um contrato editorial legível, não um schema executável, JSON Schema, tipo de programação, fórmula de preço ou implementação de simulação. Não cria recursos, profissões, itens, moedas, unidades, valores ou relações econômicas reais de Eldrath.

## 1. Princípios econômicos

- A economia cria pressões narrativas compreensíveis sem exigir contabilidade individual de toda a produção de massa.
- IDs completos referenciam entidades; chaves estáveis controladas identificam unidades, moedas, períodos, qualidades, operações e classificações.
- Quantidade física, valor monetário, taxa, preço e faixa são estruturas diferentes e não podem ser usadas como sinônimos.
- Recursos fungíveis podem ser agregados por quantidade. Itens são definições de objetos discretos; suas cópias futuras pertencem ao estado da simulação.
- Nomes visíveis de moedas e unidades podem mudar sem alterar suas chaves.
- Zero é sempre um valor conhecido. Informação aplicável ainda desconhecida usa `null`; lista vazia declara ausência conhecida.
- Valores derivados não são duplicados no conteúdo. Produtores, consumidores, preços e estoques atuais serão consultas do estado futuro.
- Nenhuma regra futura do núcleo pode depender de IA generativa.

## 2. Conteúdo versus estado

Os arquivos em `content/` definem propriedades estáveis, valores e relações iniciais, capacidades, métodos permitidos e referências. Eles não são reescritos a cada tick.

O estado futuro da simulação armazenará estoque, preço, produção, consumo, salário, riqueza e tráfego atuais, além de escassez, inflação, dívida, contratos ativos e demais mutações da campanha. Um valor inicial pode ser copiado para o estado ao iniciar uma campanha; depois disso, a fonte do valor atual é o save, não o arquivo autoral.

Consequentemente:

- `reference_value` é uma referência editorial estável, não o preço vigente;
- um preço inicial local pode existir no assentamento e iniciar o estado;
- estoque inicial pode existir no assentamento, mas o estoque atual nunca volta ao arquivo;
- capacidades e perfis de produção não afirmam que uma produção esteja ocorrendo agora;
- modelos de renda não registram salário atual;
- propriedades, localização, condição e quantidade de uma cópia de item pertencem à futura instância.

### 2.1 Intervenções materiais futuras

Uma Intervenção do Arquiteto pertence ao estado da campanha. Para objetos discretos, ela aponta para uma `item_instance`, nunca para o arquivo estático `item.*`; para recursos fungíveis, aponta para uma quantidade atual persistida no save, nunca para a definição `resource.*`. O conteúdo pode definir capacidades, unidades, limites, condições e propriedades autorizadas, mas não registra a intervenção concreta.

Mover, soltar, colocar, retirar ou transferir uma instância precisa preservar proprietário ou recipiente, origem, destino, condição, proveniência e inexistência de uso duplo quando aplicáveis. Adicionar ou retirar recurso precisa validar quantidade, unidade, reserva e não negatividade. Comando, evento, evidências e percepções seguem o [contrato conceitual de intervenção](INTERVENTION_PERCEPTION_AND_KNOWLEDGE.md).

## 3. Quantidade

Estrutura compartilhada:

```yaml
quantity:
  value: null
  unit_key: null
```

`value` é numérico. Quando representa estoque físico, reserva, capacidade consumível ou outro total material, não pode ser negativo. `unit_key` é uma chave controlada definida em `world.unit_definitions` e precisa ser compatível com o `base_unit_key` e a natureza do recurso ou item. Zero é valor real; desconhecido usa `null`. `value` conhecido exige `unit_key` conhecido, salvo quando o schema especializado documentar expressamente uma contagem adimensional.

## 4. Valor monetário

Estrutura compartilhada:

```yaml
money:
  amount: null
  currency_key: null
```

`amount` é numérico. `currency_key` referencia uma entrada de `kingdom.currencies`; moeda não é entidade independente nesta versão. Toda referência monetária usa somente `currency_key`. Zero é valor real; desconhecido usa `null`. Um valor conhecido exige uma moeda conhecida. Valores monetários de reinos diferentes só podem ser comparados quando uma relação monetária aplicável estiver documentada; taxas de câmbio atuais pertencerão ao estado da simulação.

## 5. Taxa

Estrutura compartilhada:

```yaml
rate:
  quantity:
    value: null
    unit_key: null
  period_key: null
```

`period_key` é uma chave controlada de período. Conceitos como hora, dia, semana, mês, estação e ano orientam o vocabulário futuro, mas este documento não cria valores reais. Uma taxa expressa quantidade por período; ela não expressa dinheiro, preço ou duração. Taxas de perda não podem produzir estoque físico negativo e precisam declarar as condições em que se aplicam.

## 6. Preço

Estrutura compartilhada:

```yaml
price:
  money:
    amount: null
    currency_key: null
  quantity_basis:
    value: null
    unit_key: null
  quality_key: null
  settlement_id: null
  effective_date: null
  source: null
```

`quantity_basis` declara quanto do bem é adquirido pelo valor em `money`; não deve ser confundido com estoque ou lote em trânsito. `quality_key`, `settlement_id`, `effective_date` e `source` são opcionais. `source` identifica a natureza editorial da informação por chave controlada ou referência documentada, não substitui causalidade.

Existem três usos distintos:

1. **valor de referência:** `resource.reference_value` ou `item.reference_value`; é uma referência editorial, não uma cotação atual;
2. **preço inicial local:** condição inicial registrada no assentamento, com `settlement_id` coerente com o arquivo;
3. **preço atual da simulação:** valor mutável calculado e armazenado somente no estado futuro.

Fórmulas finais, limites de oscilação, impostos, escassez, inflação e conversões atuais são decisões adiadas.

## 7. Faixa

Estrutura compartilhada:

```yaml
range:
  minimum: null
  maximum: null
  unit_key: null
```

`minimum` e `maximum` são numéricos ou `null`; quando ambos forem conhecidos, `minimum` não pode superar `maximum`. `unit_key` precisa ser compatível com a grandeza representada. Zero não significa desconhecido. A faixa descreve limites editoriais, não uma distribuição probabilística e não substitui quantidade ou taxa.

## 8. Modificador

Estrutura compartilhada:

```yaml
modifier:
  modifier_key: null
  operation: null
  value: null
  condition_keys: []
  notes: null
```

`modifier_key` é estável dentro do contexto que o declara. `operation` usa uma chave controlada e possui a seguinte semântica conceitual:

| Operação | Significado editorial |
|---|---|
| `add` | acrescentar `value` ao valor contextual |
| `subtract` | subtrair `value` do valor contextual |
| `multiply` | multiplicar o valor contextual por `value` |
| `divide` | dividir o valor contextual por `value` |
| `set` | substituir o valor contextual por `value` |
| `minimum` | impedir resultado inferior a `value` |
| `maximum` | impedir resultado superior a `value` |

Essas operações são apenas vocabulário editorial nesta fase. `value` é numérico ou `null`, condições são explícitas e divisão por zero é inválida. Ordem de aplicação, composição, precedência, arredondamento e implementação são decisões adiadas.

## 9. Fluxo de produção

Cada fluxo usa a estrutura:

```yaml
- flow_id: null
  resource_id: null
  item_id: null
  quantity:
    value: null
    unit_key: null
  period_key: null
  required_profession_ids: []
  required_location_type_keys: []
  required_item_ids: []
  input_refs: []
  output_refs: []
  condition_keys: []
  waste_outputs: []
  notes: null
```

`flow_id` é estável e único dentro do arquivo; não é uma entidade global. Exatamente um entre `resource_id` e `item_id` deve ser preenchido. `input_refs` e `output_refs` são listas de strings que apontam para outros `flow_id` irmãos do mesmo arquivo quando for necessário relacionar etapas; não contêm fluxos aninhados. `waste_outputs` usa entradas com exatamente um `resource_id` ou `item_id`, `quantity` e `notes`. Requisitos usam IDs completos ou chaves controladas conforme o campo.

Um fluxo de produção descreve capacidade, método ou relação inicial permitida. Produção atual, trabalhadores disponíveis, rendimento efetivo e insumos reservados pertencem ao estado futuro. Este contrato não cria receitas reais.

## 10. Fluxo de consumo

Fluxos de consumo usam a mesma estrutura do fluxo de produção e as mesmas regras de identidade, quantidade, período, requisitos, referências, condições e resíduos. A diferença é semântica: o alvo principal é consumido ou demandado pelo processo descrito. Consumo atual, demanda efetiva, substituições e escassez pertencem ao estado futuro.

Um mesmo método pode relacionar fluxos por `input_refs` e `output_refs`, mas cada material continua declarado em uma entrada própria. Quantidade por período não é preço e não contém moeda.

## 11. Estoque inicial

Estrutura compartilhada:

```yaml
- resource_id: null
  item_id: null
  quantity:
    value: null
    unit_key: null
  quality_key: null
  storage_location_id: null
  reserved_quantity:
    value: null
    unit_key: null
  notes: null
```

Exatamente um entre `resource_id` e `item_id` deve ser preenchido. `storage_location_id` é opcional e usa um ID `location.*`. `reserved_quantity` é opcional, não negativa, usa unidade compatível e não pode superar `quantity` quando ambos os valores forem conhecidos. Para item não agregável, o estoque inicial só pode representar uma contagem de instâncias que serão materializadas no estado futuro; propriedade, condição e localização de cada cópia não pertencem à definição do item.

## 12. `resource`

**Finalidade.** Recurso representa algo fungível, mensurável, armazenável ou consumível e tratado economicamente por quantidade. Categorias conceituais mencionadas no GDD servem apenas para explicar o domínio e não constituem arquivos ou conteúdo real.

| Aspecto | Regra |
|---|---|
| Formato | Markdown com front matter YAML |
| Diretório futuro | `content/worlds/eldrath/resources/{slug}.md` |
| Prefixo e arquivo | `resource.{slug}`; arquivo `{slug}.md` |
| Dependências | contrato comum; unidades do mundo; economia; geografia, profissões, itens, leis e magia quando existirem |

**Campos.** Além dos campos comuns: `resource_category_key`, `base_unit_key`, `fungible`, `renewable`, `perishable`, `magical`, `storage_requirements`, `quality_keys`, `extraction_methods`, `production_methods`, `consumption_uses`, `legal_status_key`, `hazard_keys`, `reference_value` e `references`.

`base_unit_key` aponta para `world.unit_definitions`. `fungible` deve ser `true` para uma entidade modelada como recurso; diferenças materiais que impeçam fungibilidade exigem `quality_keys` ou definições distintas. Os booleanos são valores reais, nunca substitutos de desconhecido.

Cada entrada de `storage_requirements` permite `condition_keys`, `maximum_duration` como quantidade de tempo, `required_location_type_keys`, `loss_rate` no contrato de taxa, `hazard_keys` e `notes`. Recurso não perecível pode usar `maximum_duration: null` e `loss_rate: null` quando esses dados não se aplicarem.

Cada entrada de `extraction_methods` ou `production_methods` permite `method_id` estável no arquivo, `method_type_key`, `required_profession_ids`, `required_location_type_keys`, `required_item_ids`, `inputs`, `outputs`, `duration` como quantidade de tempo, `condition_keys`, `risk_keys` e `notes`. `inputs` e `outputs` usam fluxos compartilhados; métodos não registram atividade atual. `consumption_uses` usa `use_key`, fluxos de consumo, requisitos, condições e notas.

`consumption_uses` possui `use_id` estável no arquivo, `use_key`, `consumption_flows`, `required_profession_ids`, `required_location_type_keys`, `required_item_ids`, `condition_keys` e `notes`. `consumption_flows` contém fluxos irmãos completos; suas referências internas continuam sendo apenas strings de `flow_id`.

`reference_value` usa o contrato de preço e nunca é preço atual. `legal_status_key`, categorias, qualidades, condições, riscos e perigos são chaves controladas futuras.

**Corpo Markdown.** `Visão geral`, `Natureza`, `Obtenção`, `Processamento`, `Usos`, `Armazenamento`, `Riscos`, `Valor econômico`, `Relação com magia`, `Legalidade`, `História` e `Observações editoriais`.

**Proibições.** Recurso não registra estoque ou preço atual, nem lista todos os assentamentos que o possuem. Presença regional/local pertence aos arquivos geográficos. Produtores e consumidores atuais são derivados. Item único, moeda e artefato não são recursos.

## 13. `profession`

**Finalidade.** Profissão é uma definição de atividade social e econômica, não um cargo ocupado, uma vaga ou uma pessoa.

| Aspecto | Regra |
|---|---|
| Formato | Markdown com front matter YAML |
| Diretório futuro | `content/worlds/eldrath/professions/{slug}.md` |
| Prefixo e arquivo | `profession.{slug}`; arquivo `{slug}.md` |
| Dependências | contrato comum; competências, atributos, recursos, itens, assentamentos, instituições, facções, leis e magia quando existirem |

**Campos.** Além dos campos comuns: `profession_category_key`, `required_skill_keys`, `recommended_attribute_keys`, `training_paths`, `rank_keys`, `typical_tasks`, `production_profiles`, `required_item_ids`, `consumed_resource_ids`, `produced_resource_ids`, `produced_item_ids`, `workplace_type_keys`, `institution_ids`, `faction_ids`, `legal_requirements`, `magical_requirements`, `risks`, `social_status`, `income_model` e `references`.

`rank_keys` usa somente os estágios aplicáveis entre `apprentice`, `worker`, `specialist`, `master`, `leader` e `retired`. A ordem conceitual vem do GDD; uma profissão não precisa usar todos os estágios. Esses ranks descrevem progressão profissional e nunca substituem `content_status`.

Cada `training_paths` usa `path_id`, `path_type_key`, `entry_requirement_keys`, `required_profession_ids`, `institution_ids`, `duration` como quantidade de tempo, `applicable_rank_keys`, `condition_keys` e `notes`. `typical_tasks` usa `task_key`, `applicable_rank_keys`, `required_skill_keys`, `required_item_ids`, `condition_keys`, `duration` e `notes`.

Cada `production_profiles` usa `profile_id`, `applicable_rank_keys`, `production_flows`, `consumption_flows`, `condition_keys`, `modifiers` e `notes`; fluxos e modificadores seguem os contratos compartilhados. As listas resumidas `consumed_resource_ids`, `produced_resource_ids` e `produced_item_ids` declaram capacidades da definição e precisam concordar com os perfis quando ambos forem usados.

`legal_requirements` permite `requirement_key`, `jurisdiction_id`, `law_id`, `license_key`, `issuing_authority_id`, `applicable_rank_keys`, `condition_keys` e `notes`. `magical_requirements` permite `requirement_key`, `required_school_ids`, `required_spell_ids`, `required_affinity_keys`, `applicable_rank_keys`, `condition_keys` e `notes`. Cada entrada de `risks` usa `risk_key`, `applicable_rank_keys`, `condition_keys` e `notes`. `social_status` usa `status_key`, `variation_keys`, `condition_keys` e `notes`; descreve classificação e variação social estáveis, não a reputação de um NPC.

`income_model` permite `model_keys`, `payment_basis_key`, `reference_compensation` pelo contrato de preço, `condition_keys` e `notes`. A referência é editorial; salário atual, renda efetiva, riqueza e contratos de trabalho pertencem ao estado da simulação.

**Corpo Markdown.** `Visão geral`, `Função social`, `Responsabilidades`, `Formação`, `Progressão`, `Tarefas`, `Ferramentas`, `Recursos`, `Produção`, `Riscos`, `Relação com magia`, `Instituições`, `Prestígio` e `Observações editoriais`.

**Proibições.** NPCs e titulares atuais não são listados. Vagas pertencem ao estado do assentamento; competência atual pertence ao NPC; profissão não concede personalidade. Licença ou filiação podem ser requisitos explícitos. Produção usa os contratos compartilhados.

## 14. `item`

**Finalidade.** Item representa a definição de um objeto discreto, carregável, armazenável ou possuído, produzido ou adquirido, potencialmente durável e capaz de possuir instâncias futuras. O arquivo define o tipo, não cada cópia existente.

| Aspecto | Regra |
|---|---|
| Formato | Markdown com front matter YAML |
| Diretório futuro | `content/worlds/eldrath/items/{slug}.md` |
| Prefixo e arquivo | `item.{slug}`; arquivo `{slug}.md` |
| Dependências | contrato comum; unidades, recursos, profissões, economia, leis e magia quando existirem |

**Campos.** Além dos campos comuns: `item_category_key`, `stackable`, `unique_definition`, `provenance_mode`, `base_unit_key`, `default_stack_limit`, `durability`, `quality_keys`, `resource_composition`, `production_methods`, `required_profession_ids`, `usage_keys`, `legal_status_key`, `magical`, `artifact_id`, `reference_value`, `storage_requirements` e `references`.

`provenance_mode` aceita somente `none`, `optional` ou `required`. Itens comuns podem não registrar proveniência; definições únicas ou historicamente relevantes podem exigi-la. `base_unit_key` aponta para unidade compatível do mundo. `default_stack_limit` usa quantidade e só se aplica a itens agregáveis. `unique_definition: true` exige `stackable: false` e ausência de limite de pilha; a proveniência pode ser `optional` ou `required` conforme a relevância documentada.

`durability` permite `enabled`, `maximum`, `degradation_keys`, `repair_profession_ids`, `repair_resource_ids` e `notes`. `maximum` é numérico ou `null`, não negativo quando conhecido, e só se aplica quando `enabled: true`; a unidade/escala de durabilidade permanece adiada. Não há número real neste contrato.

Cada entrada de `resource_composition` usa `resource_id`, `quantity`, `quality_key`, `condition_keys` e `notes`. `production_methods` usa a mesma estrutura de método definida para recurso, com entradas e saídas por fluxo. `storage_requirements` segue o contrato de recurso. `reference_value` segue o contrato de preço e não é preço atual.

`artifact_id` é opcional e só aparece quando existe relação explícita com uma futura entidade `artifact.*`. Item mágico comum pode usar `magical: true`; um objeto mágico relevante, único ou historicamente importante usa uma entidade de artefato e não duplica no item sua origem, poderes, riscos ou história detalhados.

**Corpo Markdown.** `Visão geral`, `Função`, `Materiais`, `Produção`, `Uso`, `Durabilidade`, `Reparo`, `Qualidade`, `Armazenamento`, `Legalidade`, `Propriedades mágicas`, `Relação com artefatos`, `História` e `Observações editoriais`.

**Agregação e persistência.** `stackable: true` permite agregar somente cópias compatíveis em item, qualidade, condição, proveniência e modificadores. A agregação não transforma o item em recurso nem elimina futuras instâncias. Itens não agregáveis, definições únicas e cópias cuja proveniência seja obrigatória exigirão instâncias persistentes no estado.

Uma futura instância poderá registrar `instance_id`, `item_id`, proprietário, localização, quantidade, condição, durabilidade, proveniência e modificadores. Esse registro será parte do estado da simulação; não há schema executável nem template de instância nesta fase.

**Proibições.** Item não tem proprietário, localização ou quantidade atual. Inventários futuros guardam instâncias. Recursos fungíveis não devem virar itens sem necessidade. Poderes detalhados de artefato não são duplicados.

## 15. Relação com `settlement`

O assentamento registra relações econômicas iniciais locais por IDs, nunca cópias das definições. `production` e `consumption` usam fluxos compartilhados; `trade` usa quantidade, período, direção, contraparte e preço inicial opcional; `initial_stocks` usa o contrato de estoque inicial; `initial_prices` associa exatamente um `resource_id` ou `item_id` ao contrato de preço.

Capacidade, infraestrutura e relações iniciais são conteúdo. Produção, consumo, estoque, preço, salário, riqueza, escassez e vagas atuais pertencem ao estado futuro. Presença local não deve ser duplicada no arquivo de recurso ou item.

## 16. Relação com `route`

Rotas conectam lugares e podem carregar comércio agregado futuramente. `distance` e `base_travel_time` usam `{ value, unit_key }`; `toll.money` usa o contrato monetário. Capacidade e condição iniciais podem iniciar o estado, mas carga, tráfego, risco, controle e pedágio atuais pertencem à simulação. Uma rota não repete definições de unidade, moeda, recurso ou item.

## 17. Relação com `kingdom`

Moedas são definições internas de `kingdom.yaml`, nunca entidades ou recursos. `primary_currency_key` aponta para uma entrada de `currencies`. Cada moeda declara `key`, `name`, `symbol`, `subdivisions`, `exchange_reference` opcional, `legal_tender` e `notes`. Cada subdivisão usa `key`, `name`, `symbol`, `conversion_factor` e `notes`; a chave é única dentro da moeda e o fator positivo expressa uma relação editorial estável com a unidade principal. `exchange_reference`, quando usado, possui `reference_currency_key`, `ratio`, `effective_date`, `source` e `notes`; ele documenta somente uma relação inicial ou de referência, nunca câmbio atual. Outros arquivos usam somente `currency_key`.

O tesouro inicial usa `money`. Nome e símbolo podem mudar sem alterar `key`. Relações monetárias iniciais podem ser documentadas futuramente; cotações atuais, inflação, dívida e riqueza atual permanecem no estado.

## 18. Relação com `world`

`world.yaml` define `unit_system` e `unit_definitions`. Cada unidade registra `key`, `quantity_type`, `name`, `symbol`, `base_unit_key`, `conversion_factor` e `notes`. Tipos conceituais possíveis são `mass`, `volume`, `length`, `time`, `count` e `area`; este documento não cria unidades concretas.

`base_unit_key` aponta para uma entrada compatível do mesmo sistema e do mesmo `quantity_type`. A unidade-base usa `base_unit_key: null` e `conversion_factor: null`; unidades derivadas apontam diretamente para a unidade-base e usam fator numérico positivo quando conhecido. Ciclos são proibidos. Um fator de conversão não é taxa econômica. Recursos, itens, rotas e assentamentos usam somente `unit_key` e não repetem definições completas. `period_key` é vocabulário temporal de recorrência e não substitui uma unidade de tempo.

## 19. Relação futura com `artifact`

Artefato pertence ao sistema mágico e representa um objeto mágico relevante, único ou historicamente importante, com origem, poderes, riscos e história próprios. Ele poderá referenciar uma definição `item.*` como base. A relação não reduz o artefato a item comum e não transfere seus poderes detalhados para o item.

O schema completo de `artifact` permanece adiado. Até sua criação, `artifact_id` em item fica `null` e nenhuma referência inexistente pode chegar a conteúdo `approved`.

## 20. Invariantes

- `schema_version` é sempre a string `"1.0.0"` nestes contratos.
- IDs de entidade usam os prefixos `resource.`, `profession.` e `item.` e o arquivo usa apenas o slug.
- Exatamente um entre `resource_id` e `item_id` é preenchido em fluxo, estoque, preço local ou saída de resíduo.
- `currency_key` resolve dentro do reino aplicável e é a única forma de referência monetária.
- `unit_key` resolve em `world.unit_definitions` e é compatível com a grandeza.
- Quantidade física e estoque não são negativos; reserva não excede total conhecido.
- `minimum` não supera `maximum`; `quantity_basis` conhecida é positiva.
- Preço atual, estoque atual, produção atual, consumo atual, salário atual, riqueza atual e tráfego atual nunca ficam em conteúdo estático.
- Recurso é fungível e quantitativo; item é uma definição discreta; artefato é entidade mágica relevante; instância pertence ao estado.
- Moeda não é recurso, item ou entidade independente nesta versão.
- Definição de item não tem proprietário nem localização atual; profissão não tem titulares atuais.
- Intervenção material usa `item_instance` ou quantidade atual de recurso no estado; nunca move nem reescreve a definição estática.
- Referências de conteúdo `approved` existem, placeholders foram removidos e prosa não contradiz dados.

## 21. Validação manual

Antes de encaminhar um arquivo para revisão, conferir:

- caminho, prefixo, slug, campos comuns e versão;
- tipos, `null`, listas vazias, booleanos e ausência de string vazia;
- compatibilidade de `unit_key` e resolução de `currency_key`;
- exclusividade entre `resource_id` e `item_id`;
- unicidade de IDs locais de métodos, fluxos, perfis, caminhos e requisitos;
- não negatividade e coerência de reservas, faixas e limites;
- referências resolvidas e categorias corretas;
- separação entre valor de referência, preço inicial local e preço atual;
- ausência de estado atual em conteúdo;
- ausência de intervenções concretas, percepções ou histórico de campanha em conteúdo estático;
- uso de `item_instance`, e não da definição `item`, como futuro alvo de movimentação;
- coerência entre listas resumidas e fluxos detalhados;
- regras de agregação, unicidade, proveniência, durabilidade e relação com artefato;
- corpo Markdown completo e coerente;
- ausência de placeholders em conteúdo `approved`;
- ausência de entidades, moedas, unidades, receitas, preços, salários ou quantidades inventadas apenas para preencher campos.

## 22. Decisões adiadas

Permanecem para fases posteriores: moedas e unidades reais de Eldrath; vocabulários de categorias, períodos, qualidade, legalidade, risco, perigo, condições, tarefas, métodos, status e renda; valores, quantidades, preços, salários, estoques e produção reais; fórmulas de preço; conversões e câmbio atuais; impostos, inflação, dívida e contratos; regras de arredondamento; receitas; simulação econômica; schema de instância de item; schema completo de artefato; validação executável, banco de dados e código.
