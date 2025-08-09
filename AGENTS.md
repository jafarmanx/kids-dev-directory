# Repository Guidelines

This repository curates child development resources as Markdown files. Keep contributions simple, well-organized, and source-referenced.

## Project Structure & Module Organization

- root: `README.md` (overview), `AGENTS.md` (this guide)
- content: `resources/<source>/<topic>/<slug>.md`
  - Example: `resources/childdevelopmentinstitute/ages-and-stages/toddler-development.md`
- misc: `GEMINI.md` (alt readme), optional local config in `.env.local` (do not commit secrets).

## Build, Test, and Development Commands

This is a content-first repo; there is no build step. Helpful local checks (use if installed):

- `markdownlint **/*.md`: Lints Markdown style.
- `prettier -w **/*.md`: Formats Markdown consistently.
- `find resources -type f -name "*.md" | wc -l`: Counts articles for a quick sanity check.
- `grep -R "http" resources | wc -l`: Quick link inventory before running a link-checker.

## Coding Style & Naming Conventions

- Markdown: Start files with a single `# Title`, then `##` sections.
- Filenames/dirs: lowercase kebab-case (e.g., `positive-parenting-techniques.md`).
- Links: Prefer absolute source URLs; include text that clearly names the source.
- Tone: Neutral, informative, non-promotional. Keep paragraphs short; prefer bulleted lists.
- Metadata: If needed, add a short “Sources” section at the end.

## Testing Guidelines

- Minimum: Files render without syntax errors; headings are properly nested.
- Optional tools (if available): `markdown-link-check` or `lychee` for broken links; `markdownlint` for style.
- PRs adding many files should sample-check links across sources/topics.

## Commit & Pull Request Guidelines

- Commits: Present tense, imperative, scoped path first when helpful.
  - Example: `resources: add toddler development tips (CDI)`
- PRs: Include summary, examples of added paths, and source URLs.
  - Link related issues; add screenshots only if rendering is relevant.
- Keep changes focused: content additions or small fixes per PR.

## Security & Configuration Tips

- Never commit API keys or secrets. Use local `.env.local` and add it to `.gitignore`.
- If adding scraping/import scripts later, place them under `scripts/` with a short `scripts/README.md` describing setup and rate-limit/robots.txt compliance.

