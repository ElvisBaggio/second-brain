# Segundo Cérebro — Sistema Híbrido GTD + Wiki

## Quem sou

Elvis — Product Manager / Liderança de Produto. Trabalho com times de produto, cloud, logística.
Uso este vault como segundo cérebro: captura tudo, processa com GTD, sintetiza conhecimento com wiki mantido por LLM.

---

## Identity and Role (LLM)

You are the co-maintainer of this second brain. You write and maintain all files inside `Wiki/`. You never modify files inside `Raw/`. The human owns everything else — GTD folders, Daily Notes, Templates. Your job is summarizing, cross-referencing, categorizing, filing, and bookkeeping inside the wiki.

---

## Directory Contract

| Path | Owner | Rule |
|---|---|---|
| `00 Inbox/` | Human | GTD capture. LLM reads only. |
| `01 Projects/` | Human | Active projects. LLM reads only unless asked. |
| `02 Areas/` | Human | Ongoing responsibilities. LLM reads only unless asked. |
| `03 Resources/` | Human | References and learning. LLM reads only unless asked. |
| `04 Archive/` | Human | Closed/inactive. LLM reads only. |
| `Raw/` | Human | Immutable source documents for the wiki. LLM reads only. Never create, edit, or delete files here. |
| `Raw/assets/` | Human | Images from clipped articles. LLM reads only. |
| `Wiki/` | LLM | LLM creates, updates, and maintains all files here. |
| `Wiki/index.md` | LLM | Master index. Updated on every ingest. |
| `Wiki/log.md` | LLM | Append-only log. Never edit past entries. |
| `Daily Notes/` | Human | Daily journal. LLM reads only unless asked. |
| `Templates/` | Human | Reusable templates. LLM reads only. |
| `CLAUDE.md` | Shared | Human and LLM co-evolve this file over time. |

---

## GTD System

### Philosophy
- **Capture first, process later** — everything goes to Inbox
- **GTD for action** — projects with defined outcome, areas for ongoing responsibilities
- **Wiki for knowledge** — concepts and sources synthesized and cross-linked by LLM

### Structure
```
00 Inbox/          ← quick capture, unprocessed
01 Projects/       ← defined outcome + clear next action
02 Areas/          ← ongoing responsibilities, no deadline
  Trabalho/
    1:1s/          ← one note per person, cumulative
  Pessoal/
  Financeiro/
03 Resources/      ← references, learnings, articles
  Produto/
  Tech/
  Liderança/
  Viagens/
04 Archive/        ← completed, inactive, or historical reference only
Daily Notes/       ← YYYY-MM-DD.md — journal + review
Templates/         ← reusable templates
```

### A note belongs in 01 Projects/ when:
- Has a defined final outcome
- Has at least one next action with `- [ ]`
- Is currently active

### A note belongs in 02 Areas/ when:
- Is an ongoing responsibility (e.g., 1:1 with someone, health, finances)
- Has no defined end

### Conventions

**Links**
- Always use `[[Note Name]]` to link related notes
- Each project note must link its related meeting and 1:1 notes
- Daily Notes link the projects worked on that day

**Tags**
- `#projeto` — active projects
- `#area` — areas of responsibility
- `#recurso` — reference and learning
- `#1:1` — 1:1 meetings
- `#trabalho` `#pessoal` `#financeiro` — domain
- `#someday` — someday/maybe backlog
- `#importante` — high priority

**Next actions**
- Use `- [ ]` for tasks within notes
- Project note must always have at least one open `- [ ]`

**1:1 notes**
- One note per person in `02 Areas/Trabalho/1:1s/`
- Format: `1:1 - Nome.md`
- Accumulates all meetings in chronological order

### Weekly Review (every Friday)
1. Process Inbox to zero
2. Review `01 Projects/` — does every project have a next action?
3. Review `02 Areas/` — did anything become a project?
4. Create week's Daily Note with summary

---

## Wiki System

### Wiki Page Format

Every wiki page (except `index.md` and `log.md`) must start with this YAML frontmatter:

```yaml
---
title: "Page title in Portuguese"
type: conceito | entidade | fonte | output
tags: []
created: YYYY-MM-DD
updated: YYYY-MM-DD
sources: 0
---
```

- `type`: one of `conceito`, `entidade`, `fonte`, or `output`
- `tags`: array of lowercase Portuguese tags, no spaces (use hyphens)
- `sources`: number of raw sources that contributed to this page
- After frontmatter, write the page body in Portuguese using markdown
- Always end every wiki page with a `## Referências` section listing backlinks using `[[Page Name]]` syntax

### Category Rules

- You may create subdirectories inside `Wiki/conceitos/` and `Wiki/entidades/` as needed
- Create a new category only when 3 or more pages clearly belong together
- Name categories in lowercase Portuguese with hyphens (e.g., `Wiki/conceitos/inteligencia-artificial/`)
- When creating a category, add a `_categoria.md` index file inside it

### `Wiki/index.md` Format

Read this first on every session. Structure:

```markdown
# Índice do Wiki

_Atualizado em: YYYY-MM-DD — X fontes ingeridas — X páginas_

## Conceitos
- [[Page Title]] — one-line summary (type: conceito, tags: tag1, tag2)

## Entidades
- [[Page Title]] — one-line summary (type: entidade)

## Fontes
- [[Page Title]] — one-line summary, source date

## Outputs
- [[Page Title]] — question or analysis that generated this output
```

Rules: keep alphabetical within each section, one line per page, update after every ingest/query/lint.

### `Wiki/log.md` Format

Append-only. Never edit past entries:

```markdown
## [YYYY-MM-DD] operação | Título ou descrição curta

- **Tipo:** ingestão | consulta | lint
- **Arquivo(s) afetado(s):** list of wiki pages created or updated
- **Resumo:** 1-3 sentences in Portuguese describing what was done
```

---

## Session Startup Checklist

At the start of every Claude Code session, before doing any work:

1. Read `CLAUDE.md` (this file) in full
2. Read `Wiki/index.md` to understand current wiki state
3. Read the last 5 entries in `Wiki/log.md` to understand recent activity
4. Confirm with the human what they want to do: ingest, query, lint, GTD processing, or other

---

## Ingest Workflow

When the human says "ingira", "processe" or drops a file in `Raw/` and asks you to process it:

1. Read the source file(s) from `Raw/`
2. Briefly discuss key takeaways (2-3 bullet points) and confirm emphasis
3. Create a `Wiki/fontes/` page summarizing the source (type: `fonte`)
4. Identify all concepts and entities — check `Wiki/index.md` for existing pages
5. For new concepts/entities: create their wiki pages
6. For existing pages: integrate new information, update `updated` and `sources` fields
7. A single source may touch 10-15 wiki pages — that is normal and expected
8. Update `Wiki/index.md`
9. Append entry to `Wiki/log.md`
10. Run `git add -A && git commit -m "ingest: [source title]"`

---

## Query Workflow

When the human asks a question against the wiki:

1. Read `Wiki/index.md` to identify relevant pages
2. Read the relevant pages in full
3. Synthesize an answer with citations to `[[Page Name]]`
4. Ask: "Quer que eu arquive esta resposta no wiki?" — if yes, create page in `Wiki/outputs/` (type: `output`)
5. If output is filed: update `Wiki/index.md` and append to `Wiki/log.md`
6. If output is filed: run `git add -A && git commit -m "query: [short description]"`

Output formats:
- Markdown page (default)
- Comparison table (markdown)
- Marp slide deck (save as `.md` with Marp frontmatter)
- Ask the human which format they prefer for complex queries

**Marp frontmatter template:**
```yaml
---
marp: true
theme: default
paginate: true
---
```

---

## Lint Workflow

When the human asks for "lint" or "saúde do wiki":

1. Read all wiki pages and `Wiki/index.md`
2. Check for: orphan pages, concepts without a page, contradictions, `sources: 0` pages, missing `## Referências`, index/file mismatches
3. Fix what you can autonomously; ask before judgment calls
4. Suggest 3-5 new questions or sources worth finding
5. Append lint entry to `Wiki/log.md`
6. Commit: `git commit -m "lint: [date] health check"`

---

## YouTube Ingestion (via MCP)

When the human shares a YouTube URL:

1. Use the YouTube MCP tool to fetch the transcript
2. Save as `Raw/[YYYY-MM-DD]-[video-title-slug].md` with frontmatter:
   ```yaml
   ---
   title: "Video title"
   url: "https://youtube.com/..."
   date: YYYY-MM-DD
   type: video-transcript
   ---
   ```
3. Then follow the standard ingest workflow

---

## Git Commit Conventions

```
ingest: [source title or slug]
query: [short description of question]
lint: [date] health check
wiki: [description of manual wiki improvement]
gtd: [GTD processing or reorganization]
chore: [maintenance task]
```

Always commit after ingest, after filing a query output, and after lint.

---

## Active Projects

- [[Produto MGC]] — principal projeto de produto
