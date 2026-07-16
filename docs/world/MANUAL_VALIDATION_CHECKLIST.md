# Checklist de validação manual

## Uso

Use este checklist antes de mover qualquer conteúdo para `in_review` ou `approved`. Leia primeiro o [contrato comum](CONTENT_SCHEMA.md), o [registro de vocabulários](CONTROLLED_VOCABULARY.md) e o schema especializado da entidade. Marque somente itens verificados; “não aplicável” deve ser justificado nas notas editoriais da revisão.

## Arquivo

- [ ] O arquivo está no caminho canônico da categoria.
- [ ] O nome é previsível a partir do slug do ID, sem repetir o prefixo.
- [ ] A extensão é `.md` com front matter YAML ou `.yaml` somente quando o contrato permitir YAML puro.
- [ ] O front matter abre e fecha corretamente e forma um único mapa YAML válido.
- [ ] O corpo é Markdown válido, com títulos hierárquicos e cercas balanceadas.
- [ ] O arquivo usa UTF-8 e finais de linha consistentes.
- [ ] Não existem chaves YAML duplicadas, strings vazias proibidas ou tipos incompatíveis.
- [ ] `schema_version` existe, está entre aspas e corresponde ao contrato aplicável.
- [ ] `content_status` existe e usa `draft`, `in_review`, `approved` ou `deprecated`.

## Identidade

- [ ] O ID segue `tipo.nome_estavel`.
- [ ] O prefixo corresponde à entidade, à pasta e ao schema.
- [ ] O ID contém somente ASCII.
- [ ] O ID está em minúsculas.
- [ ] Palavras são separadas por underscore, sem espaços ou hífens.
- [ ] O ID não foi usado por outra entidade nem reciclado após remoção.
- [ ] Um nome visível, título, alias ou caminho não foi usado como referência permanente.
- [ ] IDs de conteúdo, IDs técnicos, subregistros, instâncias, eventos concretos, snapshots e ramificações não foram confundidos.

## Referências

- [ ] Todo destino obrigatório existe; destino ausente é tratado como erro.
- [ ] Cada destino tem prefixo e tipo compatíveis com o campo que o referencia.
- [ ] A relação está registrada na direção canônica definida pelo schema.
- [ ] Nenhuma lista inversa manual duplica uma consulta derivável.
- [ ] Não existe ciclo indevido de pais, dependências, causalidade ou pertencimento.
- [ ] Referências opcionais usam omissão, `null` ou `[]` com a semântica correta.
- [ ] IDs locais e referências a subregistros resolvem dentro do proprietário correto.
- [ ] Uma referência genérica em `references` não substitui um campo especializado obrigatório.

## Propriedade

- [ ] Dados estáticos pertencem ao arquivo autoral da entidade responsável.
- [ ] Estado atual e mudanças posteriores pertencem ao save e ao log de eventos.
- [ ] `initial_state` contém apenas condições iniciais autorizadas pelo schema.
- [ ] Fatos objetivos estão separados de percepções.
- [ ] Crenças e suspeitas estão separadas de conhecimento.
- [ ] Cada memória possui origem rastreável e versão percebida.
- [ ] Rumores preservam origem, versão e genealogia.
- [ ] Cada evento possui causa anterior ou classificação e fundamento explícitos de evento-raiz.
- [ ] Conflitos registram lados, interesses e possibilidades sem resultado ou vencedor predeterminado.
- [ ] Populações, grupos, hordas e forças são agregados quando não exigem indivíduos persistentes.
- [ ] Ataques e incursões concretos pertencem ao save e aos eventos, não a arquivos estáticos.
- [ ] Espécie usa `creature.*`; indivíduo persistente usa `npc.*`.
- [ ] Membros, ocupantes, liderança, emprego, inventário, propriedade, magia conhecida, reputação e relações estão no proprietário canônico.

## Lore

- [ ] A prosa explica ou contextualiza os dados, mas não substitui campos mecânicos.
- [ ] A prosa não contradiz o front matter, schemas, fatos aprovados ou documentos superiores.
- [ ] Datas, duração, causa e ordem dos acontecimentos são cronologicamente coerentes.
- [ ] Região, assentamento, local, rota, distância e acesso são geograficamente coerentes.
- [ ] Recursos, produção, consumo, comércio, profissão, item, moeda e disponibilidade são economicamente coerentes.
- [ ] Cultura, religião, facção, família, lei, autoridade e posição social permanecem distintos e coerentes.
- [ ] Escola, magia, ritual, efeito, artefato, custo, alcance, duração, risco e legalidade seguem o contrato mágico.
- [ ] Cada personagem percebe apenas o que suas condições, evidências e fontes permitem.
- [ ] Biografia, narração ou interface não concedem metaconhecimento.
- [ ] Rumor não foi tratado como fato; crença errada e memória imperfeita continuam possíveis.
- [ ] Uma intervenção altera o mundo por efeito e evidência sem revelar automaticamente o usuário.

## GitHub

- [ ] O modo derivado usa somente dados públicos e consentidos.
- [ ] Cada associação registra projeto de origem, métricas usadas e explicação.
- [ ] A fórmula, normalização, agrupamento, nomes, gerador e mapa possuem versões registradas.
- [ ] Os pesos-base da fórmula e do agrupamento somam 100% em cada conjunto.
- [ ] Nenhum código, script, workflow ou dependência externa é executado.
- [ ] Token, cabeçalhos, e-mail, identidades desnecessárias e segredos não entram no snapshot, conteúdo ou save.
- [ ] Nenhum contribuidor, proprietário ou nome de perfil é transformado automaticamente em NPC, governante ou entidade.
- [ ] Textos externos são tratados como dados não confiáveis, limitados e não executáveis.
- [ ] Projetos ausentes, insuficientes, excedentes, forks e arquivados seguem as regras do contrato sem duplicação ou descarte silencioso.
- [ ] Toda associação automática pode ser editada ou removida antes da confirmação.
- [ ] O snapshot confirmado e seu hash ficam congelados.
- [ ] Abrir, reiniciar, ramificar, simular ou reproduzir uma campanha não consulta novamente a fonte.
- [ ] O mapa possui alternativa textual equivalente.
- [ ] Velocidade de processamento não altera decisões, eventos, causalidade ou hash final para a mesma entrada simulada.

## Revisão final

- [ ] Todos os links locais resolvem e os caminhos citados existem.
- [ ] Quantidades existentes e metas canônicas foram conferidas separadamente.
- [ ] Não existem placeholders fora de `_templates/`; conteúdo `approved` não contém placeholder algum.
- [ ] `.gitkeep` existe somente em pasta-folha completamente vazia e foi removido quando entrou conteúdo real.
- [ ] O diff contém somente arquivos e mudanças autorizados pela tarefa.
- [ ] O estado editorial do arquivo corresponde ao nível real de revisão.
- [ ] O documento responsável por cada regra, vocabulário e quantidade está registrado.
- [ ] A última atualização e o motivo da mudança estão documentados quando aplicável.
- [ ] Não há campos órfãos, referências a campos removidos ou listas inversas concorrentes.
- [ ] Nenhuma entidade foi criada apenas para preencher pasta, tela, tabela ou contagem.
- [ ] Toda decisão ainda adiada possui proprietário e fase prevista e não impede a autoria atual.
- [ ] A revisão preserva conteúdo aprovado e não antecipa fase futura.
