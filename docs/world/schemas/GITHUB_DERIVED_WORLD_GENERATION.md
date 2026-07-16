# Geração de mundo derivada do GitHub — contrato conceitual

**Versão do contrato:** 1.0.0

**Estado:** concluído documentalmente; implementação não iniciada.

Este documento define a geração opcional de um mundo fantástico a partir de dados públicos de projetos de um perfil do GitHub. É um contrato conceitual da Fase 1: não é schema executável, integração, cliente de API, algoritmo implementado, save, mapa visual, conteúdo real ou substituto de Eldrath.

## 1. Objetivo

Permitir que o usuário transforme uma seleção revisável de projetos públicos em uma proposta fantástica de regiões, assentamentos, locais, instituições e rotas. O processo deve ser transparente, determinístico, explicável, editável e independente de IA generativa.

O GitHub é somente uma fonte opcional para preparar condições iniciais. Depois da confirmação, a campanha é uma simulação local completa, não um visualizador de repositórios e não uma representação do valor pessoal ou profissional do usuário.

## 2. Limites

- Não há consulta real, perfil real, token, OAuth, scraping, clone, execução ou implementação nesta fase.
- O MVP considera somente dados públicos de um perfil informado com consentimento.
- Repositórios privados, organizações, múltiplos perfis e sincronização ficam fora do MVP.
- Nenhum código, workflow, script ou dependência de repositório é executado.
- Nenhum texto externo é tratado como regra, prompt, instrução do sistema ou contrato canônico.
- Nenhum contribuidor real vira NPC, personagem, governante ou entidade do mundo.
- O modo derivado não substitui Eldrath, a criação manual nem os contratos editoriais existentes.
- IA generativa não é necessária para cálculo, agrupamento, nomes, mapa ou criação do mundo.

## 3. Modos de criação

O produto possui três modos conceituais:

1. **Eldrath canônico:** carrega o cenário oficial construído e aprovado nas fases de conteúdo.
2. **Criação manual:** permite configurar um mundo por formulários e ferramentas estruturados.
3. **Mundo derivado do GitHub:** usa um snapshot revisado de projetos públicos para propor um mundo editável.

Os três modos chegam ao mesmo limite de inicialização: referências validadas, pacote inicial imutável, semente definida, checkpoint inicial criado e campanha ainda pausada.

## 4. Fluxo

O fluxo futuro obrigatório é:

1. escolher “Criar mundo pelo GitHub”;
2. informar URL pública de perfil ou nome de usuário público;
3. validar o formato;
4. consentir com a consulta e ver quais dados poderão ser usados;
5. consultar a API oficial do GitHub;
6. criar snapshot dos dados recebidos;
7. listar todos os repositórios encontrados no escopo;
8. permitir incluir ou excluir projetos;
9. mostrar métricas originais e normalizadas;
10. calcular e explicar a relevância;
11. agrupar projetos;
12. propor até quatro regiões;
13. propor capital, cidades e vilas;
14. propor locais e instituições;
15. propor rotas;
16. criar mapa preliminar;
17. explicar cada associação e cada exclusão;
18. permitir alterações manuais;
19. exigir confirmação explícita;
20. validar IDs, referências e integridade;
21. criar o mundo inicial;
22. criar o checkpoint inicial;
23. iniciar a campanha pausada.

Nenhum mundo ou campanha começa antes da prévia, da edição permitida e da confirmação.

## 5. Validação de URL

Entradas aceitas conceitualmente:

- um nome de usuário público em formato válido;
- uma URL HTTPS cujo host seja GitHub e cujo caminho identifique somente um perfil público.

A normalização remove espaços externos e barra final, separa o identificador da forma exibida e registra a URL normalizada. Caminhos de repositório, issues, organizações, buscas, fragments, query strings, esquemas não seguros, outros hosts, entrada vazia ou caracteres incompatíveis são rejeitados com erro específico.

A validação local confirma apenas formato. Existência, disponibilidade e resposta do perfil só podem ser verificadas futuramente pela API oficial. A forma canônica retornada pela fonte fica registrada sem depender da capitalização digitada.

## 6. Dados públicos

O contrato pode considerar:

- nome e nome completo do repositório;
- descrição;
- tópicos;
- linguagens e proporções disponíveis;
- tamanho relativo;
- data de criação;
- data de atualização;
- sinal de atividade recente;
- estrelas;
- forks;
- releases;
- quantidade de contribuidores, quando disponível sem expor identidades;
- estado arquivado;
- indicação de fork;
- indicação de template;
- propriedade do repositório.

README e outros textos só podem contribuir para uma categorização futura explicitamente limitada e tratada como não confiável. Detalhes finais de endpoints, paginação, autenticação opcional e campos da API permanecem adiados.

## 7. Snapshot

O snapshot conceitual contém:

- identificador estável;
- versão do schema do snapshot;
- perfil informado;
- identificador público normalizado;
- URL normalizada;
- data e hora da coleta;
- campos solicitados e campos efetivamente utilizados;
- repositórios encontrados;
- projetos incluídos e excluídos, com motivos;
- métricas originais;
- métricas normalizadas;
- versão da fórmula;
- pesos-base e pesos efetivos;
- pontuações e desempates;
- agrupamentos e versão do agrupador;
- associações automáticas;
- correções manuais;
- política de nomes;
- semente;
- versão do gerador;
- versão do layout do mapa;
- hash do snapshot;
- avisos e erros;
- configurações relevantes;
- origem e versão de eventual snapshot importado.

O hash usa serialização canônica dos campos que influenciam o resultado. Token, cabeçalhos de autenticação, cache transitório, logs técnicos e identidades de contribuidores não entram no snapshot.

Depois da criação, o snapshot fica congelado. Mudanças externas não alteram o mundo, o save, o mapa inicial ou o replay.

## 8. Normalização

Cada projeto incluído é analisado somente contra o conjunto incluído no mesmo snapshot. Métricas brutas permanecem disponíveis para auditoria.

Para contagens não negativas e assimétricas, como tamanho, estrelas, forks, releases e contribuidores:

1. ordenar os valores disponíveis;
2. obter o percentil 95 por posto mais próximo: posição teto de 0,95 vezes a quantidade;
3. limitar cada valor ao percentil 95;
4. aplicar logaritmo natural de um mais o valor;
5. combinar o valor logarítmico com a posição relativa média entre empates.

~~~text
log_norm(x) = ln(1 + min(x, P95)) / ln(1 + P95)
rank_norm(x) = (posto_medio_ascendente(x) - 1) / (n - 1)
count_norm(x) = 0,60 * log_norm(x) + 0,40 * rank_norm(x)
~~~

Quando há um único valor, `rank_norm` é 0,5. Quando todos os valores de uma submétrica são iguais, essa submétrica recebe 0,5 para todos e não cria diferença artificial. Essas regras especiais são aplicadas antes das fórmulas e evitam divisão por zero, inclusive quando o único valor ou todos os valores constantes são zero. Zero conhecido continua sendo zero como dado bruto; dado indisponível não é convertido em zero.

Recência combina decaimento limitado de 730 dias com posição relativa da data de atualização:

~~~text
recency_abs = max(0, 1 - dias_desde_atualizacao / 730)
activity_norm = 0,60 * recency_abs + 0,40 * rank_recencia
~~~

Contagens, datas e proporções são avaliadas com o instante congelado da coleta. Valores internos mantêm pelo menos seis casas decimais; a interface exibe duas sem arredondamento intermediário.

## 9. Fórmula

A fórmula padrão chama-se **github-relevance-v1.0.0**. Cada componente produz valor entre 0 e 1:

- atividade: recência absoluta e relativa;
- continuidade: duração ativa limitada e posição relativa;
- maturidade: idade saturada, continuidade e sinais estáveis disponíveis;
- tamanho relativo: tamanho normalizado no próprio perfil;
- variedade tecnológica: quantidade e distribuição de linguagens;
- releases: quantidade normalizada e presença de versões;
- colaboração: contribuidores e forks, quando disponíveis;
- reconhecimento externo: estrelas e forks com limite robusto;
- riqueza de tópicos: tópicos e presença de descrição;
- relação com outros projetos: conexões por linguagens, tópicos, tipo e relações estruturais.

A composição interna padrão é:

| Componente | Composição determinística |
|---|---|
| Atividade | activity_norm definido na seção 8 |
| Continuidade | count_norm dos dias entre criação e última atualização |
| Maturidade | 50% idade saturada em 730 dias + 25% presença de ao menos uma release + 25% continuidade |
| Tamanho relativo | count_norm do tamanho retornado pela fonte |
| Variedade tecnológica | 50% count_norm da quantidade de linguagens + 50% entropia normalizada das proporções de linguagens |
| Releases | count_norm da quantidade de releases |
| Colaboração | 70% count_norm de contribuidores + 30% count_norm de forks |
| Reconhecimento externo | 70% count_norm de estrelas + 30% count_norm de forks |
| Riqueza de tópicos | 80% count_norm da quantidade de tópicos + 20% presença de descrição não vazia |
| Relação com outros projetos | 70% count_norm do grau ponderado no grafo de similaridade + 30% presença de vínculo estrutural com projeto incluído |

Idade saturada é min(dias desde a criação / 730, 1). Presença usa 1 quando verdadeira e 0 quando falsa. A entropia de linguagens usa:

~~~text
H = - soma(p_linguagem * ln(p_linguagem)) / ln(quantidade_de_linguagens)
~~~

Para zero ou uma linguagem, H é 0. Se a fonte fornecer somente a lista, as linguagens recebem proporções iguais; se não fornecer nenhuma informação de linguagem, a submétrica fica indisponível.

O grafo de similaridade liga projetos incluídos pela mesma combinação versionada usada no agrupamento: linguagens 25%, tópicos 25%, tipo 15%, descrição categorizada 10%, faixa de atividade 10%, relações estruturais 10% e complementaridade declarada 5%. O grau ponderado é a soma dos pesos das conexões do projeto. Vínculo estrutural significa fork, template ou outra relação pública explicitamente retornada entre dois projetos incluídos; inferência por nome não conta.

~~~text
pontuacao = 100 * soma(peso_i * componente_i disponível)
                 / soma(peso_i disponível)
~~~

Uma submétrica ausente é removida e os pesos internos do componente são renormalizados. Se todo um componente estiver indisponível, seu peso é redistribuído proporcionalmente entre os componentes disponíveis e a interface mostra os pesos efetivos. Ausência não recebe punição silenciosa.

Se todos os componentes estiverem indisponíveis, a pontuação é `null`: o projeto permanece listado com a resposta incompleta explicada, não recebe ordenação automática e pode ser excluído, completado por nova consulta ou incluído manualmente antes da confirmação. Criação manual e Eldrath canônico continuam disponíveis. O sistema nunca divide por zero nem transforma ausência total em pontuação zero.

O cálculo não avalia inteligência, competência, moralidade, empregabilidade, valor humano, sucesso profissional ou qualidade pessoal. Ele apenas ordena projetos para distribuir referências em um mundo fictício.

## 10. Pesos

| Componente | Peso-base |
|---|---:|
| Atividade | 15% |
| Continuidade | 10% |
| Maturidade | 10% |
| Tamanho relativo | 10% |
| Variedade tecnológica | 10% |
| Releases | 10% |
| Colaboração | 10% |
| Reconhecimento externo | 10% |
| Riqueza de tópicos | 7% |
| Relação com outros projetos | 8% |
| **Total** | **100%** |

Estrelas e forks participam de componentes limitados e não controlam o total. Idade não é sinônimo de qualidade: projetos antigos não recebem inferioridade por inatividade, e projetos novos continuam elegíveis mesmo sem maturidade acumulada.

## 11. Desempates

A ordenação decrescente usa, nesta ordem:

1. pontuação total interna, antes da formatação;
2. projeto original e pertencente ao perfil, quando essa preferência estiver habilitada;
3. componente de maturidade;
4. data de criação mais antiga como data estável;
5. nome completo normalizado em ordem lexicográfica ascendente.

Persistindo igualdade absoluta, usa-se o identificador público estável do repositório. Sorteio não determinístico é proibido.

## 12. Seleção

Todos os projetos encontrados são listados antes do cálculo final. O usuário pode incluir ou excluir qualquer projeto elegível e recebe explicação para:

- seleção automática;
- exclusão automática por limite do MVP;
- exclusão manual;
- falta de dados;
- condição de fork, template ou arquivado;
- uso como assentamento ou influência secundária.

Alterar a seleção recalcula, na prévia, a normalização relativa, a pontuação, os agrupamentos e as propostas. A mudança fica registrada como correção manual no snapshot confirmado.

## 13. Regiões

Os projetos incluídos são agrupados em até quatro regiões. O número-alvo é o menor entre quatro e a quantidade de projetos incluídos; regiões adicionais necessárias ao formato do mundo podem ser completadas por dados agregados, conteúdo canônico autorizado ou criação manual.

A similaridade conceitual considera:

| Sinal | Peso de agrupamento |
|---|---:|
| Linguagens | 25% |
| Tópicos | 25% |
| Tipo de projeto | 15% |
| Descrição categorizada | 10% |
| Faixa de atividade | 10% |
| Relações estruturais | 10% |
| Complementaridade declarada | 5% |
| **Total** | **100%** |

O agrupador futuro precisa ser versionado, estável, explicável, editável e usar ordem canônica de projetos. Empates usam pontuação, nome completo normalizado e identificador estável. O mesmo projeto não pode aparecer em dois grupos sem associação manual explícita e visível; duplicação silenciosa é proibida.

## 14. Assentamentos

A proposta de referência usa:

| Posição de relevância | Proposta |
|---|---|
| 1 | capital |
| 2 a 4 | três cidades |
| 5 a 8 | quatro vilas |
| 9 em diante | locais, instituições, guildas, recursos, escolas, rotas ou história |

Cada assentamento registra projeto de origem, pontuação, métricas usadas, motivo da classificação, versão da fórmula e alterações manuais. O usuário pode substituir projeto, tipo, nome, região e associação antes de confirmar.

Relevância não define sozinha riqueza, moralidade, felicidade, segurança, prosperidade, qualidade ou valor dos habitantes.

## 15. Locais

Projetos não usados como assentamentos podem inspirar, sem obrigação:

- locais especiais;
- instituições;
- guildas;
- escolas;
- oficinas;
- arquivos;
- monumentos;
- recursos;
- características históricas;
- perigos temáticos não ofensivos.

Tópicos e linguagens influenciam somente temas, afinidades, estética, profissões e funções. Cada proposta aponta para a fonte e pode ser removida. Nenhuma associação cria entidade real antes da confirmação do mundo.

## 16. Rotas

Rotas podem ser propostas por:

- proximidade regional;
- similaridade;
- complementaridade;
- importância do assentamento;
- dependência temática;
- necessidade de manter o grafo conectado.

O gerador futuro primeiro garante uma conexão justificável entre todos os assentamentos alcançáveis e depois pode adicionar rotas secundárias dentro de um orçamento versionado. O custo conceitual combina distância proposta, baixa complementaridade e risco; empates usam IDs normalizados dos extremos.

O mapa não pode ficar desconectado sem justificativa registrada. Ilhas, portais ou isolamento deliberado exigem explicação e alternativa de acesso ou indicação explícita de inacessibilidade.

## 17. Mapa

O mapa mundial futuro é 2D, leve, navegável, consultável e derivado da geografia. Não é fonte canônica e não é necessário para compreender o mundo.

Pode mostrar regiões, capital, cidades, vilas, locais, rotas, perigos, conflitos, influência de facções, eventos, migrações, monstros, hordas, ataques e incursões. Não exige 3D, WebGL, sprites, combate visual, animação pesada ou renderização individual de NPCs.

As coordenadas iniciais são produzidas uma vez por snapshot, configuração, versão do layout e semente, validadas e congeladas no estado inicial. A interface lê essas coordenadas; não recalcula cidades a cada abertura. Camadas de campanha podem mudar sem mover a geografia-base.

Toda informação cartográfica possui alternativa em lista, tabela, relatório, timeline ou página de entidade. Com snapshot, fórmula, configuração, versões e semente iguais, o mapa inicial é igual.

## 18. Nomes

O usuário escolhe uma política:

1. manter o nome do repositório;
2. transformar o nome em variante fantástica;
3. gerar nome independente e preservar associação interna.

A transformação possui fallback determinístico por dicionários, prefixos, sufixos, idiomas, categorias e semente. IA generativa é opcional e nunca a única forma de nomear.

O nome do perfil não cria rei, NPC, divindade ou metaconhecimento e não precisa aparecer publicamente. Contribuidores reais nunca viram NPCs automaticamente.

## 19. Projetos insuficientes

Com menos de oito projetos elegíveis:

- nenhum projeto é duplicado;
- dados agregados podem completar características;
- o usuário pode completar manualmente;
- partes autorizadas de Eldrath podem ser usadas;
- assentamentos sem projeto direto ficam identificados como não associados.

Com nenhum projeto adequado, oferecer: tentar novamente, escolher outro perfil, usar criação manual, carregar Eldrath canônico ou importar snapshot anterior.

## 20. Projetos excedentes

Com mais de oito projetos:

- os oito primeiros são candidatos a assentamentos;
- os demais viram influências secundárias possíveis;
- busca e filtros continuam disponíveis;
- o usuário pode substituir qualquer selecionado;
- cada exclusão da camada principal recebe explicação;
- nenhum projeto é descartado silenciosamente.

O snapshot preserva todos os encontrados no escopo, incluídos ou excluídos, salvo apagamento explícito do snapshot.

## 21. Forks

Forks são identificados e não tratados como autoria original. Por padrão, não recebem preferência de desempate nem candidatura principal automática quando houver projeto original elegível, mas permanecem visíveis e podem ser incluídos explicitamente.

Quando incluídos, podem inspirar ramificações, enclaves, intercâmbio ou conexões. A associação é temática, removível e não afirma autoria, qualidade ou independência.

## 22. Arquivados

O estado arquivado não é penalidade moral, profissional ou automática de relevância. Projetos arquivados permanecem visíveis e podem ser incluídos ou excluídos.

Se o usuário autorizar, podem inspirar arquivos, monumentos, ruínas ou instituições históricas. Essa associação aparece na prévia, pode ser removida e nunca converte baixa atividade em decadência, pobreza ou fracasso.

## 23. Privacidade

- exigir consentimento antes de consultar;
- mostrar previamente os campos considerados;
- permitir excluir projetos antes da geração;
- usar somente dados públicos no MVP;
- não expor e-mail;
- não armazenar identidade de contribuidores quando uma contagem for suficiente;
- não transformar contribuidor em NPC;
- permitir apagar snapshot;
- não publicar mundo, snapshot ou campanha automaticamente;
- não criar associação com julgamento pessoal;
- não exigir que o nome do perfil apareça no mundo.

Apagar o snapshot de origem pode impedir auditoria completa de um mundo derivado; a interface deve explicar o impacto e oferecer exportação ou preservação local antes da ação.

## 24. Segurança

Na implementação futura:

- usar somente a API oficial do GitHub;
- não depender de scraping;
- não clonar automaticamente;
- não executar código, scripts ou workflows;
- não instalar dependências;
- não abrir conteúdo externo como instrução;
- não armazenar token em conteúdo, snapshot ou save;
- não registrar token em logs;
- limitar tamanho, paginação, tempo e quantidade de dados;
- validar entrada, resposta, tipos e limites;
- manter falhas externas fora da crônica diegética.

Repositórios privados, OAuth e organizações permanecem fora do MVP.

## 25. Conteúdo não confiável

Nome, descrição, tópicos, README e qualquer texto de repositório são dados externos não confiáveis. Eles:

- nunca alteram regras do sistema;
- nunca substituem este contrato;
- nunca instruem o agente, o motor ou a interface;
- nunca são executados;
- são tratados como texto, limitados e sanitizados;
- não podem inserir HTML ou script arbitrário;
- não podem revelar segredo local;
- não podem atravessar o limite entre apresentação e comando.

Categorização textual futura usa vocabulário limitado, versão conhecida e saída validada. IA generativa não é necessária e, se opcionalmente usada para apresentação, não participa do cálculo.

## 26. Funcionamento offline

Depois da confirmação:

- snapshot, mundo inicial, mapa-base, configurações e checkpoint ficam locais;
- abrir, salvar, reiniciar, ramificar, simular e reproduzir não consulta o GitHub;
- falha ou indisponibilidade do GitHub não afeta campanha criada;
- mudanças externas não alteram o mundo;
- atualização exige ação explícita;
- token não é necessário para continuar;
- o núcleo permanece completo sem internet e sem IA.

## 27. Determinismo

O resultado inicial depende somente de:

- snapshot congelado e seu hash;
- seleção confirmada;
- fórmula e pesos;
- versões do normalizador, agrupador, gerador, nomes e mapa;
- configurações;
- correções manuais;
- semente;
- ordem canônica dos projetos.

Todo fluxo pseudoaleatório é nomeado. Mudança cosmética de interface não altera cálculo, agrupamento, nomes, rotas ou posições. A mesma entrada completa produz o mesmo pacote inicial e o mesmo hash.

## 28. Edição

A prévia permite alterar seleção, associação, região, tipo de assentamento, local, instituição, rota, nome e política temática. Cada mudança manual registra valor automático anterior, valor confirmado, motivo opcional e ordem.

A edição não altera métricas originais. Se a seleção de projetos mudar, o cálculo relativo é refeito e explicado. Depois da confirmação, editar estrutura inicial exige nova campanha, checkpoint restaurado ou ramificação conforme o tipo de mudança.

## 29. Versionamento

Devem existir versões independentes para:

- schema do snapshot;
- fórmula de relevância;
- normalização;
- agrupamento;
- gerador de geografia;
- política de nomes;
- layout do mapa;
- pacote de conteúdo;
- motor e save.

Versão antiga não é reinterpretada silenciosamente. Mudança incompatível exige migração explícita ou nova importação. A versão da fórmula padrão deste contrato é github-relevance-v1.0.0.

## 30. Atualização

“Atualizar pelo GitHub” é uma ação explícita posterior, fora do fluxo comum de abrir ou reiniciar campanha. Ela cria novo snapshot, apresenta diff e nova prévia e nunca altera a linha ativa sem confirmação.

Uma nova importação cria outro mundo ou uma ramificação identificada. Sincronização automática, atualização periódica e mesclagem silenciosa ficam fora do MVP.

## 31. Erros

Erros distinguem, quando aplicável:

- entrada inválida;
- perfil não encontrado;
- perfil indisponível;
- limite de consulta;
- autorização ausente ou inválida;
- resposta incompleta;
- campo incompatível;
- nenhum repositório encontrado;
- nenhum projeto elegível;
- snapshot inválido;
- hash divergente;
- referência quebrada;
- falha de geração.

A interface preserva a entrada e a seleção já confirmada quando seguro, explica o impacto, permite tentar novamente e oferece criação manual ou Eldrath canônico. Erro externo não cria evento, rumor ou memória no mundo.

## 32. Saves

Todo save de mundo derivado registra:

- modo de criação;
- ID e hash do snapshot;
- versão da fórmula e do gerador;
- semente;
- hash do pacote inicial;
- ID do checkpoint inicial;
- configurações;
- campanha pai e ramificação;
- log ordenado de comandos;
- versões do motor e do conteúdo.

O snapshot de proveniência é separado do estado mutável. Eventos, relações, economia, ameaças e demais mudanças pertencem à campanha.

## 33. Checkpoints

O checkpoint inicial é criado depois da confirmação e validação do mundo e antes do primeiro tick. Ele contém data inicial, estado inicial completo, fila inicial, semente, posições dos fluxos pseudoaleatórios, configurações, mapa-base, pacote de conteúdo e snapshot de origem.

Checkpoints posteriores não substituem o inicial. Restauração valida hash, versões, referências e consistência antes de ativar a nova linha.

## 34. Ramificações

Uma ramificação preserva:

- campanha pai;
- checkpoint ou tick de origem;
- snapshot e hash de origem;
- comandos comuns até a separação;
- comandos divergentes;
- versões e configurações;
- relação administrativa entre linhas.

Nova importação, mudança estrutural, exploração de “e se” ou reinício podem criar ramificação. NPCs não conhecem ramificações ou linhas abandonadas.

## 35. Reinício

A opção **Voltar o mundo ao início** fica no menu de opções da campanha e:

1. pausa a simulação;
2. mostra a data atual e o checkpoint inicial;
3. explica o estado que será restaurado;
4. lista acontecimentos que sairão da linha ativa;
5. oferece arquivar a campanha atual;
6. oferece criar ramificação;
7. exige confirmação explícita;
8. restaura o checkpoint inicial;
9. valida o estado;
10. inicia a nova linha no começo e pausada.

Por padrão, a linha anterior é preservada. Excluir permanentemente é ação separada.

O reinício restaura data, mundo, NPCs, relações, inventários, economia, assentamentos, facções, ameaças, rumores iniciais, conflitos latentes, fila, semente, fluxo pseudoaleatório, configurações, mapa-base e snapshot do GitHub. Não faz nova consulta.

É operação administrativa: aparece no histórico administrativo, preserva origem e linha, permite replay e auditoria e não cria memória, conhecimento, rumor ou metaconhecimento nos NPCs.

## 36. Velocidade

Controles previstos:

- pausado;
- 1×;
- 2×;
- 5×;
- 10×;
- velocidade máxima segura;
- avançar um dia;
- avançar uma semana;
- avançar até uma data;
- avançar até o próximo evento relevante.

Velocidade altera somente ritmo de processamento, frequência de atualização visual, quantidade de ticks processados por tempo real e agrupamento de apresentação. Não altera regras, ordem, decisões, probabilidades, semente, causalidade, eventos ou estado final.

Com mesma semente, mesma sequência de comandos e mesma duração simulada, 1× e 10× produzem o mesmo hash de estado.

A velocidade máxima segura adapta o lote ao dispositivo, informa velocidade solicitada e efetiva, reduz atualizações visuais, diminui sob sobrecarga e nunca perde evento ou consequência.

Pausas automáticas configuráveis incluem morte importante, guerra, ataque a cidade, incursão, queda de governante, descoberta rara, colapso econômico, intervenção pendente e erro de integridade. O evento causador é resolvido e persistido antes da pausa; pausar não o altera.

O controle de velocidade fica visível durante a simulação e também no menu de opções. “Voltar o mundo ao início” permanece nas opções e exige confirmação.

## 37. Decisões adiadas

Ficam para as fases apropriadas:

- endpoints, paginação, quotas e autenticação técnica da API;
- formato executável do snapshot;
- algoritmo e limiares finais de categorização e agrupamento;
- vocabulários fantásticos e dicionários de nomes;
- gerador geográfico, layout, orçamento de rotas e representação cartográfica;
- formatos técnicos de save, checkpoint, ramificação e replay;
- UX, componentes, acessibilidade detalhada e design visual;
- política de atualização e migração;
- OAuth, privados, organizações e múltiplos perfis;
- sincronização e atualização periódica;
- análise semântica avançada;
- implementação, testes executáveis, banco, API, frontend e backend.

## 38. Critérios de aceitação

O contrato futuro é atendido somente quando:

1. URL ou nome público pode ser informado;
2. dados utilizados são mostrados;
3. projetos podem ser excluídos;
4. fórmula é reproduzível;
5. fórmula possui versão;
6. pesos-base somam 100%;
7. cada assentamento associado mostra o projeto de origem;
8. popularidade não é apresentada como valor pessoal;
9. prévia pode ser editada;
10. mesmo snapshot e semente geram o mesmo mundo;
11. posições do mapa são estáveis;
12. mapa possui alternativa textual;
13. campanha continua offline;
14. mudanças externas não alteram a campanha;
15. reinício não consulta o GitHub;
16. checkpoint inicial é restaurado;
17. campanha anterior pode ser preservada;
18. reinício não cria memória nos NPCs;
19. 1× e 10× geram o mesmo estado;
20. aceleração não perde eventos;
21. pausa não altera o evento;
22. código externo não é executado;
23. tokens não aparecem em conteúdo, snapshot, save ou logs;
24. contribuidores não viram NPCs automaticamente;
25. criação manual continua disponível;
26. Eldrath canônico continua disponível;
27. IA generativa continua opcional.

## 39. Checklist

Antes de aprovar uma futura especificação ou implementação:

- [ ] preservar os três modos de criação;
- [ ] exigir consentimento e prévia;
- [ ] usar apenas dados públicos no MVP;
- [ ] validar URL sem tratar formato como existência;
- [ ] listar incluídos, excluídos e motivos;
- [ ] mostrar métricas brutas, normalizadas, pesos e versão;
- [ ] confirmar pesos-base em 100%;
- [ ] aplicar normalização robusta e tratamento explícito de ausentes;
- [ ] aplicar desempates estáveis;
- [ ] registrar origem de regiões, assentamentos, locais e rotas;
- [ ] impedir duplicação silenciosa;
- [ ] permitir edição antes da confirmação;
- [ ] preservar mapa leve, estável e não canônico;
- [ ] oferecer alternativas textuais completas;
- [ ] congelar snapshot e checkpoint inicial;
- [ ] operar offline depois da criação;
- [ ] não consultar GitHub ao abrir, simular, reproduzir ou reiniciar;
- [ ] preservar campanha anterior por padrão no reinício;
- [ ] impedir metaconhecimento dos NPCs;
- [ ] provar equivalência entre velocidades;
- [ ] impedir perda de eventos na velocidade máxima segura;
- [ ] tratar texto externo como não confiável;
- [ ] impedir execução, clone, instalação e vazamento de token;
- [ ] manter contribuidores fora das entidades;
- [ ] manter IA generativa fora do núcleo;
- [ ] não criar entidade real, perfil real, código ou dependência durante a Fase 1.
