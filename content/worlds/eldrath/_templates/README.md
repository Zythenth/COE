# Templates editoriais de Eldrath

Esta pasta contém modelos para autoria consistente; ela não contém conteúdo real e deverá ser obrigatoriamente excluída pelo futuro carregador de conteúdo.

Os templates usam nomes em `snake_case` e descrevem sua finalidade, por exemplo `base_entity.md` e, quando autorizados, `npc.md` ou `spell.md`. Placeholders usam a forma explícita `{{nome_do_valor}}`. Eles orientam a cópia para um arquivo de trabalho, mas nunca são dados e não podem chegar a um arquivo com `content_status: approved`.

[`base_entity.md`](base_entity.md) é a base comum dos campos definidos no [contrato editorial](../../../../docs/world/CONTENT_SCHEMA.md). Um template especializado futuro deverá partir dela e acrescentar apenas os campos documentados para sua categoria; ele não é substituído por conteúdo real e não define schema especializado por si só.

Quando o contrato comum ou um schema especializado mudar de forma aprovada, os templates afetados deverão ser revisados antes de novos arquivos serem aprovados. O ciclo de revisão de um template é o mesmo do conteúdo: elaboração, revisão, aprovação explícita e eventual depreciação documentada. Nenhum template especializado é criado nesta tarefa.
