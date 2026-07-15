# Reserva de design

Esta pasta será utilizada em fases futuras para preservar o processo visual do projeto: referências, briefings de telas, prompts do Google Stitch, capturas das telas geradas, exportações, auditorias e registros de versões.

Todas as subpastas estão vazias por intenção na Fase 0.

## Finalidade das pastas

| Caminho | Finalidade futura |
|---|---|
| `design/references/` | Referências visuais curadas, acompanhadas de origem e justificativa documentadas. |
| `design/stitch/briefs/` | Briefings de telas derivados das especificações aprovadas e preenchidos com dados reais do mundo. |
| `design/stitch/prompts/` | Prompts versionados usados no Google Stitch. |
| `design/stitch/screenshots/` | Capturas das variações e estados gerados para desktop, tablet e mobile. |
| `design/stitch/exports/` | Exportações oficiais preservadas como insumo de referência e transferência. |
| `design/stitch/audits/` | Auditorias Anti-AI, acessibilidade, hierarquia, densidade, responsividade e divergências. |

## Regras de fase e transferência

- O Google Stitch será usado somente na **Fase 10**.
- `Base/ANTI_AI_DESIGN_GUIDE.md` será criado e aprovado na Fase 8, antes do Stitch.
- `Base/DESIGN_SYSTEM.md` será criado e aprovado na Fase 9, antes do Stitch.
- `Base/STITCH_WORKFLOW.md` será criado e aprovado na Fase 9, antes do Stitch.
- Referências visuais deverão registrar origem e justificar o princípio que se deseja estudar; não serão pedidos de cópia direta.
- Resultados e exportações do Stitch serão referências, não código automaticamente aprovado.
- O Codex substituirá o Claude Code no fluxo de transformação das referências em implementação.
- A transferência preferencial usará o MCP oficial quando disponível e quando uma tarefa autorizar explicitamente sua conexão.
- Nenhuma credencial do Stitch, Google Cloud ou MCP poderá ser salva no repositório.
- Nenhum prompt, screenshot, exportação, referência ou auditoria deve ser criado na Fase 0.

O funcionamento do Stitch não foi pesquisado nesta etapa. Esta reserva aplica somente as regras já registradas em `Base/GDD.md`.
