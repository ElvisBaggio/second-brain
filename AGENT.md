# Briefing — Segundo Cérebro (para agentes)

Você está operando o segundo cérebro de Elvis (Product Manager). Este vault combina GTD para ação e um wiki mantido por LLM para conhecimento. Leia este documento e siga as regras antes de fazer qualquer coisa.

---

## Regra de ouro

- **Você escreve apenas em `Wiki/`**
- **Você nunca toca em `Raw/`** (leitura apenas)
- **Tudo o mais pertence ao humano** (leitura apenas, salvo pedido explícito)

---

## Startup obrigatório (toda sessão)

```
1. Ler Wiki/index.md        → entender estado atual da wiki
2. Ler últimas 5 entradas de Wiki/log.md → entender atividade recente
3. Confirmar com o humano: ingerir, consultar, lint, GTD ou outro?
```

---

## Workflows

### Ingestão (`ingira`, `processe`)

```
1. Checar Wiki/index.md → seção ## Fontes
   Se o arquivo já tem uma fonte correspondente: avisar e parar.
2. Ler o arquivo em Raw/
3. Discutir 2-3 pontos principais e confirmar ênfase
4. Criar Wiki/fontes/<slug>.md  (type: fonte)
5. Identificar conceitos e entidades → checar index.md
   - Novo: criar página em Wiki/conceitos/ ou Wiki/entidades/
   - Existente: integrar info, atualizar campos updated e sources
6. Atualizar Wiki/index.md
7. Append em Wiki/log.md
8. git add -A && git commit -m "ingest: [título]"
```

### Consulta (pergunta sobre o wiki)

```
1. Ler Wiki/index.md → identificar páginas relevantes
2. Ler as páginas relevantes
3. Responder com citações [[Page Name]]
4. Perguntar: "Quer arquivar esta resposta no wiki?"
   - Se sim: criar Wiki/outputs/<slug>.md, atualizar index, append log, commit
```

### Lint (`lint`, `saúde do wiki`)

```
1. Ler todas as páginas wiki e index.md
2. Checar: páginas órfãs, conceitos sem página, sources: 0, ## Referências ausente, divergências index/arquivo
3. Corrigir o que puder autonomamente; perguntar antes de julgamentos
4. Sugerir 3-5 novas perguntas ou fontes
5. Append log, commit "lint: [data] health check"
```

---

## Estrutura de diretórios

```
Wiki/
  index.md          ← índice mestre (sempre atualizar)
  log.md            ← append-only (nunca editar entradas passadas)
  fontes/           ← uma página por fonte Raw/ ingerida
  conceitos/        ← ideias, frameworks, mecanismos abstratos
  entidades/        ← organizações, pessoas, projetos concretos
  outputs/          ← respostas arquivadas de queries

Raw/                ← LEITURA APENAS. nunca criar, editar ou deletar.
  clippings/        ← artigos clippados
  assets/           ← imagens

00 Inbox/           ← captura GTD (leitura apenas)
01 Projects/        ← projetos ativos (leitura apenas)
02 Areas/           ← responsabilidades contínuas (leitura apenas)
03 Resources/       ← referências (leitura apenas)
04 Archive/         ← inativo (leitura apenas)
```

---

## Formato de páginas wiki

```yaml
---
title: "Título em português"
type: conceito | entidade | fonte | output
tags: [tag-em-portugues]
created: YYYY-MM-DD
updated: YYYY-MM-DD
sources: N
---
```

- Corpo em **português**
- Sempre terminar com `## Referências` com backlinks `[[Page Name]]`
- Links internos: sempre `[[Nome da Página]]`

---

## Formato do index.md

```markdown
# Índice do Wiki
_Atualizado em: YYYY-MM-DD — X fontes ingeridas — X páginas_

## Conceitos
- [[Título]] — resumo de uma linha (type: conceito, tags: ...)

## Entidades
- [[Título]] — resumo de uma linha (type: entidade)

## Fontes
- [[Título]] — resumo de uma linha, data da fonte

## Outputs
- [[Título]] — pergunta ou análise que gerou o output
```

---

## Commits

```
ingest: [título da fonte]
query: [descrição curta]
lint: [data] health check
wiki: [melhoria manual]
gtd: [reorganização GTD]
chore: [manutenção]
```

---

## Contexto do humano

- Elvis, PM, foco em produto, cloud, logística
- Projeto principal ativo: [[Produto MGC]]
- Wiki é novo — crescerá por ingestão progressiva de Raw/

> Para detalhes completos, ver `CLAUDE.md` na raiz do vault.
