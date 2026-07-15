# Templates editoriais de Eldrath

Esta pasta contém modelos para autoria consistente; ela não contém conteúdo real e deverá ser obrigatoriamente excluída pelo futuro carregador de conteúdo.

Os templates usam nomes em `snake_case` e descrevem sua finalidade, por exemplo `base_entity.md` e, quando autorizados, `npc.md` ou `spell.md`. Placeholders usam a forma explícita `{{nome_do_valor}}`. Eles orientam a cópia para um arquivo de trabalho, mas nunca são dados e não podem chegar a um arquivo com `content_status: approved`.

[`base_entity.md`](base_entity.md) continua sendo a origem conceitual dos campos comuns definidos no [contrato editorial](../../../../docs/world/CONTENT_SCHEMA.md). Os templates especializados acrescentam somente os campos do [schema correspondente](../../../../docs/world/schemas/FOUNDATIONAL_ENTITIES.md); eles não são conteúdo real e não definem schemas por si só.

## Catálogo fundamental

| Template | Entidade | Formato | Destino futuro | Dependências | Estado |
|---|---|---|---|---|---|
| [`world.template.yaml`](world.template.yaml) | mundo | YAML puro | `../world.yaml` | contrato comum e entidades fundamentais | concluído |
| [`calendar.template.md`](calendar.template.md) | calendário | Markdown com front matter YAML | `../calendars/{slug}.md` | contrato comum e identidade do mundo | concluído |
| [`language.template.md`](language.template.md) | idioma | Markdown com front matter YAML | `../languages/{slug}.md` | contrato comum; culturas e regiões quando existirem | concluído |
| [`culture.template.md`](culture.template.md) | cultura | Markdown com front matter YAML | `../cultures/{slug}.md` | contrato comum; idiomas e regiões quando existirem | concluído |
| [`kingdom.template.yaml`](kingdom.template.yaml) | reino | YAML puro | `../kingdom.yaml` | contrato comum, mundo e entidades fundamentais relacionadas | concluído |

Copie somente o template da entidade que será autorizada, substitua seus placeholders antes da revisão e mantenha `null` e listas vazias conforme o contrato. Nenhum desses arquivos cria ou representa `world.yaml`, `kingdom.yaml` ou uma entidade real.

## Ordem recomendada

1. `world.template.yaml`;
2. `calendar.template.md`;
3. `language.template.md`;
4. `culture.template.md`;
5. `kingdom.template.yaml`.

Quando o contrato comum ou um schema especializado mudar de forma aprovada, os templates afetados deverão ser revisados antes de novos arquivos serem aprovados. O ciclo de revisão de um template é o mesmo do conteúdo: elaboração, revisão, aprovação explícita e eventual depreciação documentada.
