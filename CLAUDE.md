# Second Brain — Vault Principal

## Quem sou

Elvis — Product Manager / Liderança de Produto na MGC.
Este é o vault principal do dia a dia: captura tudo aqui, opera trabalho e time, roteia conhecimento para o wiki.

---

## Vaults do sistema

| Vault | Propósito |
|---|---|
| `second_brain` (este) | Vault principal — captura, trabalho, produto, time, pessoal |
| `wiki` | Base de conhecimento sintetizado |

---

## Identity and Role (LLM)

Co-mantenedor deste vault. Ajuda a processar Inbox, manter documentos de produto e time, rotear conhecimento para o wiki. Use `/para-wiki` para enviar conteúdo ao vault wiki.

---

## Directory Contract

| Path | Owner | Rule |
|---|---|---|
| `00 Inbox/` | Human | Captura diária. LLM lê e ajuda a processar. |
| `Daily Notes/` | Human | Journal diário. LLM lê se pedido. |
| `Templates/` | Human | Templates reutilizáveis. LLM lê. |
| `Excalidraw/` | Human | Diagramas. LLM lê. |
| `02 Areas/Financeiro/` | Human | IPTU, impostos, contabilidade pessoal |
| `02 Areas/Pessoal/` | Human | Saúde, família, compras, casa |
| `02 Areas/Trabalho/analytics/` | Shared | Métricas, queries, schemas |
| `02 Areas/Trabalho/governance/` | Shared | OKR health, cross-pillar log, planning calendar |
| `02 Areas/Trabalho/product_execution/` | Shared | Pilares de produto |
| `02 Areas/Trabalho/strategy/` | Shared | Visão, OKRs estratégicos |
| `02 Areas/Trabalho/team_mgmt/` | Shared | 1:1s, carreira, hiring, rituais |
| `02 Areas/Trabalho/produto_mgc/` | Shared | Processo de produto, iniciativas, OKRs |
| `03 Resources/Viagens/` | Human | Roteiros, restaurantes, notas de viagem |
| `assets/` | Human | Imagens e arquivos soltos |

---

## GTD

### Fluxo de captura

```
Qualquer coisa → 00 Inbox/

Processar:
├── É conhecimento a sintetizar?    → /para-wiki
├── É de trabalho/produto/time?     → 02 Areas/Trabalho/
├── É pessoal (saúde, família)?     → 02 Areas/Pessoal/ ou Financeiro/
└── É lixo?                         → deletar
```

### Convenções

- `- [ ]` para próximas ações dentro das notas
- `[[Link]]` para conectar notas relacionadas
- Tags: `#projeto` `#area` `#1:1` `#someday` `#importante`

### Weekly Review (toda sexta)
1. Processar Inbox a zero
2. Rotear conhecimento pendente via `/para-wiki`
3. Atualizar `02 Areas/Trabalho/governance/okr-health.md`
4. Atualizar `02 Areas/Trabalho/governance/cross-pillar-log.md`
5. Revisar `02 Areas/Trabalho/product_execution/` — cada pilar tem próxima ação?

---

## Session Startup Checklist

1. Ler `CLAUDE.md` em full
2. Confirmar com o humano o que fazer

---

## Skills disponíveis

- `/para-wiki <conteúdo>` — envia para o vault wiki para ingestão
- `/wiki <pergunta>` — consulta a base de conhecimento do vault wiki

### gstack

Use `/browse` para todo web browsing. Nunca usar `mcp__claude-in-chrome__*` diretamente.

Skills: `/office-hours`, `/plan-ceo-review`, `/plan-eng-review`, `/plan-design-review`, `/design-consultation`, `/design-shotgun`, `/design-html`, `/review`, `/ship`, `/land-and-deploy`, `/canary`, `/benchmark`, `/browse`, `/connect-chrome`, `/qa`, `/qa-only`, `/design-review`, `/setup-browser-cookies`, `/setup-deploy`, `/retro`, `/investigate`, `/document-release`, `/codex`, `/cso`, `/autoplan`, `/plan-devex-review`, `/devex-review`, `/careful`, `/freeze`, `/guard`, `/unfreeze`, `/gstack-upgrade`, `/learn`

---

## Git Commit Conventions

```
inbox: [processamento do inbox]
work: [atualização de trabalho/produto]
people: [gestão de pessoas]
gtd: [reorganização GTD]
chore: [manutenção]
```
