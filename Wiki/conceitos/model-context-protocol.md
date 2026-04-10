---
title: "Model Context Protocol"
type: conceito
tags: [mcp, protocolo, llm, ferramentas, ia]
created: 2026-04-10
updated: 2026-04-10
sources: 1
---

# Model Context Protocol (MCP)

Protocolo aberto criado pelo [[The MCP Project]] que padroniza como aplicações de IA (especialmente LLMs) se conectam a ferramentas, fontes de dados e serviços externos.

## O que é

MCP define uma interface entre um **host** (ex: Claude, um agente) e **servidores** que expõem capacidades — ferramentas, recursos, prompts. O protocolo elimina a necessidade de integrações customizadas ponto-a-ponto.

## Por que importa

- Permite que agentes acessem contexto externo de forma padronizada
- Facilita composição de ferramentas de diferentes fornecedores
- Base para [[Agentic Workflows]] mais seguros e auditáveis

## Componentes principais

| Componente | Papel |
|---|---|
| Host | Aplicação que usa o LLM (ex: Claude Code) |
| Servidor MCP | Expõe ferramentas/recursos via protocolo |
| [[Tool Annotations MCP\|Tool Annotations]] | Descrevem comportamento de cada ferramenta |
| [[Specification Enhancement Proposal\|SEPs]] | Processo de evolução do protocolo |

## Evolução

O protocolo evolui via [[Specification Enhancement Proposal|SEPs]] submetidos pela comunidade. A área de [[Tool Annotations MCP|tool annotations]] é ativa — 5 SEPs abertos com propostas de novas anotações.

---

## Referências

- [[Model Context Protocol Blog — Tool Annotations]]
- [[Tool Annotations MCP]]
- [[Agentic Workflows]]
- [[Specification Enhancement Proposal]]
- [[The MCP Project]]
