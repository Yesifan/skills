# Initialize the spec location

## Choose a location and create an index

- Ask the user where specs should be maintained. If the user has already specified a location or the project has one configured, use it without asking again.
- Create or update `README.md` in the selected directory to index all existing specs, including those in subdirectories. Use links relative to the README and a one-sentence purpose for each entry.

README template:

```markdown
# Specifications

Specs record agreed behavior, scope, and implementation decisions. Check a spec's status before using it to guide implementation.

## Index

| Spec | Purpose | Status | Execution time |
| ---- | ------- | ------ | -------------- |

## Maintenance

- Add a relative link and a one-sentence purpose for every spec in the index.
- When implementing a spec, align the documentation and code so they remain consistent.
- Update the index when a spec is added, renamed, moved, or removed, or when its purpose, status, or execution time changes. The spec's metadata is the source of truth for its status and execution time in the index.
- Keep completed specs unchanged. For subsequent changes, create a new spec that links to the earlier spec and explains which agreements it replaces, adjusts, or extends. Record the relationship between the specs in the index as well.
```

## Add project rules when creating the first spec

When creating the first spec, add the following rule to `AGENTS.md` in the project root. Merge it with any equivalent rules already present to avoid duplication.

The template path `docs/specs/README.md` is an example. Replace it with the actual index location, using a link relative to the project root's `AGENTS.md`. Use this rule to find the spec location on subsequent runs.

```markdown
## Specifications

Before adding, editing, or implementing a spec, read the [spec index and maintenance rules](docs/specs/README.md) and follow them when maintaining specs and the index.
```
