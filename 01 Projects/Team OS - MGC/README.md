# Team OS — MGC
### Guia de Operacionalização

> Sistema operacional do Head de Produto & Design para gerenciar PMs, PDs e lideranças intermediárias com apoio de LLM (Claude Code). Baseado no [team-os-example-repo](https://github.com/in-the-weeds-hannah-stulberg/team-os-example-repo) e adaptado a partir do [podcast Aakash G sobre Claude Code como Team OS](https://www.news.aakashg.com/p/claude-code-team-os).

---

## 1. O que é este sistema

O Team OS é um repositório estruturado que funciona como a memória operacional do Head. Ele não substitui ferramentas como Jira, Slack ou Figma — ele é o **contexto persistente** que conecta pessoas, estratégia, execução e dados em um lugar só.

**A lógica central:** Claude Code lê os `CLAUDE.md` de cada pasta como briefings, e os arquivos de conteúdo (1:1s, PRDs, OKRs) como histórico. Quanto mais preenchido, mais útil. O sistema não aprende sozinho — ele cresce à medida que você escreve.

---

## 2. Setup inicial

Faça isso uma vez, antes de usar o sistema operacionalmente.

- [ ] **Team Roster** — abra `CLAUDE.md` na raiz e substitua os `@handle` pelos nomes reais do time
- [ ] **Visão de produto** — abra `strategy/vision.md` e preencha o propósito e os diferenciais competitivos
- [ ] **Pilares** — abra cada `product_execution/pilar_*/CLAUDE.md` e defina: nome do pilar, PM responsável, PD responsável, domínio de atuação (ex: "Growth & Aquisição")
- [ ] **Mapa de lideranças** — abra `team_mgmt/leadership/roster.md` e mapeie EMs, TLs, Design Lead e stakeholders de diretoria
- [ ] **Métricas** — abra `analytics/metrics_definitions.md` e valide (ou adapte) as definições de MRR, Churn, LTV e MAU para a realidade da empresa

> Após o setup, o agente consegue rotear qualquer pergunta de negócio para o pilar certo e responder com contexto específico da sua operação.

---

## 3. Uso diário

### Fluxos por situação

| Situação | Onde agir | Skill |
|---|---|---|
| Terminou um 1:1 com PM ou PD | `team_mgmt/1on1s/` | `/1on1-summary` |
| Terminou um 1:1 com liderança | `team_mgmt/leadership/1on1s/` | `/1on1-summary` |
| Precisa revisar ou calibrar um PRD | `product_execution/pilar_*/prds/` | `/product-review` |
| Vai iniciar novo ciclo de OKR | `strategy/okrs/` | `/okr-draft` |
| Precisa briefar PD para uma feature | `product_execution/pilar_*/` | `/design-brief` |
| Quer comunicar a semana para a diretoria | — | `/weekly-digest` |
| Design Crit quinzenal | `team_mgmt/rituals/templates/design-crit.md` | pauta pronta |
| Product Review quinzenal | `team_mgmt/rituals/templates/product-review.md` | pauta pronta |
| QBR trimestral | `team_mgmt/rituals/templates/qbr.md` | pauta pronta |
| Avaliar candidato a PM | `team_mgmt/hiring/scorecard-pm.md` | — |
| Avaliar candidato a PD | `team_mgmt/hiring/scorecard-pd.md` | — |

### Como invocar um skill

Com o Claude Code aberto dentro do diretório `Team OS - MGC/`, use:

```
/1on1-summary
/product-review
/okr-draft
/design-brief
/weekly-digest
```

O skill guia a interação — basta seguir as instruções que ele fornece.

### Cadência de rituais

Consulte `team_mgmt/rituals/calendar.md` para a visão completa. Resumo:

| Frequência | Ritual |
|---|---|
| Semanal | Reunião de liderança (30 min) + Sync de pilar (30 min) |
| Quinzenal | Design Crit (60 min) + Product Review (60 min) |
| Mensal | Revisão de métricas (60 min) + All-hands P&D (45 min) |
| Trimestral | Planning de roadmap + QBR + Ciclo de feedback de carreira |

---

## 4. Como o sistema evolui

**Claude não tem memória entre sessões. O filesystem é a memória.**

Cada vez que você usa o sistema e escreve algo, o contexto futuro fica mais rico:

| O que acumula | Onde | O que o agente passa a saber |
|---|---|---|
| Notas de 1:1 | `team_mgmt/1on1s/` | Padrões de comportamento, histórico de feedback, ações em aberto |
| PRDs aprovados | `product_execution/pilar_*/prds/` | Decisões de produto anteriores, hipóteses testadas |
| Ciclos de OKR | `strategy/okrs/` | Evolução do portfólio, o que funcionou ou não |
| Design briefs | `product_execution/pilar_*/` | Contexto de features em desenvolvimento |

**Regra de ouro:** qualquer decisão que você precisaria lembrar em 90 dias precisa estar em um arquivo.

**Quando rodar lint:** mensalmente, ou após qualquer mudança de time (novo PM, novo PD, pilar renomeado). O lint verifica arquivos desatualizados, CLAUDE.md com nomes antigos e referências quebradas.

---

## 5. Estrutura de diretórios

```
Team OS - MGC/
│
├── README.md                          ← este arquivo
├── CLAUDE.md                          ← índice raiz + team roster
│
├── .claude/
│   ├── CLAUDE.md                      ← índice de skills
│   └── skills/
│       ├── 1on1-summary.md            ← estrutura notas brutas de 1:1
│       ├── product-review.md          ← review de PRD com foco em problema e métricas
│       ├── okr-draft.md               ← rascunho de OKRs com KRs mensuráveis
│       ├── design-brief.md            ← briefing de design a partir de problema de produto
│       └── weekly-digest.md           ← digest executivo semanal para diretoria
│
├── team_mgmt/                         ← governança e gestão de pessoas
│   ├── 1on1s/                         ← histórico de 1:1s com ICs (um arquivo por pessoa)
│   ├── career_ladder/
│   │   ├── levels.md                  ← APM → PM → SPM → GPM
│   │   └── design_levels.md           ← PDJ → PD → SPD → Design Lead
│   ├── hiring/
│   │   ├── process.md                 ← funil seletivo e SLAs
│   │   ├── scorecard-pm.md            ← avaliação objetiva de candidatos PM
│   │   └── scorecard-pd.md            ← avaliação objetiva de candidatos PD
│   ├── leadership/
│   │   ├── roster.md                  ← mapa de líderes: reports, parceiros, diretoria
│   │   ├── alignment.md               ← princípios e cadência de alinhamento
│   │   └── 1on1s/                     ← histórico de 1:1s com lideranças
│   └── rituals/
│       ├── calendar.md                ← todos os rituais por frequência
│       └── templates/
│           ├── design-crit.md         ← pauta com regras de feedback
│           ├── product-review.md      ← perguntas calibradas para PRDs
│           └── qbr.md                 ← estrutura de 90 min para diretoria
│
├── strategy/                          ← direcional de alto nível
│   ├── vision.md                      ← propósito e diferenciais competitivos
│   └── okrs/                          ← ciclos OKR (YYYY-QN.md ou YYYY-HN.md)
│
├── product_execution/                 ← execução diária por pilar
│   ├── pilar_a/
│   │   ├── CLAUDE.md                  ← contexto: PM, PD, domínio de atuação
│   │   ├── prds/                      ← Product Requirements Documents
│   │   ├── customers/                 ← resumos de customer calls
│   │   └── discovery/                 ← experimentos e pesquisas quanti/quali
│   ├── pilar_b/                       ← mesma estrutura do pilar_a
│   └── pilar_c/                       ← mesma estrutura do pilar_a
│
└── analytics/                         ← fonte da verdade de dados
    ├── metrics_definitions.md         ← glossário oficial de métricas
    ├── queries/                        ← biblioteca SQL auditada
    └── schemas/                        ← documentação de tabelas
```

---

> **Próximo passo:** preencher o setup inicial acima. Enquanto os pilares tiverem nomes genéricos (Pilar A, B, C), o agente não consegue rotear perguntas de negócio com precisão.
