# LLM Wiki Agent Instructions

This repository is a reusable LLM Wiki template. Follow these rules when maintaining a wiki created from this template.

## Core Model

- `raw/` is the immutable source layer. Read files there, but do not edit, rename, summarize in place, or delete them.
- `wiki/` is the maintained knowledge layer. Create and update markdown pages there.
- `AGENTS.md` is the operating schema. Update it only when the wiki workflow itself changes.
- Prefer Obsidian-compatible wiki links like `[[page-name]]` for internal wiki references.
- Use kebab-case filenames, for example `llm-wiki-pattern.md` or `andre-karpathy.md`.

## Directory Roles

- `raw/sources/`: user-provided source documents.
- `raw/assets/`: local images, PDFs, screenshots, and attachments referenced by sources.
- `wiki/index.md`: content-oriented catalog of wiki pages.
- `wiki/log.md`: chronological append-only activity log.
- `wiki/overview.md`: high-level synthesis of the current wiki.
- `wiki/sources/`: one page per source document.
- `wiki/entities/`: people, organizations, products, places, and other named entities.
- `wiki/concepts/`: ideas, theories, terms, patterns, and frameworks.
- `wiki/syntheses/`: cross-source analyses, comparisons, and evolving theses.
- `wiki/questions/`: durable answers to useful user questions.
- `wiki/_templates/`: page templates.
- `tools/`: optional scripts and local search tooling.

## Workflow: ingest

Use this workflow when the user adds a source to `raw/sources/` and asks you to process it.

1. Read the source and identify key claims, entities, concepts, dates, and evidence.
2. Create or update a matching page in `wiki/sources/` using `wiki/_templates/source.md`.
3. Update related pages in `wiki/entities/`, `wiki/concepts/`, and `wiki/syntheses/`.
4. Add or refresh links in `wiki/index.md`.
5. Append an entry to `wiki/log.md` with the format `## [YYYY-MM-DD] ingest | Title`.
6. Mention contradictions, uncertainty, and open questions instead of smoothing them over.

## Workflow: query

Use this workflow when answering questions against the wiki.

1. Read `wiki/index.md` first.
2. Open the most relevant wiki pages and synthesize an answer from them.
3. Cite source pages or wiki pages with links.
4. If the answer is durable, create or update a page in `wiki/questions/` or `wiki/syntheses/`.
5. Append an entry to `wiki/log.md` with the format `## [YYYY-MM-DD] query | Question`.

## Workflow: lint

Use this workflow when asked to health-check the wiki.

- Find contradictions between pages.
- Find stale claims superseded by newer sources.
- Find orphan pages with no inbound links.
- Find important mentioned concepts that lack pages.
- Find missing cross-references.
- Find data gaps that need more sources.
- Record material maintenance work in `wiki/log.md` with the format `## [YYYY-MM-DD] lint | Scope`.

## Writing Standards

- Keep pages concise, structured, and easy to scan.
- Preserve source provenance. Do not present source-specific facts without a source reference.
- Separate facts, interpretation, uncertainty, and open questions.
- Prefer updating existing pages over creating duplicates.
- Do not invent sources or citations.
- Do not modify files under `raw/` unless the user explicitly asks.

## Commit Standards

- When creating commits, follow `docs/commit-convention.md`.
