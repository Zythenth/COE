# Convenções de IDs

Este documento resume as regras de ID aplicáveis ao contrato comum da Fase 1. A definição completa de formato de arquivo, referências e semântica está em [`CONTENT_SCHEMA.md`](CONTENT_SCHEMA.md); `Base/GDD.md` continua sendo a fonte canônica.

## Formato

Todo ID de conteúdo segue o padrão:

```text
tipo.nome_estavel
```

Regras obrigatórias:

- usar letras minúsculas;
- usar somente caracteres ASCII;
- separar palavras com underscore (`_`);
- começar com um prefixo correspondente ao tipo da entidade;
- usar IDs, e não nomes visíveis, em referências entre entidades;
- nunca reciclar um ID removido;
- permitir que o nome visível mude sem quebrar referências;
- fazer cada ID representar uma única entidade;
- tratar qualquer referência ausente como erro;
- não reutilizar IDs de entidades removidas;
- nunca usar nomes visíveis como chave permanente.

## ID e nome de arquivo

Para entidades persistentes, a pasta determina a categoria, o front matter contém o ID completo e o arquivo usa somente o slug estável após o primeiro ponto. O prefixo não é repetido no arquivo.

| ID | Caminho correto | Caminho incorreto |
|---|---|---|
| `npc.lysandra_vale` | `npcs/lysandra_vale.md` | `npcs/npc.lysandra_vale.md` |
| `spell.purifying_light` | `magic/spells/purifying_light.md` | `magic/spells/spell_purifying_light.md` |
| `faction.order_of_dawn_healers` | `factions/order_of_dawn_healers.md` | `factions/Ordem_das_Curandeiras.md` |

Manifestos, índices, READMEs e arquivos em `_templates/` são exceções explícitas: eles não representam uma entidade persistente e não recebem nome derivado de ID.

Uma mudança cosmética de nome visível nunca autoriza renomear o ID ou o arquivo. Se uma mudança de ID for legitimamente necessária, ela exigirá migração documentada futura. Conteúdo `deprecated` mantém seu ID reservado; removê-lo do uso ativo não permite reciclá-lo.

## Exemplos válidos

| ID | Motivo |
|---|---|
| `npc.lysandra_vale` | Prefixo de tipo, minúsculas, ASCII e palavras separadas por underscore. |
| `faction.order_of_dawn_healers` | Identifica de forma estável uma facção sem depender do nome visível. |
| `settlement.aurenfall` | Possui tipo explícito e nome estável previsível. |
| `spell.purifying_light` | Permite que magias sejam referenciadas pelo ID mesmo se o título mudar. |
| `event.seed.plague_of_white_ash` | Usa segmentos de tipo para identificar um evento-semente e mantém o nome estável em minúsculas. |

## Exemplos inválidos

| ID inválido | Problema |
|---|---|
| `NPC.LysandraVale` | Usa maiúsculas, não separa palavras com underscore e não segue o prefixo normalizado. |
| `npc.lysandra vale` | Contém espaço; palavras devem ser separadas por underscore. |
| `npc.lysândra_vale` | Contém caractere fora de ASCII. |
| `lysandra_vale` | Não possui prefixo obrigatório de tipo. |
| `faction.order-of-dawn` | Usa hífens em vez de underscore entre palavras. |
| `Aurenfall` | É um nome visível, não uma chave permanente com tipo explícito. |
| `spell.purifying_light` para duas magias | Um mesmo ID não pode representar mais de uma entidade. |
| `npc.lysandra_vale` reutilizado após remoção | IDs removidos não podem ser reciclados, mesmo que o nome volte a ser usado. |

Uma referência como `teacher: faction.order_of_dawn_healers` é válida apenas se a entidade referenciada existir. Se estiver ausente, a autoria ou validação deve acusar erro; não se deve substituir o ID pelo nome da facção.

Este documento não define campos, schemas completos, expressões regulares nem implementação de validação.
