# GTD + Wiki com Claude — Como usar

## A pergunta que organiza tudo

> **"Isso é algo que preciso fazer ou algo que preciso saber?"**
> - Preciso **fazer** → GTD (pastas `00` a `04`)
> - Preciso **saber** → Wiki (pasta `Wiki/`, Claude mantém)

---

## Fluxo completo

```
CAPTURA
  └── qualquer coisa → 00 Inbox/

VOCÊ PROCESSA (GTD)
  ├── tarefa/projeto?      → 01 Projects/ ou 02 Areas/
  ├── artigo/fonte/vídeo?  → Raw/  →  peça ao Claude: "ingira"
  ├── referência rápida?   → 03 Resources/ (você organiza)
  └── não precisa mais?    → 04 Archive/ ou deleta

CLAUDE PROCESSA (Wiki)
  Raw/ → Claude lê → Wiki/ (conceitos, entidades, fontes, outputs)
```

---

## Onde cada coisa vive

| O que é | Onde vai | Quem cuida |
|---|---|---|
| Ideia solta, tarefa, captura rápida | `00 Inbox/` | Você |
| Projeto com entregável definido | `01 Projects/` | Você |
| Responsabilidade contínua (1:1, área) | `02 Areas/` | Você |
| Referência leve (link, nota rápida) | `03 Resources/` | Você |
| Artigo, PDF, transcrição para estudar | `Raw/` | Você salva, Claude processa |
| Conceito sintetizado | `Wiki/conceitos/` | Claude |
| Pessoa, empresa, produto | `Wiki/entidades/` | Claude |
| Resumo de fonte | `Wiki/fontes/` | Claude |
| Resposta ou análise arquivada | `Wiki/outputs/` | Claude |

---

## Comandos do dia a dia (Claude Code)

### GTD
| O que fazer | O que dizer ao Claude |
|---|---|
| Processar o Inbox | `"processa meu inbox"` |
| Weekly Review | `"weekly review"` |
| Ver próximas ações | `"quais são minhas próximas ações abertas?"` |
| Fechar projeto | `"fecha o projeto [nome] e arquiva"` |
| Registrar 1:1 | `"adiciona ao 1:1 de [nome]: [anotações]"` |

### Wiki
| O que fazer | O que dizer ao Claude |
|---|---|
| Ingerir arquivo | `"ingira o arquivo [nome].md"` |
| Ingerir vídeo | `"ingira este vídeo: [URL]"` |
| Consultar conhecimento | `"o que o wiki sabe sobre [tema]?"` |
| Comparar conceitos | `"compare [A] e [B]"` |
| Gerar slides | `"crie slides sobre [tema]"` |
| Checar saúde do wiki | `"saúde do wiki"` ou `"lint"` |

---

## O ciclo GTD clássico (não muda)

```
CAPTURAR → PROCESSAR → ORGANIZAR → REVISAR → FAZER
```

Ao processar cada item do Inbox:
- É acionável? → cria `- [ ]` próxima ação
- Leva menos de 2 min? → faz na hora
- É referência para estudar? → vai para `Raw/` e ingere no wiki
- É projeto? → vai para `01 Projects/`
- É algum dia/talvez? → tag `#someday`
- É lixo? → deleta

---

## Rotinas sugeridas

### Diária (5 min)
1. Capture tudo no `00 Inbox/`
2. Crie sua Daily Note e linke o que trabalhou

### Semanal — toda sexta (15 min)
1. Processe o Inbox até zerar
2. Revise `01 Projects/` — todo projeto tem próxima ação?
3. Revise `02 Areas/` — algo virou projeto?
4. Diga: *"weekly review"*

### Sob demanda
- Sempre que ler algo importante → salve em `Raw/` e diga *"ingira"*
- Antes de pesquisar algo → pergunte ao wiki primeiro

---

## Regras de ouro

1. **Capture tudo no Inbox** — não tente organizar na hora
2. **Raw/ é imutável** — só adicione, nunca edite o que está lá
3. **Wiki/ é do Claude** — não edite manualmente
4. **GTD é seu** — Claude só mexe nas pastas `00–04` se você pedir
5. **Pergunte antes de pesquisar** — se o wiki já sabe, use o que está lá

---

## Links úteis
- [[CLAUDE.md]] — instruções do sistema para o Claude
- [[Wiki/index]] — índice do wiki
- [[Templates/Daily Note]] — template do diário
- [[Templates/1:1]] — template de 1:1
- [[Templates/Projeto]] — template de projeto
- [[01 Projects/Produto MGC/INDEX]] — projeto principal
- [[02 Areas/Trabalho/Dashboard]] — hub de trabalho
