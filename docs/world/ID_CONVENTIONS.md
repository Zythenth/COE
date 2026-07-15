# Convenções iniciais de IDs

Este documento organiza somente as regras já estabelecidas em `Base/GDD.md`. Convenções definitivas, schemas e validadores pertencem à Fase 1.

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
- usar nomes de arquivo previsíveis e coerentes com o ID;
- tratar qualquer referência ausente como erro;
- não reutilizar IDs de entidades removidas;
- nunca usar nomes visíveis como chave permanente.

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
