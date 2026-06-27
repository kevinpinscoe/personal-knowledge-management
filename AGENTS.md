# Repository Guidelines

## Public Repository Scope

This repository is a curated public example derived from a separate private Obsidian vault. It demonstrates the owner's PKM workflow; it is not the live vault, a backup, or a complete mirror.

Keep changes limited to the files in this repository. Do not inspect, copy from, synchronize with, or otherwise depend on `~/KnowledgeVault/PKM` or any other external vault unless the user explicitly requests that work. Do not bulk-import private notes, journals, attachments, configuration, or history. Prefer a small, coherent set of sample MOCs and matching notes suitable for public consumption.

`README.md` is the public entry point for the repository. `home.md` is the internal Obsidian entry point for the published sample and should link only to MOCs intentionally included here.

## Project Structure & Module Organization

Use `moc/` for Maps of Content, `notes/` for evergreen notes, `runbooks/` for operational procedures, and `references/` for source summaries or external research. Store reusable note skeletons in `templates/`, LCC lookup material in `lcc/`, attachments in `attachments/`, and vault conventions in `rules/`.

The sanitized `.obsidian/` configuration is published so this repository can be opened directly as an Obsidian vault. Keep Obsidian Sync disabled and do not commit workspace history, recent-file entries, or paths from the private vault.

The rule files describe the fuller vault model and are retained to explain the workflow. This public example does not need to contain every private-vault artifact named by those rules. Do not create missing directories or placeholder content solely to make the sample resemble the private vault.

Repository verification as of 2026-06-19:

- The obsolete uppercase `Ingest/` directory is absent.
- The optional `uncategorized/` directory is absent.
- `ingest/` and `ingest-holding/` contain only `.gitkeep` placeholders; they are not active cleanup queues and no migration task should be inferred from them.
- `home.md` contains the deliberately limited navigation published with this sample.
- `scripts/` currently contains no executable maintenance script.

Do not recreate removed legacy directories or describe their removal as pending work. If empty demonstration placeholders are later removed, update this section and the README together.

## Development Commands

There is no application build step or automated test suite. Most work is Markdown editing and vault organization.

- `rg "term"`: search notes and rules quickly.
- `rg --files`: inspect the published file set before referring to repository content.
- `git status --short`: review pending changes and avoid overwriting unrelated user work.

Do not document or invoke maintenance scripts unless they actually exist in this repository. If a script is added, document its external tools and controlled verification procedure.

## Style & Naming Conventions

Follow `rules/file-naming-rules.md`: filenames should be lowercase, contain no spaces, and use hyphens for readability. Conventional top-level documents such as `README.md` and `AGENTS.md` are exceptions.

Use the files in `templates/` when creating sample content and include relevant frontmatter. Prefer human-friendly `title` values and aliases for display names. Classified evergreen notes may use a lowercase LCC-style prefix, for example `notes/qa76-linux-systemd-timers.md`. Top-level MOC filenames should use plain topic slugs such as `moc/linux.md`, with classification stored in frontmatter.

When a shell script is explicitly added, use Bash with `set -euo pipefail` unless the script has a documented reason not to.

## Content and Validation Guidelines

Before adding or relocating a note, read the relevant files in `rules/` and consult the appropriate `lcc/lcco-*.md` file when classification is needed. Link a new sample note from an appropriate MOC when one exists.

Validate changes by checking:

- Markdown readability and frontmatter consistency.
- Internal links and the existence of linked sample files.
- Placement and filenames against the repository rules.
- Public suitability; do not expose personal, secret, or private-vault content.
- Scope; avoid broad cleanup or publication of unrelated copied material.

The public-example scope in this file controls whether content should be published. The detailed rules control how approved sample content is named, classified, and placed.

## Commit & Pull Request Guidelines

Use Conventional Commit-style messages such as `docs(readme): clarify public example scope`, `feat(notes): add systemd timer example`, or `fix(moc): repair sample note link`.

Pull requests should describe the content or structure changed, list moved or renamed files, identify any intentional rule exception, and confirm that newly published material is appropriate for a public repository. Include screenshots only when rendered Obsidian behavior matters.
