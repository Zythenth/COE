# Intervenção, percepção e conhecimento — contrato conceitual

Este documento especializa conceitualmente o GDD 1.3 para Intervenções do Arquiteto e para a cadeia que liga alteração, evidência, percepção, interpretação, crença, memória, rumor e consequência. Ele não é schema executável, JSON Schema, tipo de programação, arquivo de save, template de conteúdo nem entidade de Eldrath.

## 1. Objetivo

Definir como o usuário pode intervir durante uma campanha sem romper causalidade, autonomia dos NPCs, conhecimento limitado, determinismo ou replay. A origem extradiegética da ação permanece disponível às ferramentas administrativas, mas nunca se torna automaticamente conhecimento dos personagens.

## 2. Escopo

O contrato cobre:

- papéis do usuário antes e durante a campanha;
- comandos e eventos de intervenção;
- alterações materiais, ambientais, informacionais, de acontecimentos e de influência;
- evidências, testemunhas e resultados individuais de percepção;
- conhecimento, crença, suspeita, memória e rumor;
- resistência, determinismo, checkpoints, ramificações e permissões;
- integração futura com NPCs, eventos, itens, recursos e interface.

Não cria entidades reais, pastas de conteúdo, templates, valores, lore, saves, validação automatizada ou código.

## 3. Termos

- **Causa real do sistema:** metadado restrito que identifica uma Intervenção do Arquiteto.
- **Alteração:** mudança física ou sistêmica produzida pelo comando.
- **Evidência:** sinal persistente ou transitório deixado pela alteração.
- **Percepção:** parte da alteração ou da evidência acessível a uma entidade.
- **Interpretação:** explicação subjetiva formada a partir do percebido.
- **Conhecimento:** fato corretamente conhecido por via válida.
- **Crença:** afirmação aceita como verdadeira, mesmo que seja falsa.
- **Suspeita:** possibilidade considerada sem aceitação plena.
- **Memória:** registro subjetivo da experiência ou comunicação recebida.
- **Rumor:** versão transmissível de uma afirmação com origem e genealogia.
- **Consequência:** decisão ou evento posterior produzido pela cadeia causal.
- **Influência:** modificador temporário de pesos da decisão que preserva escolha.
- **Compulsão:** tentativa separada de obrigar uma ação específica.

Fato, percepção, interpretação, crença e conhecimento não são sinônimos.

## 4. Separação entre conteúdo estático e estado de campanha

O pacote estático define entidades iniciais, propriedades, capacidades, limites, condições e referências autorizadas. A campanha registra comandos, `item_instance`, quantidades atuais de recursos, alterações, eventos, evidências, percepções, memórias, rumores e consequências.

Uma intervenção pertence ao estado da campanha. Ela não é arquivo de conteúdo inicial, não possui pasta própria em `content/`, não recebe template e não existe uma quantidade planejada de “intervenções iniciais”.

## 5. Papéis do usuário

O usuário continua combinando Arquiteto, Observador e Cronista.

- **Arquiteto — editor inicial:** antes da campanha, edita conteúdo inicial e configurações permitidas; essas mudanças ainda não precisam ser percebidas por NPCs.
- **Arquiteto — interventor:** durante a campanha, produz alterações por comandos validados e registrados.
- **Observador:** acompanha o mundo sem precisar interferir e pode usar visões autorizadas.
- **Cronista:** organiza e comenta a história sem alterar a simulação, salvo conversão explícita e validada em fato do mundo.

O usuário não é NPC, divindade obrigatória, facção, personagem invisível nem entidade conhecida pelo mundo.

## 6. Intervenção do Arquiteto

Uma intervenção em campanha:

- não altera estado silenciosamente;
- gera comando e evento;
- entra na cadeia causal, histórico e replay;
- deixa efeitos e evidências coerentes com sua natureza;
- só é percebida por entidades em condições válidas;
- não revela automaticamente a causa real;
- termina como sucesso, falha ou efeito parcial.

Personagens podem atribuir seus efeitos a causas internas como magia, acidente, criatura, divindade ou conspiração. A interpretação não comprova a existência do usuário.

## 7. Categorias de intervenção

### Material

Pode mover, soltar, colocar, retirar ou transferir uma `item_instance`; adicionar ou retirar quantidade válida de `resource`; e alterar propriedade material autorizada. `item` é definição estática, `item_instance` é ocorrência persistida e `resource` é fungível e quantitativo. O comando nunca move o arquivo estático do item.

### Ambiental

Pode produzir som, luz, odor, marca, movimento, mudança localizada de temperatura, manifestação visual ou outro estímulo suportado. Alcance, duração, intensidade e evidências devem ser coerentes.

### Informacional

Pode introduzir pista, documento, mensagem anônima, inscrição, afirmação ou rumor inicial. Um rumor exige origem, primeiro portador ou canal, local, momento, conteúdo, alcance inicial e possibilidade de transmissão.

### Sobre acontecimentos

Pode iniciar evento permitido, atrasar evento agendado, acelerar condição existente, remover efeito removível ou revelar local ou informação por via válida. Não pode ignorar invariantes ou criar referências inexistentes.

### Influência de decisão

Pode adicionar modificador temporário a fatores como coragem, medo, curiosidade, cautela, hostilidade, confiança, urgência, interesse por alvo, prioridade de investigação ou resistência a uma possibilidade. Não escolhe a ação pelo NPC.

## 8. Comando de intervenção

O comando é a intenção validável e ordenável do usuário. Conceitualmente registra:

- ID único, campanha e ramificação;
- tick solicitado e ponto seguro de aplicação;
- tipo, alvos por ID e parâmetros;
- intensidade, duração e política de visibilidade;
- estado anterior necessário para auditoria;
- validações realizadas;
- fluxo pseudoaleatório nomeado, quando necessário;
- resultado e estado de sucesso, falha ou efeito parcial.

Este conjunto é um contrato conceitual. O modelo técnico e o formato persistente serão definidos somente nas fases autorizadas.

## 9. Evento resultante

Toda alteração aplicada gera pelo menos um evento imutável que registra o que ocorreu no mundo. O evento aponta para o comando, os alvos, o local, os efeitos, as evidências e as consequências diretas, preservando a origem administrativa em campo restrito.

Evento resultante não é a mesma coisa que percepção. Um acontecimento pode existir sem ser percebido por ninguém e ainda assim deixar evidências futuras.

## 10. Origem real restrita

A indicação “Intervenção do Arquiteto” fica disponível somente em:

- log interno;
- modo onisciente;
- inspetor causal;
- histórico administrativo da campanha;
- replay e depuração.

Essa origem não pode alimentar conhecimento, crença, memória, rumor ou decisão de NPC. Apresentações focadas ou públicas mostram somente fatos, evidências e versões diegéticas autorizadas.

## 11. Evidências

Evidências são sinais compatíveis com a alteração: posição de um objeto, impacto sonoro, luz residual, marca, odor, documento, rastro, mudança de estoque ou outro vestígio suportado. Cada evidência possui local, disponibilidade temporal, intensidade e condições de descoberta coerentes.

Nem toda intervenção deixa evidência duradoura, mas nenhuma pode omitir efeitos que sua natureza necessariamente produziria. Evidência não transmite automaticamente a causa verdadeira.

## 12. Testemunhas potenciais

Testemunhas potenciais são entidades que poderiam receber algum estímulo ou encontrar evidência, considerando:

- presença, localização e distância;
- linha de visão, iluminação e audição;
- atenção, saúde e consciência;
- competência e magia;
- duração, alcance e intensidade do estímulo;
- passagem posterior pelo local;
- comunicação de outra entidade.

Potencial não significa percepção confirmada.

## 13. Resultados individuais de percepção

Cada NPC recebe resultado próprio: percepção visual, auditiva ou de outro sentido; descoberta posterior; informação comunicada; percepção parcial; interpretação incorreta; ou ausência de percepção.

Exemplo canônico: ao mover uma espada da mesa para o chão, um NPC pode ver o movimento sem agente visível, outro ouvir o impacto, outro encontrar a espada mais tarde e outro não perceber nada. Nenhum recebe a frase “o Arquiteto moveu a espada”.

O resultado deve permitir explicar por que a entidade percebeu, percebeu parcialmente ou não percebeu.

## 14. Conhecimento

Conhecimento exige uma via válida e uma correspondência correta com o fato. Pode vir de percepção suficiente, evidência interpretada corretamente, comunicação confiável, investigação ou efeito mágico já existente.

Conhecimento não surge por proximidade narrativa nem por acesso interno do motor. Um NPC ausente não aprende automaticamente o que ocorreu.

## 15. Crença

Crença registra a afirmação aceita, confiança, fonte, data, evidências, confirmações e contradições. Pode ser verdadeira ou falsa e deve permanecer distinta do fato do motor.

Uma intervenção pode criar circunstâncias que alterem crenças, mas não pode escrever crença silenciosamente. A mudança precisa passar por experiência, evidência, comunicação ou outro mecanismo diegético válido.

## 16. Suspeita

Suspeita é uma hipótese considerada com confiança insuficiente para virar crença consolidada. Pode apontar para uma causa interna possível, inclusive magia, acidente, criatura, divindade ou conspiração.

Suspeita nunca usa o metadado restrito da intervenção. Ela pode ser fortalecida, enfraquecida, abandonada ou transformada em crença conforme novas evidências.

## 17. Memória

Memória registra a versão subjetiva percebida ou comunicada, sua origem, certeza, emoção, saliência, local, data e vínculos causais. Ela não copia automaticamente o evento verdadeiro nem o campo de origem administrativa.

Uma testemunha visual, uma auditiva e um descobridor posterior podem criar memórias diferentes do mesmo evento. A memória pode perder detalhes ou ser reinterpretada sem alterar o fato histórico.

## 18. Rumor

Rumor é uma afirmação transmissível com origem e genealogia. Uma intervenção informacional pode iniciar sua cadeia somente por um primeiro portador ou canal válido, em local e momento definidos, com alcance inicial limitado.

Transmissões posteriores dependem de comunicação e podem distorcer agente, quantidade, intenção, causa ou certeza. Rumores e memórias guardam versões diegéticas, nunca a causa real restrita.

## 19. Influência de decisão

Influência adiciona modificador temporário ao cálculo de utilidade. O resultado continua dependendo de:

- personalidade, valores e objetivos;
- necessidades, emoções e relações;
- crenças, memórias e conhecimento;
- risco percebido e alternativas disponíveis;
- intensidade, duração e resistência;
- desempate determinístico.

A influência pode ser aceita, parcial, reinterpretada, resistida ou falhar. Fatores aplicados e resultado precisam permanecer explicáveis.

## 20. Resistência

Resistência representa a capacidade contextual de preservar prioridades e rejeitar ou reduzir uma influência. Pode derivar de vontade, personalidade, valores, convicções, experiência, relações, percepção de risco, proteção mágica ou outras regras aprovadas.

Resistência não precisa anular sempre o efeito. Ela pode reduzir intensidade, duração ou peso, redirecionar a interpretação ou impedir a influência. O desempate continua reproduzível.

## 21. Diferença entre influência e compulsão

**Influência** modifica pesos, preserva escolha e pertence ao MVP. **Compulsão** tenta obrigar uma ação específica, reduz autonomia, fica desativada por padrão e não pertence ao MVP inicial.

Se futuramente autorizada, compulsão será recurso separado. O NPC poderá registrar impulso inexplicável, sensação de perda de controle, lacuna, compulsão ou conflito interno, mas ainda não conhecerá o usuário como origem.

## 22. Ordem do tick

No ponto seguro do tick:

1. comandos são recebidos;
2. permissões, alvos, parâmetros e invariantes são validados;
3. comandos são ordenados e recursos são reservados;
4. intervenções admitidas são aplicadas;
5. eventos e evidências são produzidos;
6. testemunhas potenciais e percepções individuais são resolvidas;
7. conhecimento, influências e contexto disponíveis alimentam decisões;
8. ações dos NPCs seguem o fluxo normal;
9. memórias, rumores, consequências e logs são persistidos.

Intervenção aplicada antes da decisão pode afetar o mesmo tick. Comando recebido durante resolução atômica já iniciada aguarda o próximo ponto seguro.

## 23. Determinismo

A intervenção altera o futuro determinístico a partir do tick de aplicação, sem tornar irreproduzível a linha anterior preservada. Ordem dos comandos, validações, estado anterior e fluxos pseudoaleatórios nomeados fazem parte da reprodução.

Nenhuma intervenção pode depender de geração de texto ou IA para determinar efeitos, sucesso, percepção ou decisão.

## 24. Replay

A nova linha é reproduzível usando versão do motor e do conteúdo, semente, configurações, estado inicial ou checkpoint e log ordenado de comandos. O replay deve reconstruir eventos, evidências, percepções e resultados probabilísticos equivalentes.

Desfazer não apaga silenciosamente o comando já persistido. Linhas abandonadas permanecem identificáveis enquanto preservadas.

## 25. Checkpoints

Checkpoint é um estado consistente usado antes de ação destrutiva, migração ou outra operação de risco. Restaurá-lo retorna a esse estado e mantém registro de origem e relação com a linha posterior.

Checkpoint não é edição mental, não modifica o conteúdo estático e não substitui a confirmação do usuário.

## 26. Ramificações

Ramificação preserva a linha pai, o ponto de separação e a sequência divergente de comandos. Alterações estruturais de política, intervenções destrutivas ou exploração de “e se” podem exigir ramificação.

São operações diferentes: desfazer antes de continuar, restaurar checkpoint, criar ramificação, corrigir administrativamente e apagar um save inteiro. Desfazer cancela comando ainda não aplicado; depois da aplicação, usa o checkpoint anterior ou uma ramificação e preserva o registro administrativo.

## 27. Permissões da campanha

- **Observador:** intervenções de campanha desativadas.
- **Arquiteto livre:** intervenções válidas sem orçamento de jogo.
- **Arquiteto limitado:** limites, custos ou recargas configuráveis.

Observador e Arquiteto livre são previstos no MVP. Arquiteto limitado é posterior. Mudança estrutural de política após o início exige ramificação ou confirmação explícita e não cria condição de vitória.

## 28. Invariantes

- Toda intervenção aplicada possui comando, evento e cadeia causal.
- A causa real restrita nunca vira conhecimento de NPC.
- Percepção exige via válida e é resolvida individualmente.
- Fato, percepção, interpretação, crença, suspeita, memória e rumor permanecem distintos.
- `item` estático não é movido; intervenção material aponta para `item_instance`.
- Quantidades atuais de `resource` pertencem ao save.
- Referências usam IDs existentes e válidos.
- Influência preserva escolha e registra resistência.
- Crenças, memórias, relações, conhecimento, objetivos, personalidade e decisão final não são editados silenciosamente.
- Rumor possui origem e não aparece simultaneamente em todas as mentes.
- Resolução atômica não recebe mutação concorrente.
- Replay reproduz a linha pelo log ordenado.
- Correção administrativa é pausada, explícita e separada do acontecimento orgânico.

## 29. Integração futura com NPCs

O futuro contrato de NPC deve representar limites sensoriais, atenção, consciência, competências, conhecimento, crenças, suspeitas, memórias, resistência e fontes de informação sem oferecer acesso a metadados administrativos.

NPCs-semente precisarão declarar condições iniciais suficientes para validar interpretações divergentes e resistência, sem inventar onisciência.

## 30. Integração futura com eventos

O futuro contrato de evento deve separar fato ocorrido, comando originador, causa administrativa restrita, efeitos, evidências, observadores potenciais, percepções confirmadas e consequências. Evento permanece imutável e consultável pela cadeia causal.

Eventos históricos estáticos não são intervenções de campanha, ainda que possam servir de referência causal ao estado inicial.

## 31. Integração futura com rumores

O futuro contrato de rumor deve registrar afirmação, origem, primeiro emissor ou canal, local, momento, alcance inicial, fontes intermediárias, versões, grupos e lugares alcançados. A genealogia preserva a distinção entre repetição e fontes independentes.

Nenhum rumor expõe “Intervenção do Arquiteto” como verdade conhecida por personagens.

## 32. Integração futura com itens e recursos

Uma intervenção material usa `item_instance` para objetos discretos persistidos e quantidade do estado para recursos fungíveis. Definições `item.*` e `resource.*` continuam no pacote estático e podem declarar capacidades, unidades, limites e propriedades autorizadas.

Transferência valida proprietário ou recipiente, origem, destino, quantidade, compatibilidade, reserva e inexistência de uso duplo no tick. Valores atuais nunca são escritos de volta aos arquivos autorais.

## 33. Integração futura com interface

O fluxo futuro deve permitir pausar, selecionar contexto, escolher intervenção, preencher parâmetros, ver prévia, alcance, evidências e possíveis observadores, confirmar, acompanhar resultado, consultar cadeia causal e criar ramificação.

Ações principais ficam visíveis e nomeadas. A interface diferencia edição inicial, intervenção e correção administrativa; confirma ações destrutivas; mostra antes e depois; mantém histórico; informa que NPCs não recebem a causa real; explica percepções individuais; e funciona por fichas, listas, busca e páginas de entidade, sem depender de mapa gráfico.

## 34. Validação manual

Antes de aprovar um contrato futuro relacionado, conferir:

- separação entre conteúdo estático e estado da campanha;
- comando, evento, causa restrita e cadeia causal explícitos;
- alvos por ID e referências existentes;
- `item_instance` em vez de definição `item` para movimento material;
- quantidades atuais de recursos somente no estado;
- evidências compatíveis com a ação;
- testemunhas potenciais e percepções individuais justificadas;
- ausência de conhecimento automático ou metadado extradiegético em NPCs;
- distinção entre fato, interpretação, crença, suspeita, memória e rumor;
- origem e genealogia de rumor;
- influência sem decisão garantida e com resistência;
- ordem segura do tick, determinismo e replay;
- confirmação, checkpoint ou ramificação em ações destrutivas;
- ausência de alteração mental silenciosa;
- ausência de entidade real, template, pasta de conteúdo, save ou código criado por este contrato.

## 35. Decisões adiadas

Permanecem para fases posteriores:

- catálogo definitivo de comandos e parâmetros;
- formato persistente e IDs técnicos de intervenção;
- políticas concretas de alcance, intensidade, duração e evidência;
- fórmulas sensoriais, de resistência e de influência;
- limites, custos e recargas do Arquiteto limitado;
- eventual compulsão posterior ao MVP;
- ferramentas administrativas profundas;
- política detalhada de checkpoints e ramificações avançadas;
- schemas executáveis, banco de dados, API, interface e implementação.
