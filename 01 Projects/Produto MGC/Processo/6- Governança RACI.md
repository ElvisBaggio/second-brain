---
title: Governança RACI
tags:
  - processo
  - produto
  - governança
  - raci
aliases:
  - RACI
  - Governance
---

# 👥 Governança RACI

> [!abstract] Objetivo
> Clareza de quem decide, quem executa, quem é consultado e quem é informado em cada tipo de decisão.

Voltar para [[Processo de Produto]]

---

> [!note] Legenda RACI
> **R** = Responsible (executa) · **A** = Accountable (decide) · **C** = Consulted · **I** = Informed

---

## Decisões Estratégicas

| Decisão | Head de Produto | PM de Tribo | Tech Lead | Design Lead | Stakeholder |
|---------|:---:|:---:|:---:|:---:|:---:|
| Visão de Produto | **A** | C | C | C | I |
| Estratégia & Big Rocks | **A** | **R** | C | C | C |
| OKRs Anuais | **A** | **R** | C | C | I |
| Alocação cross-tribo | **A/R** | C | C | — | I |
| Revisão Semestral (go/no-go) | **A** | **R** | C | C | I |

---

## Decisões Táticas

| Decisão | Head de Produto | PM de Tribo | Tech Lead | Design Lead |
|---------|:---:|:---:|:---:|:---:|
| Iniciativas do Q | C | **A** | **R** | **R** |
| Priorização de backlog | I | **A/R** | C | C |
| Quebra em Épicos | I | **A** | **R** | C |
| Sprint planning | — | C | **A/R** | C |
| Kill/Pivot de iniciativa | **A** | **R** | C | C |
| Feature spec / PRD | I | **A/R** | C | **R** |

---

## Princípios de Governança

> [!tip] Regras de Ouro
> 1. **Quem decide, decide.** Consultar ≠ pedir permissão.
> 2. **Disagree and commit.** Após a decisão, todos remam na mesma direção.
> 3. **Decisões reversíveis** podem ser tomadas rapidamente pelo PM.
> 4. **Decisões irreversíveis** (cortar produto, mudar estratégia) escalam ao Head.
> 5. **Transparência por padrão.** Decisões são documentadas e comunicadas.

---

## Escalation Path

```
Blocker no Squad
    │
    ▼
PM de Tribo tenta resolver
    │
    ├── Resolveu → ✅ Segue
    │
    └── Não resolveu (cross-tribo, estratégico, ou recurso)
         │
         ▼
    Head de Produto
         │
         ├── Resolveu → ✅ Segue
         │
         └── Não resolveu (precisa de negócio/C-level)
              │
              ▼
         Stakeholders / C-Level
```

---

Ver também: [[Processo de Produto]] · [[1- Planejamento Anual]] · [[3- Ciclo Trimestral]]
