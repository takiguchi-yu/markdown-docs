# Copilot instructions for markdown-docs

This repository is a personal Markdown documentation store, not a generated site.
Keep changes focused on the docs content and the Markdown tooling that enforces it.

## Build, format, and lint

- Install dependencies: `npm install`
- Format Markdown: `npm run format`
- Check formatting: `npm run format:check`
- Lint Markdown: `npm run lint`
- Auto-fix lint issues: `npm run lint:fix`

Single-file checks:

- Prettier: `npx prettier --check docs/path/to/file.md`
- markdownlint: `npx markdownlint docs/path/to/file.md`
- textlint: `npx textlint docs/path/to/file.md`

Notes:

- There is no separate application build step or test suite.
- `npm install` runs `simple-git-hooks` setup via `postinstall`.
- Pre-commit hooks run `npm run lint`.

## High-level architecture

- `docs/` is the main content root.
- `docs/README.md` is the entry point for the documentation tree.
- `docs/guides/` contains writing and operating guidelines.
- `docs/tutorials/` contains basic how-to content and examples.
- `docs/marp/` contains Marp slide sources and references.
- `themes/` contains slide-related assets such as theme CSS.

Validation is layered:

- Prettier handles formatting.
- markdownlint enforces Markdown structure.
- textlint enforces Japanese technical writing rules.

## Key conventions

- Use one H1 per file.
- Do not skip heading levels; keep headings in order.
- Put blank lines before and after headings and between paragraphs.
- Use `-` for unordered lists and `1.` for ordered lists.
- Keep prose and long lines aligned with the configured limits
  (`MD013` 80 chars, textlint sentence length max 125 chars).
- Prefer clear, descriptive link text and relative links inside the repo.
- For Japanese prose, keep notation consistent and end sentences cleanly so
  textlint does not flag mixed punctuation.
- When writing Marp slides, start with front matter like `---`, `marp: true`,
  and use `---` to split slides.

## Editing guidance

- Add new Markdown under `docs/` unless there is a strong reason not to.
- If you add a new doc category, update `docs/README.md` so the tree stays
  navigable.
- Reuse the existing file organization instead of creating parallel structures.
