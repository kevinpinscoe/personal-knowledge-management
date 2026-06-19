# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A curated **public example** of an Obsidian-based personal knowledge management (PKM) vault. It is not software — there is no build, lint, or test suite. Work is almost entirely Markdown editing and vault organization.

This repo is derived from a separate **private** working vault. It is not that vault, a backup, or a complete mirror. Read `AGENTS.md` before changing content — it defines the public-scope boundary in full. The hard rule: keep all changes inside this repository and never import, sync, or copy from `~/KnowledgeVault/personal-knowledge-base` or any other external/private vault unless the user explicitly asks.

## Core model

The system separates four concerns, and understanding this separation is the key to working here:

```text
Folders (moc/, notes/, ...) = storage    — a note lives in exactly one place on disk
Maps of Content (moc/*.md)  = navigation — a note can be linked from many MOCs
Links / [[backlinks]]       = relationships
LCC-inspired frontmatter    = broad subject orientation (routing aid, not formal cataloging)
```

Because navigation lives in MOCs (not folders), folders stay shallow. The canonical example: `notes/qa76-linux-systemd-timers.md` is linked from `moc/linux.md` and could later be linked from automation/ops/systemd MOCs without being moved or copied. `home.md` is the Obsidian entry point and links only to deliberately-promoted top-level MOCs; `README.md` is the public entry point.

A note carries its display title, aliases, `classification` (e.g. `QA76`), `classification_label`, `primary_moc`, `related_mocs`, `tags`, and `created`/`updated` in YAML frontmatter. Classification codes come from the Library of Congress outlines in `lcc/lcco-*.md` — consult the relevant `lcco-<class>.md` when classifying a note or MOC.

## Conventions that are easy to get wrong

- **Filenames** must be lowercase, no spaces, hyphen-separated (`rules/file-naming-rules.md`). This applies to *file and directory names only* — frontmatter `title`, `aliases`, `classification_label`, MOC names, headings, and tags use normal capitalization/spaces/codes. Exceptions allowed to be uppercase: `README.md`, `AGENTS.md`, `RUNBOOK.md`.
- **MOC filenames** use plain topic slugs (`moc/linux.md`), with the classification code stored in frontmatter — not in the filename. Ordinary notes *may* carry a broad LCC-style prefix in the filename as a shelf marker (`qa76-...`) when useful.
- Start new content from the matching skeleton in `templates/` (`note-template.md`, `moc-note-template.md`, `runbook-template.md`, `reference-note-template.md`, `daily-note-template.md`).
- Journal entries are dated `journal/YYYY-MM-DD.md`.
- When a requested change conflicts with a file in `rules/`, prefer the rule and surface the conflict to the user rather than silently overriding it.

## Placement (which directory)

`moc/` navigation hubs · `notes/` evergreen notes · `runbooks/` operational procedures · `references/` source summaries / external research · `lcc/` LoC class outlines · `journal/` dated notes · `attachments/` images & supporting files · `templates/` skeletons · `archive/` retired content · `docs/` vault-design material · `rules/` ground-rule conventions · `scripts/` maintenance utilities.

## Empty placeholders — do not treat as work

Several required directories are present but empty (tracked via `.gitkeep`) only to demonstrate the layout — `archive/`, `references/`, `runbooks/`, `scripts/`, `docs/`, `ingest/`, `ingest-holding/`. Per `AGENTS.md`'s 2026-06-19 verification, these are **not** active queues: `ingest/` and `ingest-holding/` hold no migration backlog, and `scripts/` has no maintenance script. Do not invent content to fill them, do not document non-existent scripts, and do not recreate the removed legacy uppercase `Ingest/` or optional `uncategorized/` directories or describe their removal as pending.

> Note: `rules/rules-directory-layout.md` describes the fuller working-vault model and states this explicitly. Where it disagrees with `AGENTS.md` about what should exist *in this public repo*, `AGENTS.md` controls.

## Commands

- `rg "term"` — search notes and rules.
- `rg --files` — inspect the published file set before referencing repo content.
- `git status --short` — review pending changes before editing.

Commit with Conventional Commit messages scoped to the area touched, e.g. `docs(readme): clarify scope`, `feat(notes): add systemd timer example`, `fix(moc): repair sample note link`.
