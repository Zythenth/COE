---
schema_version: "1.0.0"
id: "language.valdren"
name: "Valdren"
content_status: approved
tags: []
aliases:
  - "Fala Valdrena"
summary: >-
  Idioma vivo de ampla circulação usado em administração, comércio, troca de
  informações e comunicação entre grupos, sem ser universal nem intrinsecamente
  superior a outras línguas.
references: []
art: []
notes: |-
  Valdren é uma língua franca por processos históricos de circulação, ensino e
  conveniência social. Sua difusão não implica maior inteligência, precisão ou
  valor cultural de seus falantes.

  Todas as formas apresentadas nas convenções são exemplos lexicais sem
  referente canônico. Variantes valdrenas dos nomes do Calendário do Marco não
  são registradas porque o contrato atual não possui propriedade adequada para
  traduções; os nomes e IDs já aprovados do calendário permanecem canônicos.
native_name: "Valdren"
language_status: active
writing_systems:
  - type: "alphabetic"
    name: "Escrita corrente valdrena"
    direction: "left_to_right"
    reference_ids: []
    transliteration: >-
      Usa correspondência previsível em caracteres ASCII comuns, espaços entre
      palavras e nenhuma marca rara obrigatória.
    speech_writing_relation: >-
      A ortografia corrente acompanha a fala formal de perto, mas preserva
      algumas grafias históricas e não permite deduzir pronúncia regional sem
      aprendizagem adicional.
culture_ids:
  - "culture.dorven"
  - "culture.namaru"
  - "culture.tessari"
  - "culture.ostelar"
region_ids: []
speaker_groups:
  - type: "native_and_additional_speakers"
    reference_ids: []
    description: >-
      Inclui falantes nativos e pessoas que a aprendem para circulação social,
      trabalho, administração, comércio ou acesso a informações; nenhuma
      cultura ou região específica é definida nesta etapa.
official_uses:
  - type: "administration"
    reference_ids: []
    description: >-
      Redação administrativa geral, registros correntes, procedimentos e
      comunicação entre responsabilidades distintas.
  - type: "trade"
    reference_ids: []
    description: >-
      Negociação, contratos, medidas explicadas em texto e circulação de
      informações comerciais entre falantes de repertórios diferentes.
  - type: "information_exchange"
    reference_ids: []
    description: >-
      Avisos, correspondência, ensino geral e transmissão de notícias, sem
      pressupor acesso universal ou domínio uniforme.
religious_uses: []
magical_uses: []
intelligibility:
  - language_id: "language.ardren"
    type: "historical_continuity"
    spoken_comprehension: >-
      Muito limitada sem estudo, porque não existe uma comunidade cotidiana
      moderna de Ardren e a pronúncia preservada é especializada.
    written_comprehension: >-
      Parcial para fórmulas frequentes e palavras herdadas; textos contínuos
      exigem formação específica, repertório documental e contexto.
    notes: >-
      Valdren descende de variedades faladas tardias de Ardren, mas simplificou
      flexões, alterou sons e incorporou vocabulário de contato.
  - language_id: "language.senkar"
    type: "contact_borrowing"
    spoken_comprehension: >-
      Não há compreensão geral; termos de circulação e comércio podem ser
      reconhecidos isoladamente por falantes expostos ao registro de contato.
    written_comprehension: >-
      A transliteração comum permite reproduzir formas, mas não fornece
      significado nem domínio da gramática senkar.
    notes: >-
      Empréstimos circulam nos dois sentidos, com adaptação aos sons e à
      estrutura de cada idioma.
naming_conventions:
  personal_names:
    pattern: >-
      Um radical de duas ou três sílabas, às vezes seguido por final breve
      -a, -en ou -or; as terminações não determinam gênero, posição ou caráter.
    example_forms:
      - "Larev"
      - "Miren"
  family_names:
    pattern: >-
      Radical estável sem artigo obrigatório; ramos futuros podem usar um
      segundo radical descritivo, mas a referência permanente continuará sendo
      o ID da família.
  cities_and_villages:
    pattern: >-
      Composto de um radical descritivo e um núcleo locativo; cidades tendem a
      conservar o núcleo pleno, enquanto vilas podem usar forma reduzida sem
      alterar a identidade referenciada.
  regions:
    pattern: >-
      Radical amplo seguido por -ar para área coletiva; o sufixo orienta a
      forma linguística e não cria território ou fronteira.
  factions_and_institutions:
    pattern: >-
      Termo de função seguido pelo coletivo -et; nomes formais podem antepor um
      qualificador, e siglas nunca substituem o ID da entidade.
  roles_and_titles:
    pattern: >-
      Radical de função com o agente -er; títulos precedem nomes em registro
      formal e não são incorporados ao nome pessoal estável.
  magic_schools_and_spells:
    pattern: >-
      Escolas usam um domínio seguido por termo de estudo; magias usam verbo de
      efeito mais qualificador de alcance, modo ou resultado, sem codificar
      custo ou poder apenas no nome.
  artifacts:
    pattern: >-
      Nome comum do objeto seguido por qualificador distintivo ligado por ri;
      a forma visível não substitui o futuro ID do artefato.
  books_and_documents:
    pattern: >-
      Gênero documental primeiro e assunto depois; autoria, versão, idioma e
      confiabilidade permanecem metadados separados do título.
phonetic_notes: |-
  Vogais: a, e, i, o, u. Consoantes frequentes: b, d, f, g, k, l, m, n, p,
  r, s, t, v e os dígrafos ch e sh em empréstimos estabilizados. A sílaba
  básica é (C)V(C); encontros de duas consoantes podem ocorrer na fronteira
  silábica, e finais preferem n, l, r ou s. O acento tende à penúltima sílaba.
  Palavras correntes têm duas ou três sílabas, ritmo regular e contraste claro
  entre raízes e partículas gramaticais.
---

# Visão geral

Valdren é uma língua viva de circulação ampla, mas desigual. Seu papel comum
resulta de redes históricas de contato, ensino, registro e negociação; não é uma
propriedade natural da língua e não elimina repertórios locais. Ela pode sustentar
o futuro uso principal de um reino sem definir esse reino agora e sem impedir
multilinguismo, tradução ou usos especializados de outros idiomas.

A ordem predominante é sujeito–verbo–objeto, com preposições e modificadores
descritivos geralmente depois do núcleo. O plural usa `-en` após consoante e
`-n` após vogal quando precisa ser explícito. A posse usa a sequência possuído,
partícula `ri`, possuidor. `va` precede o complexo verbal na negação, e `ke` ao
fim da oração marca perguntas totais. As partículas pré-verbais `da`, `se` e
`lu` distinguem, respectivamente, ação concluída, curso atual e projeção ou
possibilidade. Contexto pode tornar uma marca desnecessária, mas não altera sua
função.

Há registros cotidiano, corrente formal e documental. O formal evita contrações,
explicita títulos e favorece vocabulário ardreno aprendido. Formalidade indica
relação e situação, não valor pessoal. Falar, compreender fala, ler, escrever,
traduzir e dominar terminologia especializada são capacidades separáveis.

## Escrita

A escrita corrente valdrena é alfabética e segue da esquerda para a direita. A
transliteração editorial usa somente caracteres comuns: `ch` e `sh` representam
sons únicos quando aparecem, e não há acento gráfico obrigatório. Formas nativas,
transliteração e tradução podem ser armazenadas separadamente no futuro; uma
camada visual de escrita não poderá ser requisito para acesso ao conteúdo.

A ortografia é relativamente próxima da fala formal, mas conserva algumas
formas herdadas. Saber falar não garante alfabetização, e copiar uma forma
transliterada não implica compreender seu conteúdo, registro ou autenticidade.

## Uso

Valdren serve à administração, ao comércio, à correspondência e à circulação de
informações entre grupos. Sua presença é ampla, porém não universal: alcance,
fluência, alfabetização e vocabulário técnico dependem de acesso, aprendizagem e
experiência. Em contextos de contato, termos senkares são adaptados à fonotática
valdrena; em contextos documentais, formas ardrenas podem ser preservadas por
prestígio acadêmico ou precisão histórica.

Dificuldades comuns de aprendizagem incluem grafias históricas, escolha de
registro, distinção entre partículas breves e reconhecimento de empréstimos
ardrenos que não seguem inteiramente o padrão corrente.

O idioma não concede conhecimento do assunto tratado. Ler um registro não prova
sua veracidade, reconhecer uma fórmula não revela segredos, e compreender uma
descrição mágica não produz interpretação ou capacidade mágica automática.
Dialeto, falsificação, memória, crença e tradução continuam problemas distintos.

## Convenções de nomes

Nomes valdrenos favorecem duas ou três sílabas, vogais claras e encontros
consonantais moderados. Nomes pessoais, familiares, territoriais, institucionais
e técnicos seguem construções diferentes para que um mesmo radical possa ser
reconhecido sem transformar o nome visível em chave permanente.

As formas `Larev` e `Miren` são somente demonstrações fonológicas. Sufixos como
`-ar`, `-et` e `-er` orientam, respectivamente, áreas coletivas, coletivos
institucionais e agentes funcionais; não afirmam nenhuma região, facção ou cargo.
Nomes de escolas, magias, artefatos, livros e documentos devem descrever domínio,
efeito, objeto ou gênero sem prometer resultado mecânico que os dados futuros
não sustentem.

## História

Valdren descende de variedades faladas tardias de Ardren. A perda de terminações
átonas, a fixação da ordem das palavras e a substituição de parte das flexões por
partículas produziram a gramática atual. Empréstimos aprendidos reintroduziram
formas clássicas em registros acadêmicos e documentais, sem restaurar a língua
antiga como fala cotidiana.

O contato prolongado com Senkar criou um repertório compartilhado sobretudo em
circulação e troca. Os empréstimos foram adaptados de maneira diferente nos dois
idiomas, por isso reconhecer algumas palavras não cria inteligibilidade geral.
A extensão geográfica, os agentes históricos e as instituições responsáveis por
essas mudanças permanecem adiados às entidades futuras adequadas.
