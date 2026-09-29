---
name: writing-doc
description: "Write or revise documentation, including skills, AGENTS.md, and reference documents loaded on demand."
disable-model-invocation: true
---

# Writing Docs

## Content Selection

> Less is more

- Document information unavailable from the current environment: implicit conventions, personal preferences, reasons behind decisions, and similar context.
- Maintain a single source of truth.
  - For information already available in code, documentation, configuration, or tool output, provide only a pointer and a brief explanation.
- Preserve necessary conditions and exceptions when simplifying.

## Information Organization

- Each project must have a central documentation index so readers can determine where information lives and when to read it without opening every file.
  - Update the index whenever documents are added, moved, or deleted.
- When a document covers multiple use cases and forces the model to read substantial irrelevant material, consider splitting it into a router and supporting pages.
  - Split along clear usage boundaries. If the model must move back and forth between files to make a single decision, the split adds cognitive overhead.

## Maintenance Tradeoffs

> When adding or splitting documents, weigh the benefits of loading content on demand against the costs of finding it, navigating between files, and keeping updates in sync.

- Archive older content that remains useful for historical reference. Delete content that no longer serves a purpose, and remove its incoming references.
