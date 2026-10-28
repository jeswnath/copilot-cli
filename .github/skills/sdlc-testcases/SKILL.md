---
name: sdlc-testcases
description: Converts user stories into ADO-ready test cases with positive, negative, edge, and security coverage.
---

# SDLC Test Cases Skill

Use this skill to derive comprehensive test cases from user stories.

## Primary Output Template (ADO)

```markdown
### Feature: [Feature name]

| Test Case ID | Title | Priority | Type | Preconditions | Steps | Expected Result | Linked Story | Linked Requirement | Tags |
|--------------|-------|----------|------|---------------|-------|-----------------|--------------|--------------------|------|
| TC-001 | [Happy path] | High | Positive | [state] | 1) [step] | [outcome] | US-001 | REQ-001 | smoke,happy-path |
```

## Coverage Rules
1. Minimum per feature: 2 positive, 2 negative, 2 edge, 1 security scenario.
2. Use clear plain-English test steps.
3. Preserve traceability: TC -> US-ID -> REQ-ID.
4. Include tags: smoke, happy-path, negative, edge-case, security.
5. Add a short coverage summary after each feature block.
