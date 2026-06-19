# Required Repository Directory Layout

This rule defines the minimum directory layout for this knowledge base.

This rule describes the fuller working-vault model. For what should actually exist in this public example repository, `AGENTS.md` is authoritative: where this rule and `AGENTS.md` disagree about whether a directory, template, or queue should be present here, follow `AGENTS.md`. Do not create directories, templates, or placeholder content solely to make this sample resemble the private vault.

When scaffolding or repairing the repository, create every required directory and every required file listed below. Example topic files are shown only to explain where content belongs; do not create example files unless they are specifically needed.

## Required Files

- `home.md`

## Required Directories

- `moc/`
- `notes/`
- `runbooks/`
- `references/`
- `lcc/`
- `journal/`
- `attachments/`
- `templates/`
- `archive/`
- `docs/`
- `scripts/`
- `rules/`

## Empty Directory Convention

When a required directory is empty, place a `.gitkeep` file inside it so git tracks the directory. Remove the `.gitkeep` once real content is added.

## Required Templates

Create these files inside `templates/`:

- `moc-note-template.md`
- `note-template.md`
- `runbook-template.md`
- `reference-note-template.md`
- `daily-note-template.md`

## Inbound / Holding Directories

These directories are inbound holding areas in the working vault. In this public example they exist as empty `.gitkeep` placeholders only and are **not** active cleanup queues — do not infer any migration or triage backlog from them, and do not move content into them as part of unrelated work.

- `ingest/` — raw inbound material awaiting triage.
- `ingest-holding/` — staging area for inbound material being processed.

The obsolete uppercase `Ingest/` directory has been removed. Do not recreate it or describe its removal as pending work.

## Optional Directories

These directories are not required and are absent from this public example. Do not create them solely to match the private vault. They are recognized and governed by this rule only if a user deliberately adds them:

- `uncategorized/` — temporary holding area for notes that arrived without a clear home. If present, triage regularly; notes here should either be promoted, linked, classified, archived, or deleted.

## Example Layout

The following tree shows the expected organization. Files marked as examples are illustrative only and are not required.

```text
.
├── home.md
├── moc/
│   └── linux.md                             # example
├── notes/
│   └── qa76-linux-kernel.md                 # example
├── runbooks/
│   └── check-loaded-kernel-modules.md       # example
├── references/
│   └── linux-kernel-documentation.md        # example
├── lcc/
│   ├── lcco-q.md                            # example — Science class outline from LoC
│   └── lcco-t.md                            # example — Technology class outline from LoC
├── journal/
│   └── 2026-06-15.md                        # example
├── attachments/
│   └── linux-kernel-boot-flow.png           # example
├── templates/
│   ├── moc-note-template.md
│   ├── note-template.md
│   ├── runbook-template.md
│   ├── reference-note-template.md
│   └── daily-note-template.md
├── archive/
│   └── old-linux-kernel-index.md            # example
├── docs/
│   └── vault-design-reference.md            # example
├── scripts/
│   └── download-lcc-outline.sh             # example
├── rules/
│   └── rules-directory-layout.md           # example
├── ingest/                                  # inbound holding (empty placeholder here)
├── ingest-holding/                          # inbound staging (empty placeholder here)
└── uncategorized/                           # optional; absent in this example
```

## Placement Rules

- Put map-of-content notes in `moc/`.
- Put evergreen notes in `notes/` using a broad lowercase LCC-style prefix in the filename when useful (e.g. `qa76-linux-systemd-timers.md`). Group by topic subdirectory only when volume warrants it.
- Put step-by-step operational procedures in `runbooks/`.
- Put source summaries, documentation links, and external research notes in `references/`.
- Put LCC outline files downloaded from the Library of Congress in `lcc/`. When classifying a new note or MOC, read the relevant `lcco-<class>.md` file to identify the correct class code and label.
- Put dated daily notes in `journal/` using `YYYY-MM-DD.md`.
- Put images, PDFs, and other supporting files in `attachments/`.
- Put reusable note templates in `templates/`.
- Put retired or superseded content in `archive/`.
- Put reference material used when researching and shaping vault structure in `docs/`. Track and push all files not excluded by `.gitignore`.
- Put utility scripts for ingesting articles or modifying vault content in `scripts/`.
- Put vault ground rules in `rules/`. If a requested change conflicts with a rule, prefer the rule or explicitly document the exception.
- If `uncategorized/` exists, triage it regularly — promote, classify, archive, or delete notes; do not leave them there indefinitely.
- Treat `ingest/` and `ingest-holding/` as inbound holding areas. In this public example they are empty placeholders, not active queues; do not infer migration work from them or move unrelated content into them.
