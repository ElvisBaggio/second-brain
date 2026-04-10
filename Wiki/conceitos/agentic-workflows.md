---
title: "Agentic Workflows"
type: conceito
tags: [agentes, ia, automação, risco, llm]
created: 2026-04-10
updated: 2026-04-10
sources: 1
---

# Agentic Workflows

Fluxos de trabalho em que um agente de IA (geralmente um LLM) executa sequências de ações de forma autônoma — chamando ferramentas, tomando decisões e iterando — com supervisão humana reduzida ou nenhuma.

## Características

- O agente decide **quais ferramentas** chamar e **em qual ordem**
- Ações podem ter efeitos colaterais reais: escrever arquivos, enviar e-mails, modificar bancos de dados
- A cadeia de ações pode ser longa e difícil de auditar em tempo real

## Onde o risco vive

Em workflows agênticos, o risco não está só em "o que a ferramenta faz", mas em:

1. **Composição** — uma sequência de ações individually seguras pode ter efeito destrutivo combinado
2. **Contexto** — a mesma ferramenta é segura em um contexto e perigosa em outro
3. **Irreversibilidade** — ações destrutivas ou externas são difíceis de desfazer
4. **Escala** — um agente pode repetir um erro milhares de vezes antes de ser interrompido

## Relação com MCP

O [[Model Context Protocol]] é infraestrutura crítica para workflows agênticos — define como agentes acessam ferramentas. As [[Tool Annotations MCP|tool annotations]] existem especificamente para dar ao agente (e ao host) informação suficiente para gerenciar risco nesse contexto.

---

## Referências

- [[Model Context Protocol]]
- [[Tool Annotations MCP]]
- [[Model Context Protocol Blog — Tool Annotations]]
