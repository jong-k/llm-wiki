# Raw Sources

This directory contains source material selected by the user.

Rules:

- Treat this directory as immutable input.
- LLM agents may read files here but should not edit them.
- Put articles, notes, transcripts, PDFs, exports, and other source files in `raw/sources/`.
- Put downloaded images, screenshots, PDFs, and attachments in `raw/assets/`.
- Summaries and interpretations belong in `wiki/`, not here.

Large files can be kept out of git with project-specific `.gitignore` rules if needed.
