---
title: Métricas e Acompanhamento
tags:
  - processo
  - produto
  - métricas
  - okr
aliases:
  - Metrics
  - Acompanhamento
---

# 📊 Métricas e Acompanhamento

> [!abstract] Objetivo
> Definir como medir progresso, saúde dos times e impacto das entregas em todos os níveis do processo.

Voltar para [[Processo de Produto]]

---

## Metric Tree

```
              NORTH STAR METRIC
              (ex: Weekly Active Engaged Users)
              ┌──────────┼──────────┐
              │          │          │
        Acquisition  Activation  Retention
        ┌───┴──┐    ┌───┴──┐    ┌───┴──┐
        │      │    │      │    │      │
     Signups  Qual  Setup  TTV  D7    D30
       Rate   Rate  Rate   Days Ret   Ret
```

> [!tip] Como usar
> Cada tribo deve ser dona de uma parte da árvore. A North Star é responsabilidade do Head de Produto, mas cada PM influencia seus input metrics.

---

## OKR Scoring

| Score | Significado | Ação |
|-------|------------|------|
| **0.0 - 0.3** | ❌ Falhou | Root cause analysis obrigatório |
| **0.4 - 0.6** | ⚠️ Progresso parcial | Avaliar se continua ou pivota |
| **0.7 - 1.0** | ✅ Sucesso | Celebrar + documentar learnings |
| **> 1.0** | 🎯 Meta muito fácil | Recalibrar para ser mais ambicioso |

> [!note] Regra de Ouro dos OKRs
> Se você está atingindo 100% dos OKRs consistentemente, suas metas não são ambiciosas o suficiente. O sweet spot é **70% de atingimento**.

---

## Health Metrics por Tribo

Monitorar semanalmente via dashboard no Jira:

| Métrica | O que mede | 🟢 Saudável | 🟡 Atenção | 🔴 Crítico |
|---------|-----------|-------------|-----------|-----------|
| Sprint Velocity Trend | Previsibilidade | Variação < 15% | 15-30% | > 30% |
| Discovery Pipeline | Ideias em validação | ≥ 5 em validating | 3-4 | < 3 |
| Cycle Time | Ideia → produção | < 4 semanas | 4-6 semanas | > 6 semanas |
| Blocked Items | Itens parados | 0 | 1-2 | > 2 por > 3 dias |
| OKR Progress (mid-Q) | % atingimento | > 40% | 25-40% | < 25% |
| Bug Escape Rate | Bugs em produção | < 5% | 5-10% | > 10% |

---

## Cadência de Review

| Cadência | O que revisar | Quem |
|----------|--------------|------|
| **Diária** | Blockers, anomalias críticas | PM + Squad |
| **Semanal** | Health metrics, velocity, pipeline | Head + PMs |
| **Mensal** | OKR progress, feature adoption | PMs + Analytics |
| **Trimestral** | OKR scoring, Big Rock progress | Head + PMs + Stakeholders |
| **Semestral** | Estratégia, market metrics | Head + C-Level |

---

## Feature Success Metrics

Toda feature entregue deve ser medida em 4 dimensões:

| Dimensão | Métrica | Quando medir |
|----------|---------|-------------|
| **Adoption** | % de usuários usando | Semana 1-2 |
| **Frequency** | Uso por usuário por período | Semana 2-4 |
| **Depth** | % da funcionalidade utilizada | Semana 4-8 |
| **Retention** | Uso continuado ao longo do tempo | Mês 2-3 |

---

Ver também: [[4- Execução Semanal]] · [[3- Ciclo Trimestral]] · [[Template - Quarterly Review]]
