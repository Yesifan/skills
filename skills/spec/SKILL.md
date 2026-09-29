---
name: spec
description: "Turn the current discussion and codebase context into a spec, and initialize or maintain the project's spec directory and index."
disable-model-invocation: true
---

# Spec

Create a spec from the current conversation and project context. Explore the project first to resolve uncertainties; ask the user about decisions and questions that remain unresolved.

## Initialization

If the spec location is unknown or its directory lacks a `README.md`, follow the [initialization guide](references/initialization.md). If the project's `AGENTS.md` does not yet link to the spec index and maintenance rules, add that entry as described in the guide.

## Writing a Spec

1. Explore the current codebase as needed, read related specs, use the project's terminology, and respect relevant architectural decisions. Do not repeat exploration when the available context is sufficient.
2. Identify the test boundaries for the feature. Prefer existing boundaries and test at the highest level that can verify the intended behavior, minimizing separate test boundaries across modules. If these choices have not already been confirmed with the user, check that they match the user's expectations.
3. Write the spec using the structure below. Prefer updating an unfinished spec on the same topic; otherwise, create a file with a descriptive name.
4. Save it in the configured location and update the README index.

## Document Structure

Metadata field guidance

- `status` (required): `not-started`, `in-progress`, or `completed`. Delete or archive abandoned specs.
- `execution_time` (required): the creation date in `YYYY-MM-DD` format; when completed, use `YYYY-MM-DD / YYYY-MM-DD` (creation / completion).
- `commit` (optional): short Git commit hash for the completed implementation.
- `version` (optional): the corresponding project version, if the project is versioned.
- `related_documents` (optional): document titles with relative paths or URLs.

```markdown
# Feature Name

---

status: not-started
execution_time: "YYYY-MM-DD"
commit: null
version: null
related_documents: []

---

## Goal

Briefly describe the problem from the user's perspective.

## Solution

Briefly describe the solution from the user's perspective.

## User Stories

Use a numbered list covering user goals, primary flows, and relevant error or exceptional cases.
For each story, state who the user is, what they want to do, and why.

## Implementation Decisions

Record agreed decisions about module responsibilities, interfaces, architecture, data structures, API contracts, and interactions.

## Testing Decisions

Describe the external behavior to verify, test boundaries, modules involved, and relevant testing practices already used in the codebase.

## Out of Scope

State what this spec does not address.

## Further Notes

Record unresolved questions and other context that affects implementation.
```

Implementation decisions should generally omit specific code paths and snippets to avoid becoming stale as implementation details change. If a prototype's state machine, data structure, or type definition expresses a decision more precisely than prose, include the relevant excerpt and note that it came from a prototype.

Base testing decisions on observable behavior rather than internal implementation details.
