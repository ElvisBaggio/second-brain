---
title: "Computação Quântica"
type: conceito
tags: [computacao-quantica, hardware, fisica-quantica, ia, ciberseguranca]
created: 2026-04-10
updated: 2026-04-10
sources: 1
---

# Computação Quântica

Paradigma de computação que usa princípios da mecânica quântica — superposição, entrelaçamento e interferência — para realizar cálculos complexos exponencialmente mais rápidos do que computadores clássicos para determinadas classes de problemas.

## Como funciona

Em vez de bits (0 ou 1), computadores quânticos usam [[Qubit|qubits]], que operam em **superposição** de estados (0 e 1 simultaneamente). Isso permite explorar um número exponencialmente maior de possibilidades em paralelo.

Os três princípios fundamentais são:

| Princípio | Descrição |
|-----------|-----------|
| **Superposição** | Um qubit existe em múltiplos estados ao mesmo tempo, não apenas 0 ou 1 |
| **Entrelaçamento quântico** | Dois ou mais qubits correlacionados — medir um afeta instantaneamente o outro, permitindo operações em grandes conjuntos de dados |
| **Interferência quântica** | Amplifica ou cancela probabilidades de estados, corrigindo erros e maximizando a chance de obter o resultado correto |

O componente central é o **processador quântico**, responsável por manipular os qubits e executar os algoritmos.

## Aplicações

- **Farmacêutica:** simulação de reações bioquímicas para descoberta de medicamentos e pesquisa de DNA
- **Cibersegurança:** criação de criptografia pós-quântica mais robusta; quebra de criptografias clássicas (RSA)
- **Inteligência Artificial:** aceleração de treinamento de modelos de ML e otimização de algoritmos
- **Finanças:** otimização de portfólios e detecção de fraudes em grandes volumes de dados
- **Logística:** otimização de recursos e planejamento urbano
- **Química:** desenvolvimento de novos materiais com propriedades específicas

## Desafios e limitações

- **Decoerência quântica:** qubits são extremamente sensíveis a ruído eletromagnético e variações de temperatura — qualquer perturbação causa erros nos cálculos
- **Correção de erros:** não é possível corrigir qubits como bits tradicionais; a decoerência torna isso um problema em aberto
- **Custo:** hardware quântico custa >US$ 100 mil; operação exige grande espaço físico e energia robusta
- **Complexidade de programação:** requer profundo conhecimento de mecânica quântica e álgebra linear

## Relação com computadores clássicos

Computadores quânticos **não substituem** os clássicos. São complementares:
- **Clássico:** versátil, eficiente para tarefas cotidianas (internet, documentos, aplicativos)
- **Quântico:** especializado em problemas de alta complexidade combinatória, simulações e otimização

## Acesso via nuvem

Para pesquisadores e empresas sem hardware próprio, Amazon (AWS Braket) e Microsoft (Azure Quantum) oferecem acesso à computação quântica como serviço.

## Histórico

| Ano | Marco |
|-----|-------|
| ~1959 | Richard Feynman propõe que computadores quânticos poderiam simular sistemas quânticos eficientemente |
| 1985 | David Deutsch descreve portas lógicas quânticas |
| 1994 | Peter Shor cria o primeiro algoritmo de fatoração quântica (Algoritmo de Shor) |
| 1998 | Primeiro computador quântico com 2 qubits construído por Isaac Chuang, Neil Gershenfeld e Mark Kubinec |
| 2019 | Google Sycamore atinge supremacia quântica: resolve em segundos problema que levaria 10.000 anos no clássico |

## Referências

- [[Qubit]]
- [[O que é um computador quântico? — Tecnoblog]]
