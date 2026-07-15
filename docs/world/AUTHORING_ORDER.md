# Ordem de autoria

Esta é a sequência obrigatória de construção definida para Chronicles of Eldrath. A fundação editorial e os contratos e templates previstos nesta subetapa da Fase 1 foram concluídos, incluindo NPCs, eventos, rumores, história, cadeias causais, conflitos latentes, ameaças monstruosas e incursões. Os contratos estão documentados, mas suas entidades reais não foram iniciadas. A Fase 1 continua em andamento; a próxima atividade é a auditoria editorial final, consolidação e encerramento explícito da fase. Nenhuma etapa de construção do mundo foi iniciada. Esta ordem registra dependências editoriais e de produção, sem desenvolver o conteúdo de nenhuma etapa.

1. fundação editorial;
2. convenções definitivas de arquivos e IDs;
3. schemas editoriais fundamentais — concluído;
4. templates de conteúdo fundamentais — concluído;
5. regras de referências cruzadas;
6. identidade geral de Eldrath;
7. calendário e eras;
8. idiomas;
9. culturas;
10. cosmologia necessária;
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
41. contratos e templates de eventos, rumores, história, cadeias causais, conflitos latentes e gatilhos, além do contrato de ameaças monstruosas e incursões — concluídos; a auditoria editorial final e a consolidação da Fase 1 são a próxima atividade;
42. planejamento dos NPCs-semente;
43. criação dos NPCs-semente;
44. relações iniciais;
45. objetivos, medos e segredos;
46. crenças, conhecimentos e memórias;
47. eventos históricos;
48. rumores iniciais;
49. conflitos latentes;
50. referências cruzadas;
51. auditoria cronológica;
52. auditoria geográfica;
53. auditoria econômica;
54. auditoria social;
55. auditoria mágica;
56. correções;
57. congelamento da primeira versão do mundo;
58. `PROJECT_SPECIFICATION.md`;
59. `DATA_MODEL.md`;
60. `MVP.md`;
61. `APP_AND_UI_SPECIFICATION.md`;
62. `SITE_MAP.md`;
63. `USER_FLOWS.md`;
64. `COMPONENT_INVENTORY.md`;
65. `ARCHITECTURE.md` em nível conceitual;
66. `ROADMAP.md`;
67. pesquisa e criação do `ANTI_AI_DESIGN_GUIDE.md`;
68. criação do `DESIGN_SYSTEM.md`;
69. criação do `STITCH_WORKFLOW.md`;
70. briefings das telas;
71. dados reais para as maquetes;
72. referências visuais documentadas;
73. prompts para o Google Stitch;
74. geração das telas no Stitch;
75. auditoria Anti-AI das telas;
76. correções no Stitch;
77. exportação e versionamento;
78. conexão pelo MCP oficial;
79. transferência ao Codex;
80. arquitetura técnica;
81. programação do vertical slice;
82. MVP;
83. versão 1.0.

## Dependência entre os grupos

| Etapas | Grupo | Por que depende do anterior |
|---|---|---|
| 1 | Fundação editorial | Estabelece a autoridade canônica, a estrutura e o controle necessários para qualquer autoria posterior. |
| 2–5 | Contratos editoriais | Dependem da fundação para definir, de forma consistente, como entidades e referências serão representadas. |
| 6–15 | Fundamentos do mundo | Dependem dos contratos para registrar a identidade macro, o tempo, a sociedade e o reino sem formatos incompatíveis. |
| 16–25 | Geografia e vida material | Dependem do contexto macro para localizar territórios, assentamentos, circulação, recursos e economia coerentemente. |
| 26 | Contrato transversal de intervenção | Depende da economia material e estabelece causalidade, percepção e conhecimento antes dos contratos sociais. |
| 27–39 | Sociedade, instituições, magia e saúde | Dependem do território, da vida material e do contrato transversal para que poder, fé, famílias, magia, saúde e leis tenham contexto e consequências. |
| 40–41 | Contratos de NPCs, história inicial e ameaças | Dependem dos contratos sociais, geográficos, econômicos, mágicos e de saúde para separar pessoa, espécie, estado agregado, conhecimento, inventário, causalidade, rumor, conflito e narrativa sem metaconhecimento. A subetapa termina com auditoria editorial final antes da autoria do mundo. |
| 42–49 | NPCs e história inicial | Dependem de todos os contratos anteriores para criar pessoas e conflitos conectados ao mundo. |
| 50–57 | Integração, auditoria e congelamento | Dependem do pacote de conteúdo completo para resolver referências, contradições e incoerências antes de fixar a primeira versão. |
| 58–66 | Especificações do produto | Dependem do mundo aprovado para especificar dados, tarefas, interface e limites com conteúdo real em vez de suposições. |
| 67–69 | Governança visual | Depende das especificações para estabelecer critérios Anti-AI, sistema de design e fluxo do Stitch adequados ao produto. |
| 70–79 | Preparação, uso e transferência do Stitch | Dependem da governança visual para produzir, auditar, corrigir e transferir referências rastreáveis sem tratá-las como código aprovado. |
| 80–83 | Implementação e versões | Dependem do mundo, das especificações e das referências visuais aprovadas; a programação começa somente na Fase 11. |

Avançar um grupo não autoriza pular a revisão e a aprovação do grupo anterior. Os nomes de documentos das etapas futuras são apenas referências de planejamento; esses arquivos não são criados na Fase 0.
