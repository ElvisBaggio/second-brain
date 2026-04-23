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

# 👥 Governança RACI v2 (Topologia de Pilares)

> [!abstract] Objetivo
> Clareza de quem decide, executores, quem é consultado e quem é informado em cada tipo de decisão sob a estrutura de Pilares.

Voltar para [[Processo de Produto v2]]

---

> [!note] Legenda RACI
> **R** = Responsible (executa) · **A** = Accountable (decide) · **C** = Consulted · **I** = Informed · **F** = Facilitator (orquestra o processo, não decide)

> [!tip] Sobre a função Governança
> **Governança** é a função que garante que as cerimônias estratégicas acontecem — preparando materiais, facilitando sessões e documentando decisões. Opera exclusivamente na camada Head + GPM + C-Level. Contexto operacional em `Team OS - MGC/governance/`.

---

## Decisões Estratégicas

| Decisão | Head de Produto | GPM (Líder do Pilar) | PM de Domínio | Tech Lead | Design Lead | Stakeholder | Governança |
|---------|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| Visão de Produto | **A** | **R** | C | C | C | I | **F** |
| Estratégia & Big Rocks | **A** | **R** | C | C | C | C | **F** |
| OKRs Anuais | **A** | **R** | **R** | C | C | I | **F** |
| Alocação cross-pilar | **A/R** | **C** | — | C | — | I | **F** |
| Revisão Semestral / Avaliação Topologia | **A** | **R** | C | C | C | I | **F** |
| Cross-Pilar Alignment (Q) | C | **R** | — | — | — | — | **F** |
| OKR Portfolio Health | **A** | C | — | — | — | — | **R** |

---

## Decisões Táticas

| Decisão | Head de Produto | GPM do Pilar | PM de Domínio | Tech Lead | Design Lead |
|---------|:---:|:---:|:---:|:---:|:---:|
| Iniciativas do Q | I | **A** | **R** | **R** | **R** |
| Priorização de backlog | I | C | **A/R** | C | C |
| Quebra em Épicos | — | I | **A** | **R** | C |
| Sprint planning | — | — | C | **A/R** | C |
| Kill/Pivot de iniciativa | **A** | **R** | **R** | C | C |
| Feature spec / PRD | — | I | **A/R** | C | **R** |

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
PM de Domínio tenta resolver
    │
    ├── Resolveu → ✅ Segue
    │
    └── Não resolveu (cross-domínio no mesmo Pilar)
         │
         ▼
    GPM (Líder do Pilar)
         │
         ├── Resolveu → ✅ Segue
         │
         └── Não resolveu (cross-pilar, estratégico, topo)
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
