---
title: "Qubit"
type: conceito
tags: [computacao-quantica, fisica-quantica, hardware]
created: 2026-04-10
updated: 2026-04-10
sources: 1
---

# Qubit

Unidade fundamental de informação em [[Computação Quântica]]. Enquanto o **bit** clássico representa apenas 0 ou 1, o qubit pode existir em **superposição** — uma combinação de 0 e 1 simultaneamente — até o momento em que é medido.

## Implementação física

Qubits são implementados usando partículas subatômicas como elétrons ou fótons. Sua instabilidade intrínseca é tanto a fonte do poder quântico quanto o principal desafio de engenharia.

## Por que qubits são poderosos

Com N qubits em superposição, um computador quântico pode representar e processar 2ᴺ estados simultaneamente. Com 300 qubits, isso supera o número de átomos estimado no universo observável — tornando certas classes de problemas resolvíveis em tempo viável.

## Fragilidade: decoerência quântica

Qubits são extremamente sensíveis a perturbações externas (ruído eletromagnético, variações de temperatura). Qualquer interferência causa **decoerência quântica** — o qubit "colapsa" para um estado definido prematuramente, introduzindo erros nos cálculos. Por isso, processadores quânticos operam a temperaturas próximas do zero absoluto (-273°C).

## Diferença do bit clássico

| | Bit | Qubit |
|---|---|---|
| Estados possíveis | 0 ou 1 | 0, 1, ou superposição de ambos |
| Processamento | Sequencial | Paralelo (exponencial) |
| Correção de erros | Simples | Complexa — não pode ser copiado diretamente (no-cloning theorem) |
| Sensibilidade | Robusto | Extremamente frágil |

## Referências

- [[Computação Quântica]]
- [[O que é um computador quântico? — Tecnoblog]]
