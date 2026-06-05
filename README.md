# LLM Wiki

A reusable template for building an LLM-maintained wiki from curated source material.

This project follows the pattern described in `docs/en.md` and `docs/ko.md`: keep raw sources immutable, let the LLM maintain a structured markdown wiki, and use `AGENTS.md` as the operating schema.

## Structure

```text
.
├── AGENTS.md
├── docs/
├── raw/
│   ├── sources/
│   └── assets/
├── wiki/
│   ├── index.md
│   ├── log.md
│   ├── overview.md
│   ├── sources/
│   ├── entities/
│   ├── concepts/
│   ├── syntheses/
│   ├── questions/
│   └── _templates/
└── tools/
```

## Quick Start

1. Add source documents to `raw/sources/`.
2. Ask an LLM agent to ingest the source using `AGENTS.md`.
3. Browse the generated wiki from `wiki/index.md`.
4. Keep durable analyses in `wiki/syntheses/` or `wiki/questions/`.

`raw/` is for user-provided source material. `wiki/` is for LLM-maintained knowledge. `tools/` is optional and can stay empty until search or automation becomes useful.
