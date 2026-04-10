# LLM Wiki — Full Setup Prompt

> **Usage:** Run this from the root of a new, empty Obsidian vault using Claude Code.  
> This prompt is self-contained. Claude Code will build the entire infrastructure.

---

You are being run from the root of a new Obsidian vault. Your job is to set up a complete LLM-maintained personal knowledge base (wiki) from scratch. Follow every instruction below precisely. When done, summarize what was created.

All **file content, note titles, category names, and wiki articles must be written in Portuguese (Brazil)**. System and config files (`.gitignore`, YAML keys, frontmatter field names) stay in English.

---

## 1. Create the directory structure

Create all directories and their initial placeholder files:

```
raw/                        ← immutable source documents (never modified by LLM)
raw/assets/                 ← images downloaded from clipped articles
wiki/                       ← LLM-generated and LLM-maintained knowledge
wiki/conceitos/             ← concept and topic pages
wiki/entidades/             ← people, companies, products, places
wiki/fontes/                ← one summary page per raw source
wiki/outputs/               ← Q&A answers, analyses, slide decks filed back
.gitignore
README.md
CLAUDE.md
wiki/index.md
wiki/log.md
```

For each directory, create a `.gitkeep` file so git tracks empty folders (except folders that will have real files immediately).

---

## 2. Initialize git

Run the following:

```bash
git init
git add .
git commit -m "chore: initial wiki setup"
```

---

## 3. Create `.gitignore`

```gitignore
.DS_Store
*.heic
*.tiff
.obsidian/workspace.json
.obsidian/workspace-mobile.json
```

---

## 4. Create `README.md`

Write a README in Portuguese explaining:
- This is a personal knowledge base maintained by an LLM (Claude Code)
- The human curates sources; the LLM writes and maintains the wiki
- Directory structure overview (raw, wiki, CLAUDE.md)
- How to ingest a new source (drop in raw/, tell Claude Code to process it)
- How to query the wiki (open Claude Code and ask a question)
- Required Obsidian plugins (list in section 8)
- Required MCPs (list in section 9)

---

## 5. Create `CLAUDE.md`

This is the most important file. It is the schema that all future Claude Code sessions will read to understand how to operate this wiki. Write it in English. It must contain the following sections:

### 5.1 Identity and role

> You are the maintainer of this personal knowledge base. You write and maintain all files inside `wiki/`. You never modify files inside `raw/`. The human's job is to curate sources, ask questions, and guide direction. Your job is summarizing, cross-referencing, categorizing, filing, and bookkeeping.

### 5.2 Directory contract

| Path | Owner | Rule |
|---|---|---|
| `raw/` | Human | Immutable. LLM reads only. Never create, edit, or delete files here. |
| `raw/assets/` | Human | Images from clipped articles. LLM reads only. |
| `wiki/` | LLM | LLM creates, updates, and maintains all files here. |
| `wiki/index.md` | LLM | Master index. Updated on every ingest. |
| `wiki/log.md` | LLM | Append-only log. Never edit past entries. |
| `CLAUDE.md` | Shared | Human and LLM co-evolve this file over time. |

### 5.3 Wiki page format

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
- Always end every wiki page with a `## Referências` section listing backlinks to related pages using `[[Page Name]]` syntax

### 5.4 Category rules

- You may create subdirectories inside `wiki/conceitos/` and `wiki/entidades/` as needed — no predefined categories
- Create a new category only when 3 or more pages clearly belong together
- Name categories in lowercase Portuguese with hyphens (e.g., `wiki/conceitos/inteligencia-artificial/`)
- When creating a category, add a `_categoria.md` index file inside it summarizing what belongs there

### 5.5 `wiki/index.md` format

This file is your navigation tool. Read it first on every session to understand the current state of the wiki before doing any work.

Structure:

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

Rules:
- Keep entries alphabetical within each section
- One line per page — no sub-bullets
- Update this file at the end of every ingest, query (if output is filed), or lint pass

### 5.6 `wiki/log.md` format

Append-only. Never edit past entries. Each entry follows this format:

```markdown
## [YYYY-MM-DD] operação | Título ou descrição curta

- **Tipo:** ingestão | consulta | lint
- **Arquivo(s) afetado(s):** list of wiki pages created or updated
- **Resumo:** 1-3 sentences in Portuguese describing what was done
```

Start every entry header with `## [YYYY-MM-DD]` so it is grep-parseable.

### 5.7 Ingest workflow

When the human says "ingira", "processe" or drops a file in `raw/` and asks you to process it:

1. Read the source file(s) from `raw/`
2. Briefly discuss key takeaways with the human (2-3 bullet points) and confirm emphasis
3. Create a `wiki/fontes/` page summarizing the source (frontmatter type: `fonte`)
4. Identify all concepts and entities mentioned — check `wiki/index.md` to see which already have pages
5. For new concepts/entities: create their wiki pages
6. For existing pages: open them, integrate the new information, update `updated` and `sources` fields
7. A single source may touch 10-15 wiki pages — that is normal and expected
8. Update `wiki/index.md` with any new or changed entries
9. Append an entry to `wiki/log.md`
10. Run `git add -A && git commit -m "ingest: [source title]"`

### 5.8 Query workflow

When the human asks a question against the wiki:

1. Read `wiki/index.md` to identify relevant pages
2. Read the relevant pages in full
3. Synthesize an answer with citations to `[[Page Name]]`
4. Ask the human: "Quer que eu arquive esta resposta no wiki?" — if yes, create a page in `wiki/outputs/` (frontmatter type: `output`)
5. If output is filed: update `wiki/index.md` and append to `wiki/log.md`
6. If output is filed: run `git add -A && git commit -m "query: [short description]"`

Output formats available depending on the query:
- Markdown page (default)
- Comparison table (markdown)
- Marp slide deck (save as `.md` with Marp frontmatter, viewable in Obsidian with Marp plugin)
- Ask the human which format they prefer for complex queries

**Marp frontmatter template** (use when output format is slides):
```yaml
---
marp: true
theme: default
paginate: true
---
```

### 5.9 Lint workflow

When the human asks for a "lint" or "saúde do wiki":

1. Read all wiki pages and `wiki/index.md`
2. Check for and report:
   - Pages with no inbound `[[backlinks]]`
   - Concepts mentioned in multiple pages but lacking their own page
   - Contradictions between pages (flag with exact quotes)
   - Pages with `sources: 0` that should cite something
   - Missing `## Referências` sections
   - Entries in `index.md` that don't match actual files
3. Fix what you can autonomously; ask the human before making judgment calls
4. Suggest 3-5 new questions worth investigating or sources worth finding
5. Append lint entry to `wiki/log.md`
6. Commit: `git commit -m "lint: [date] health check"`

### 5.10 YouTube ingestion (via MCP)

When the human shares a YouTube URL and asks you to ingest it:

1. Use the YouTube MCP tool to fetch the video transcript
2. Save the raw transcript as `raw/[YYYY-MM-DD]-[video-title-slug].md` with frontmatter:
   ```yaml
   ---
   title: "Video title"
   url: "https://youtube.com/..."
   date: YYYY-MM-DD
   type: video-transcript
   ---
   ```
3. Then follow the standard **ingest workflow** (section 5.7) on the saved transcript

### 5.11 Session startup checklist

At the start of every Claude Code session, before doing any work:

1. Read `CLAUDE.md` (this file) in full
2. Read `wiki/index.md` to understand current wiki state
3. Read the last 5 entries in `wiki/log.md` to understand recent activity
4. Confirm with the human what they want to do: ingest, query, lint, or other

### 5.12 Git commit conventions

```
ingest: [source title or slug]
query: [short description of question]
lint: [date] health check
wiki: [description of manual wiki improvement]
chore: [maintenance task]
```

Always commit after ingest, after filing a query output, and after lint.

---

## 6. Create `wiki/index.md`

Initial content:

```markdown
# Índice do Wiki

_Atualizado em: [today's date] — 0 fontes ingeridas — 0 páginas_

## Conceitos
_Nenhum ainda._

## Entidades
_Nenhuma ainda._

## Fontes
_Nenhuma ainda._

## Outputs
_Nenhum ainda._
```

---

## 7. Create `wiki/log.md`

Initial content:

```markdown
# Log do Wiki

Registro cronológico de todas as operações. Nunca editar entradas anteriores.

---

## [TODAY_DATE] setup | Inicialização do wiki

- **Tipo:** setup
- **Arquivo(s) afetado(s):** todos (criação inicial)
- **Resumo:** Wiki criado do zero. Estrutura de diretórios, CLAUDE.md, index.md e log.md inicializados. Repositório git inicializado.
```

Replace `TODAY_DATE` with today's actual date.

---

## 8. Obsidian plugins to install (add this to `README.md`)

Tell the human to install the following plugins in Obsidian (Settings → Community Plugins):

| Plugin | Purpose |
|---|---|
| **Dataview** | Query wiki pages by frontmatter (type, tags, date, sources) |
| **Marp Slides** | View and export Marp slide decks from within Obsidian |
| **Obsidian Web Clipper** | Clip web articles directly to `raw/` as markdown |
| **Git** | Visual git history and auto-commit from within Obsidian |

Also tell the human to configure in Obsidian Settings → Files and Links:
- Set **"Attachment folder path"** to `raw/assets`
- Bind a hotkey to **"Download attachments for current file"** (Settings → Hotkeys → search "Download") — recommended: `Ctrl+Shift+D` / `Cmd+Shift+D`

---

## 9. MCP setup (add this to `README.md`)

The following MCPs enhance Claude Code's capabilities for this wiki:

### YouTube MCP
Enables automatic video transcription for ingestion.

Instruct the human to add to their Claude Code MCP config (`~/.claude/mcp_servers.json` or via `claude mcp add`):

```json
{
  "youtube": {
    "command": "npx",
    "args": ["-y", "@kimtaeyoon83/mcp-server-youtube-transcript"]
  }
}
```

Or via CLI:
```bash
claude mcp add youtube -- npx -y @kimtaeyoon83/mcp-server-youtube-transcript
```

After setup, YouTube URLs can be ingested with: "Ingira este vídeo: [URL]"

---

## 10. Final steps

After creating all files and directories:

1. Run `git add -A`
2. Run `git commit -m "chore: initial wiki setup"`
3. Print a summary to the human with:
   - List of all files and directories created
   - Instructions for next steps (install plugins, configure Web Clipper, add YouTube MCP)
   - How to do the first ingest: "Salve um artigo em raw/ com o Web Clipper e me diga: 'Ingira o arquivo [nome].md'"
   - How to query: "Me diga: 'O que o wiki sabe sobre [tema]?'"

---

_This prompt was designed to be run once. After setup, CLAUDE.md governs all future sessions._
