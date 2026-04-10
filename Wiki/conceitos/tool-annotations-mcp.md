---
title: "Tool Annotations MCP"
type: conceito
tags: [mcp, tool-annotations, segurança, protocolo, agentic]
created: 2026-04-10
updated: 2026-04-10
sources: 1
---

# Tool Annotations MCP

Mecanismo do [[Model Context Protocol]] que permite a servidores declarar o **comportamento esperado** de cada ferramenta exposta, antes de ela ser executada.

## O que são

Anotações são metadados estáticos associados a uma ferramenta. Exemplos de categorias:

| Anotação | Significado |
|---|---|
| `read-only` | Não modifica estado externo |
| `destructive` | Pode apagar ou sobrescrever dados |
| `idempotent` | Executar N vezes = executar 1 vez |
| `reaches outside local environment` | Acessa rede, APIs, sistemas externos |

## Para que servem

- Permitem que hosts (agentes, clientes MCP) tomem decisões de segurança **antes** de executar
- Informam interfaces de usuário sobre o risco de cada ação
- Base para políticas de aprovação automática vs. confirmação humana em [[Agentic Workflows]]

## Limitações

As anotações são declarações estáticas — o servidor as define, mas não há mecanismo de verificação em runtime. Um servidor mal-implementado (ou malicioso) pode declarar `read-only` e ainda assim modificar estado.

## Estado atual (2026)

Introduzidas há ~1 ano. A comunidade abriu 5 [[Specification Enhancement Proposal|SEPs]] propondo extensões, refletindo experiência real de uso em produção e necessidade de granularidade maior para cenários de risco em workflows agênticos.

---

## Referências

- [[Model Context Protocol]]
- [[Model Context Protocol Blog — Tool Annotations]]
- [[Agentic Workflows]]
- [[Specification Enhancement Proposal]]
