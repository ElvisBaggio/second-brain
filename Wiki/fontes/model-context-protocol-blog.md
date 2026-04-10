---
title: "Model Context Protocol Blog — Tool Annotations"
type: fonte
tags: [mcp, tool-annotations, agentic-workflows, protocolo]
created: 2026-04-10
updated: 2026-04-10
sources: 1
---

# Model Context Protocol Blog — Tool Annotations

**Origem:** [blog.modelcontextprotocol.io](https://blog.modelcontextprotocol.io/)
**Arquivo local:** `Raw/clippings/Model Context Protocol Blog.md`
**Data de ingestão:** 2026-04-10
**Autor:** [[The MCP Project]]

---

## Resumo

O artigo discute o estado atual das **tool annotations** no [[Model Context Protocol]], mecanismo introduzido há cerca de um ano para que servidores MCP descrevam o comportamento de suas ferramentas.

Desde a introdução, a comunidade submeteu cinco [[Specification Enhancement Proposal|SEPs]] independentes propondo novas anotações — reflexo de um entendimento coletivo mais maduro sobre onde o risco realmente vive em [[Agentic Workflows|workflows agênticos]].

O post oferece:
- Um retrospecto do que as tool annotations fazem hoje
- Uma análise honesta do que elas **não conseguem** fazer de forma realista
- Um framework para avaliar novas propostas de anotação

---

## Pontos-chave

- Tool annotations existem para descrever comportamento: `read-only`, `destructive`, `idempotent`, `reaches outside local environment`
- 5 SEPs foram abertos pela comunidade após uso em produção revelar lacunas
- O risco em workflows agênticos não é trivial de capturar apenas com anotações estáticas

---

## Referências

- [[Model Context Protocol]]
- [[Tool Annotations MCP]]
- [[Agentic Workflows]]
- [[Specification Enhancement Proposal]]
- [[The MCP Project]]
