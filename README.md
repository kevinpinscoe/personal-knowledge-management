# Personal Knowledge Management Workflow — Public Example

In my model, the chief difference between PCM and PKM is purpose. PCM is an evolving research library: it gathers ideas, evidence, possibilities, questions, and connections that may inform what I do next. PKM is more practical and operational: it records what I built, what I did, what I purchased, the decisions I made, and how I operate and maintain what I have.

Put another way, PCM reads more like a cookbook of possibilities, while PKM reads more like the owner’s manual for my actual life, tools, projects, and systems.

PCM is primarily prospective and exploratory. PKM is primarily retrospective and operational.

This repository is a curated, public demonstration of how I organize an Obsidian-based personal knowledge management system. It reflects the structure and workflow of my separate working vault, but it is not the working vault, a backup of it, or a complete publication of its contents.

The repository exists to demonstrate the system using a limited set of safe examples. Private notes, journals, attachments, active project records, purchasing information, and other personal or operational material are intentionally excluded.


## What this example demonstrates

The system separates four concerns:

```text
Folders                 = storage
Maps of Content (MOCs)  = navigation and context
Links and backlinks     = relationships
LCC-inspired metadata   = broad subject orientation
```

A note has one location on disk, but it can be linked from several MOCs. This keeps the folder structure shallow without forcing a note into only one subject.

The classification model is inspired by the Library of Congress Classification (LCC). It is used as a practical routing aid, not as a claim of formal library cataloging.

## Included MOC-to-note example

The clearest example in this repository is:

- [`moc/linux.md`](moc/linux.md) — a topic-level Map of Content
- [`notes/qa76-linux-systemd-timers.md`](notes/qa76-linux-systemd-timers.md) — an evergreen note linked from that MOC

The note uses `qa76` as a broad shelf marker for computer software. Its detailed metadata and human-readable title remain in frontmatter, while the Linux MOC provides the main navigation path.

Conceptually:

```text
Linux MOC
└── Linux systemd timers
```

On disk:

```text
moc/linux.md
notes/qa76-linux-systemd-timers.md
```

The same note could later be linked from MOCs for automation, operations, or systemd without being copied or moved.

## Workflow

When adding a note:

1. Decide whether the material is an evergreen note, MOC, runbook, reference, or journal entry.
2. Identify its main subject and consult the relevant `lcc/lcco-*.md` outline when classification is useful.
3. Start from the matching file in `templates/`.
4. Give the file a lowercase, hyphenated name. Evergreen notes may use a broad lowercase LCC-style prefix.
5. Add a human-friendly title and classification metadata in frontmatter.
6. Link the note from the most relevant MOC and add related MOC links where they improve retrieval.
7. Revisit MOCs as the collection grows; they are curated navigation pages, not automatic indexes.

For example, a Linux note may be classified broadly under computer software:

```yaml
title: "Linux systemd timers"
type: note
classification: QA76
classification_label: Computer software
classification_source: lcc
primary_moc: Linux
tags:
  - linux
  - systemd
  - automation
```

The resulting filename is descriptive but intentionally less formal than a complete library call number:

```text
notes/qa76-linux-systemd-timers.md
```

## Repository layout

```text
.
├── README.md       — public introduction to the example
├── AGENTS.md       — repository guidance for coding and AI agents
├── TODO.md         — open housekeeping tasks for the vault owner
├── home.md         — Obsidian entry point for the published sample
├── .obsidian/      — sanitized Obsidian settings for testing the sample
├── moc/            — Maps of Content used for navigation
├── notes/          — evergreen sample notes
├── runbooks/       — procedural notes
├── references/     — source summaries and external research
├── templates/      — reusable note skeletons
├── lcc/            — local LCC lookup material
├── attachments/    — supporting files used by notes
├── journal/        — dated notes when included in a vault
├── archive/        — retired or superseded material
├── docs/           — material about the vault design
├── scripts/        — optional vault-maintenance utilities
└── rules/          — naming and layout conventions
```

Some directories are empty placeholders because this repository demonstrates the workflow without publishing the corresponding private content. The private working vault may contain additional files, directories, links, and conventions that are not represented here.

## Conventions

- Keep filenames lowercase, with hyphens instead of spaces.
- Keep ordinary notes in `notes/` and navigation pages in `moc/`.
- Prefer shallow folders and explicit links over deep topic trees.
- Use frontmatter for display titles, aliases, classifications, tags, and status.
- Use MOCs as curated entry points rather than exhaustive generated lists.
- Treat `lcc/` as a lookup aid for broad classification decisions.
- MOC files must use this section order: **Overview → Child MOCs → Notes → Related MOCs**. Child MOCs must always come before Notes so the drill-down path is visible before individual note listings.

See [`rules/file-naming-rules.md`](rules/file-naming-rules.md), [`rules/rules-directory-layout.md`](rules/rules-directory-layout.md), [`rules/moc-section-order.md`](rules/moc-section-order.md), and the files in [`templates/`](templates/) for the detailed working conventions represented by this example.

## Using this repository

You can browse the Markdown files directly or open the repository as an Obsidian vault. If you adapt the approach, copy the ideas and templates that are useful rather than assuming this reduced public sample is a complete, ready-made personal vault.

Contributors and automated agents should read [`AGENTS.md`](AGENTS.md) before changing content. In particular, changes must remain scoped to this public repository and must not import material from the separate private vault.

## Related: Personal Context Management

This repository complements my other public repo, [personal-context-management](https://github.com/kevinpinscoe/personal-context-management) (PCM).

The two solve different problems:

- **Personal Knowledge Management (PKM)** — this repo — is about managing *what I know*: durable notes, references, and the maps of content that connect them.
- **Personal Context Management (PCM)** is about managing *what should already be known before helping me act*: the standing context, preferences, and conventions an assistant needs up front.

PKM is the body of knowledge; PCM is the context that should be loaded before working with it.

## License

See [`LICENSE`](LICENSE).
