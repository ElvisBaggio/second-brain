---
title: Planejamento Anual
tags:
  - processo
  - produto
  - planejamento
  - anual
aliases:
  - Annual Planning
---

# 🎯 Planejamento Anual v2 (Janeiro)

> [!abstract] Objetivo
> Definir **visão, estratégia, Big Rocks, OKRs anuais e Topologia de Pilares** que orientam toda a organização por 12 meses.

Voltar para [[Processo de Produto v2]]

---

## Participantes

| Papel | Responsabilidade |
|-------|-----------------|
| Head de Produto | Facilita, define visão e estratégia, aprova Big Rocks, avalia macro topologia |
| GPMs e PMs de Domínio | Propõem Big Rocks dos seus domínios, definem OKRs de Pilar e indicam gaps de alocação/skills |
| Líderes de Engenharia | Viabilidade técnica, capacidade, dívida técnica |
| Design Leads | Visão de experiência, research pendente |
| Stakeholders de Negócio | Contexto de mercado, metas de negócio, restrições |

---

## Cadência (3-4 semanas em Janeiro)

### Semana 1 — Inputs, Contexto & Topologia
- Retrospectiva do ano anterior (métricas, aprendizados)
- Inputs de negócio (revenue targets, mercado, competição)
- **Review de Topologia e Skills** (Gaps, vagas abertas, background da equipe)
- Research consolidado (discovery acumulado)

### Semana 2 — Strategy Workshop
- Diagnóstico: Qual é o problema central?
- Política orientadora: Onde vamos focar e o que NÃO faremos
- Big Rocks: 3-5 apostas estratégicas para o ano
- Draft de OKRs anuais

### Semana 3 — Alinhamento entre Pilares
- Cada GPM/PM apresenta como Big Rocks se traduzem no seu pilar/domínio
- Identificação de dependências cross-pilar
- Calibragem de OKRs (evitar overlap, garantir cobertura)

### Semana 4 — Finalização & Comunicação
- Documento de Estratégia finalizado
- OKRs aprovados
- Comunicação para toda a organização

---

## Artefatos Produzidos

| Artefato | Template | Onde Vive |
|----------|---------|-----------|
| Visão de Produto (12 meses) | Documento narrativo (From → To) | Confluence |
| Estratégia de Produto | [[Template - Estratégia de Produto]] | Confluence |
| Big Rocks (3-5) | [[Template - Big Rock]] | **Jira Product Discovery** |
| OKRs Anuais | Objetivos + Key Results | Confluence + Jira (labels) |
| Mapa de Dependências | Diagrama visual | Miro |

---

## Fluxo do Planejamento

```mermaid
graph LR
    A[Inputs + Topologia] --> B[Strategy Workshop]
    B --> C[Definir Big Rocks]
    C --> D[Draft OKRs]
    D --> E[Alinhamento Pilares]
    E --> F[Calibragem OKRs]
    F --> G[Comunicação]
```

> [!warning] Atenção
> O planejamento anual **não é uma lista de features**. É sobre **outcomes, macro-alocações e apostas estratégicas**. Features serão definidas trimestralmente pelos pilares.

---

## Checklist de Qualidade

- [ ] Diagnóstico é específico e baseado em evidência
- [ ] Topologia endereça as deficiências de background e prioridades
- [ ] Política orientadora restringe foco (diz o que NÃO fazer)
- [ ] Big Rocks são apostas com outcomes mensuráveis
- [ ] OKRs são ambiciosos mas atingíveis (stretch goals)
- [ ] Todos os pilares entendem como contribuem
- [ ] Dependências cross-pilar estão mapeadas
- [ ] Comunicação feita para toda a organização

---

Ver também: [[2- Revisão Semestral v2]] · [[3- Ciclo Trimestral]] · [[6- Governança RACI v2]]
