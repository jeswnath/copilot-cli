---
name: sdlc-userstory
description: Converts functional requirements into Agile user stories with acceptance criteria and REQ-to-US traceability.
---

# SDLC User Story Skill

Use this skill to convert requirements into sprint-ready user stories.

## Output Template

```
**US-ID:** US-[XXX]
**Epic:** [Feature theme]
**Title:** [Short verb-noun title]

**Story:**
As a [specific role],
I want [capability],
So that [business value].

**Acceptance Criteria:**
  - [ ] AC-1: [Happy path]
  - [ ] AC-2: [Alternative path]
  - [ ] AC-3: [Error or edge path]
  - [ ] AC-4: [Security or performance condition when applicable]

**Story Points:** [1 / 2 / 3 / 5 / 8]
**Labels:** [Sprint-Ready / Needs-Refinement / Blocked]
**Linked Requirements:** [REQ-IDs]
```

## Rules
1. Use sequential IDs: US-001, US-002, ...
2. Include at least 3 acceptance criteria per story.
3. Keep each story INVEST-compliant.
4. Preserve traceability with Linked Requirements.
5. Add a REQ-to-US traceability matrix at the end.
