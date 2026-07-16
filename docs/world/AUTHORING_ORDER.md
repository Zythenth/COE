# Ordem de autoria

Esta é a sequência obrigatória de construção definida para Chronicles of Eldrath. A fundação editorial, os contratos, os templates, a auditoria editorial final e a consolidação da Fase 1 foram concluídos sem iniciar implementação. A Fase 1 está encerrada e a Fase 2 está em andamento: a identidade geral de Eldrath foi aprovada no item 6, `calendar.marco` foi aprovado no item 7, os três idiomas foram aprovados no item 8 e quatro culturas foram criadas em revisão no item 9. A próxima atividade é aprovar as culturas e avançar ao item 10, cosmologia necessária e princípios religiosos gerais. Toda a ordem posterior permanece preservada. Esta ordem registra dependências editoriais e de produção, sem desenvolver antecipadamente o conteúdo de nenhuma etapa.

1. fundação editorial;
2. convenções definitivas de arquivos e IDs;
3. schemas editoriais fundamentais — concluído;
4. templates de conteúdo fundamentais — concluído;
5. regras de referências cruzadas;
6. identidade geral de Eldrath — `world.eldrath` aprovado;
7. calendário e eras — `calendar.marco` aprovado;
8. idiomas — `language.valdren`, `language.ardren` e `language.senkar` aprovados;
9. culturas — `culture.dorven`, `culture.namaru`, `culture.tessari` e `culture.ostelar` criadas; `in_review`;
10. cosmologia necessária e princípios religiosos gerais — próxima atividade após a aprovação do item 9;
11. reino;
12. sistema político;
13. sucessão;
14. moeda;
15. leis gerais e mágicas;
16. regiões;
17. capital;
18. cidades;
19. vilas;
20. locais especiais;
21. rotas;
22. biomas e clima;
23. recursos;
24. produção, comércio e economia;
25. profissões;
26. contrato conceitual de intervenção, percepção, conhecimento e causalidade — concluído;
27. religiões e cultos — contrato e template concluídos; entidades não iniciadas;
28. facções e instituições — contrato e template concluídos; entidades não iniciadas;
29. famílias e casas — contrato e template concluídos; entidades não iniciadas;
30. contrato e template de leis — concluídos; entidades detalhadas não iniciadas e reservadas às Fases 2 e 4;
31. escolas de magia — contrato e template concluídos; entidades não iniciadas;
32. magias — contrato e template concluídos; entidades não iniciadas;
33. rituais — contrato e template concluídos; entidades não iniciadas;
34. efeitos mágicos — contrato e template concluídos; entidades não iniciadas;
35. artefatos — contrato e template concluídos; entidades não iniciadas;
36. itens — contrato e template concluídos; entidades não iniciadas;
37. criaturas — contrato e template concluídos; entidades não iniciadas;
38. doenças — contrato e template concluídos; entidades não iniciadas;
39. saúde e condições relacionadas — contrato conceitual concluído; sem entidade, pasta, prefixo ou template próprios;
40. contratos e template de NPCs, personalidade, valores, necessidades, emoções, objetivos, relações, memória, conhecimento, reputação, inventário, afinidade e domínio mágico — concluídos; entidades não iniciadas;
41. contratos e templates de eventos, rumores, história, cadeias causais, conflitos latentes e gatilhos, além do contrato de ameaças monstruosas e incursões — concluídos;
42. contrato conceitual de geração opcional por projetos públicos do GitHub, cálculo, regiões, assentamentos, rotas, mapa, saves, checkpoint inicial, ramificações, reinício e velocidade — concluído; auditoria editorial final e consolidação concluídas; Fase 1 encerrada;
43. planejamento dos NPCs-semente;
44. criação dos NPCs-semente;
45. relações iniciais;
46. objetivos, medos e segredos;
47. crenças, conhecimentos e memórias;
48. eventos históricos;
49. rumores iniciais;
50. conflitos latentes;
51. referências cruzadas;
52. auditoria cronológica;
53. auditoria geográfica;
54. auditoria econômica;
55. auditoria social;
56. auditoria mágica;
57. correções;
58. congelamento da primeira versão do mundo;
59. `PROJECT_SPECIFICATION.md`;
60. `DATA_MODEL.md`;
61. `MVP.md`;
62. `APP_AND_UI_SPECIFICATION.md`;
63. `SITE_MAP.md`;
64. `USER_FLOWS.md`;
65. `COMPONENT_INVENTORY.md`;
66. `ARCHITECTURE.md` em nível conceitual;
67. `ROADMAP.md`;
68. pesquisa e criação do `ANTI_AI_DESIGN_GUIDE.md`;
69. criação do `DESIGN_SYSTEM.md`;
70. criação do `STITCH_WORKFLOW.md`;
71. briefings das telas;
72. dados reais para as maquetes;
73. referências visuais documentadas;
74. prompts para o Google Stitch;
75. geração das telas no Stitch;
76. auditoria Anti-AI das telas;
77. correções no Stitch;
78. exportação e versionamento;
79. conexão pelo MCP oficial;
80. transferência ao Codex;
81. arquitetura técnica;
82. programação do vertical slice;
83. MVP;
84. versão 1.0.

## Dependência entre os grupos

| Etapas | Grupo | Por que depende do anterior |
|---|---|---|
| 1 | Fundação editorial | Estabelece a autoridade canônica, a estrutura e o controle necessários para qualquer autoria posterior. |
| 2–5 | Contratos editoriais | Dependem da fundação para definir, de forma consistente, como entidades e referências serão representadas. |
| 6–15 | Fundamentos do mundo | Dependem dos contratos para registrar a identidade macro, o tempo, a sociedade e o reino sem formatos incompatíveis. |
| 16–25 | Geografia e vida material | Dependem do contexto macro para localizar territórios, assentamentos, circulação, recursos e economia coerentemente. |
| 26 | Contrato transversal de intervenção | Depende da economia material e estabelece causalidade, percepção e conhecimento antes dos contratos sociais. |
| 27–39 | Sociedade, instituições, magia e saúde | Dependem do território, da vida material e do contrato transversal para que poder, fé, famílias, magia, saúde e leis tenham contexto e consequências. |
| 40–42 | Contratos de NPCs, história, ameaças e geração de mundo | Dependem dos contratos anteriores para separar pessoa, espécie, estado agregado, conhecimento, inventário, causalidade, rumor, conflito, geração opcional, snapshot e campanha. A subetapa e sua auditoria editorial final estão concluídas. |
| 43–50 | NPCs e história inicial | Dependem de todos os contratos anteriores para criar pessoas e conflitos conectados ao mundo. |
| 51–58 | Integração, auditoria e congelamento | Dependem do pacote de conteúdo completo para resolver referências, contradições e incoerências antes de fixar a primeira versão. |
| 59–67 | Especificações do produto | Dependem do mundo aprovado para especificar dados, tarefas, interface e limites com conteúdo real em vez de suposições. |
| 68–70 | Governança visual | Depende das especificações para estabelecer critérios Anti-AI, sistema de design e fluxo do Stitch adequados ao produto. |
| 71–80 | Preparação, uso e transferência do Stitch | Dependem da governança visual para produzir, auditar, corrigir e transferir referências rastreáveis sem tratá-las como código aprovado. |
| 81–84 | Implementação e versões | Dependem do mundo, das especificações e das referências visuais aprovadas; a programação começa somente na Fase 11. |

Avançar um grupo não autoriza pular a revisão e a aprovação do grupo anterior. Os nomes de documentos das etapas futuras são apenas referências de planejamento; esses arquivos não são criados antecipadamente na Fase 1.
