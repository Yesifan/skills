---
name: skill-creator
description: "Create or improve agent skills from workflows, references, or conversations: define scope, distill reusable knowledge, and validate the result."
disable-model-invocation: true
---

# Skill Creator

A skill is a task-specific capability guide that an agent loads on demand. Prioritize stability and reuse. Include only domain knowledge, tool constraints, user preferences, and verified experience that change the model's decisions. Preserve their conditions of use; omit generic competence and repeated instructions.

## Development Workflow

### Define Requirements and Boundaries

1. Identify the requests the skill should handle, its deliverables, and success criteria. When modifying an existing skill, read its instructions and relevant resources first, then define the scope of the change. Discuss missing information only when it affects the design.
2. Infer whether the skill should allow automatic selection by the model or require explicit user invocation; ask when the context is insufficient. Preserve an existing skill's invocation mode by default.
3. Choose the emphasis based on the task: concrete operations need tools, interfaces, and execution constraints; process guidance needs decision criteria and key steps. Combine both when useful.

### Define Skill Metadata

Add YAML frontmatter at the top of `SKILL.md`, for example:

```yaml
---
# Required: match the skill directory name; use lowercase letters, digits, and hyphens.
name: release-notes
# Required: briefly describe the capability and applicable requests; add exclusions if needed.
# Use this rule for both invocation modes. Put prerequisites and branching logic in the body.
description: "Generate user-facing release notes from commit history when preparing a version release."
# Optional: true requires explicit user invocation in agents that support this field.
# Omit it to allow automatic selection in those agents.
disable-model-invocation: true
---
```

For Codex, configure `policy.allow_implicit_invocation` in `agents/openai.yaml`: `false` for explicit-only invocation, `true` to allow automatic selection.

### Draft and Discuss

Keep core guidance in `SKILL.md`, organized as a workflow, rules, or a decision guide. Include prerequisites, branching conditions, and submodule routing. Define observable completion criteria for key steps and the final result.

Create optional resources only as needed: branch-specific detail in `references/`, deterministic helpers in `scripts/`, output resources in `assets/`, and platform configuration in `agents/`. Reference resources using paths relative to the skill root, and explain when to read or execute them.

State required external tools and environment dependencies explicitly.

Write and save the skill. Explain the main tradeoffs and open questions, then discuss and revise based on feedback. Begin validation only after the user confirms satisfaction with the content; do not run validation for each draft iteration.

### Validate the Result

Check frontmatter, directory naming, invocation settings, resource links, and unfinished placeholders. Run new or changed scripts with representative inputs.

If an independent agent is available and the task can run in a temporary workspace without affecting real systems, delegate a trial using a realistic request. Assess the result against the success criteria and task boundaries. Otherwise, explain why behavioral validation was not performed. Fix demonstrated failures without adding speculative rules.

When the delegated agent's execution record is available, read it to identify ineffective steps and add targeted guidance to address them.

Report the files created or changed, the main design choices, and the validation actually performed. Installation, publishing, and unrelated configuration changes require their own scope.

## References

- [Agent Skills Overview](https://agentskills.io/home)
