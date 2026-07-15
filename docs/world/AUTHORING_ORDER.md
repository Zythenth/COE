# Ordem de autoria

Esta é a sequência obrigatória de construção definida para Chronicles of Eldrath. A fundação editorial, o contrato comum, os schemas e templates fundamentais, geográficos, de economia material, de sociedade, instituições e lei, do sistema mágico e de criaturas e doenças, além dos contratos conceituais de intervenção, percepção, conhecimento, saúde e condições da Fase 1, foram concluídos. Os contratos estão documentados, mas suas entidades reais não foram iniciadas. A Fase 1 continua em andamento; a próxima atividade documental cobre NPCs, personalidade, necessidades, objetivos, relações, memória, conhecimento, reputação, inventário, afinidade e domínio mágico. Nenhuma etapa de construção do mundo foi iniciada. Esta ordem registra dependências editoriais e de produção, sem desenvolver o conteúdo de nenhuma etapa.

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
40. contratos e templates de NPCs, personalidade, necessidades, objetivos, relações, memória, conhecimento, reputação, inventário, afinidade e domínio mágico — próxima atividade documental;
41. planejamento dos NPCs-semente;
42. criação dos NPCs-semente;
43. relações iniciais;
44. objetivos, medos e segredos;
45. crenças, conhecimentos e memórias;
46. eventos históricos;
47. rumores iniciais;
48. conflitos latentes;
49. referências cruzadas;
50. auditoria cronológica;
51. auditoria geográfica;
52. auditoria econômica;
53. auditoria social;
54. auditoria mágica;
55. correções;
56. congelamento da primeira versão do mundo;
57. `PROJECT_SPECIFICATION.md`;
58. `DATA_MODEL.md`;
59. `MVP.md`;
60. `APP_AND_UI_SPECIFICATION.md`;
61. `SITE_MAP.md`;
62. `USER_FLOWS.md`;
63. `COMPONENT_INVENTORY.md`;
64. `ARCHITECTURE.md` em nível conceitual;
65. `ROADMAP.md`;
66. pesquisa e criação do `ANTI_AI_DESIGN_GUIDE.md`;
67. criação do `DESIGN_SYSTEM.md`;
68. criação do `STITCH_WORKFLOW.md`;
69. briefings das telas;
70. dados reais para as maquetes;
71. referências visuais documentadas;
72. prompts para o Google Stitch;
73. geração das telas no Stitch;
74. auditoria Anti-AI das telas;
75. correções no Stitch;
76. exportação e versionamento;
77. conexão pelo MCP oficial;
78. transferência ao Codex;
79. arquitetura técnica;
80. programação do vertical slice;
81. MVP;
82. versão 1.0.

## Dependência entre os grupos

| Etapas | Grupo | Por que depende do anterior |
|---|---|---|
| 1 | Fundação editorial | Estabelece a autoridade canônica, a estrutura e o controle necessários para qualquer autoria posterior. |
| 2–5 | Contratos editoriais | Dependem da fundação para definir, de forma consistente, como entidades e referências serão representadas. |
| 6–15 | Fundamentos do mundo | Dependem dos contratos para registrar a identidade macro, o tempo, a sociedade e o reino sem formatos incompatíveis. |
| 16–25 | Geografia e vida material | Dependem do contexto macro para localizar territórios, assentamentos, circulação, recursos e economia coerentemente. |
| 26 | Contrato transversal de intervenção | Depende da economia material e estabelece causalidade, percepção e conhecimento antes dos contratos sociais. |
| 27–39 | Sociedade, instituições, magia e saúde | Dependem do território, da vida material e do contrato transversal para que poder, fé, famílias, magia, saúde e leis tenham contexto e consequências. |
| 40 | Contratos de NPCs | Dependem dos contratos sociais, geográficos, econômicos, mágicos e de saúde para separar pessoa, estado, conhecimento, inventário e capacidades sem metaconhecimento. |
| 41–48 | NPCs e história inicial | Dependem de todos os sistemas sociais, geográficos, mágicos e de saúde anteriores para criar pessoas e conflitos conectados ao mundo. |
| 49–56 | Integração, auditoria e congelamento | Dependem do pacote de conteúdo completo para resolver referências, contradições e incoerências antes de fixar a primeira versão. |
| 57–65 | Especificações do produto | Dependem do mundo aprovado para especificar dados, tarefas, interface e limites com conteúdo real em vez de suposições. |
| 66–68 | Governança visual | Depende das especificações para estabelecer critérios Anti-AI, sistema de design e fluxo do Stitch adequados ao produto. |
| 69–78 | Preparação, uso e transferência do Stitch | Dependem da governança visual para produzir, auditar, corrigir e transferir referências rastreáveis sem tratá-las como código aprovado. |
| 79–82 | Implementação e versões | Dependem do mundo, das especificações e das referências visuais aprovadas; a programação começa somente na Fase 11. |

Avançar um grupo não autoriza pular a revisão e a aprovação do grupo anterior. Os nomes de documentos das etapas futuras são apenas referências de planejamento; esses arquivos não são criados na Fase 0.
