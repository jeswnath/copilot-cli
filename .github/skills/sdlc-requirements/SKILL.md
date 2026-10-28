---
name: sdlc-requirements
description: Guides structured requirements capture for SDLC features. Use when asked to write, review, or analyze functional requirements for software projects. Includes templates and quality standards for enterprise-grade requirements documentation.
---

# SDLC Requirements Skill

This skill guides you in producing high-quality, enterprise-grade functional requirements that are testable, traceable, and sprint-ready.

## When This Skill Applies
- User asks to "write requirements" or "generate requirements"
- User provides a feature description or business problem
- User asks to review or improve existing requirements
- You are acting as the Requirements Writer agent in an SDLC pipeline

## Step-by-Step Process

### Step 1: Understand the Context
Before writing requirements, ask yourself (or the user):
1. What is the business problem being solved?
2. Who are the users / stakeholders?
3. What are the constraints (technology, time, budget, compliance)?
4. Are there existing systems this feature must integrate with?

If any of these are unclear, state your assumptions explicitly at the top of your response.

### Step 2: Identify Requirement Types
For each feature, identify:
- **Functional requirements** — what the system must DO
- **Non-functional requirements (NFRs)** — how the system must PERFORM
  - Performance: response times, throughput
  - Security: authentication, authorization, data protection
  - Reliability: uptime, error recovery
  - Usability: accessibility, UX standards
  - Scalability: load, concurrent users

### Step 3: Apply the Standard Template

Use this template for every requirement:

```
**REQ-ID:** REQ-[XXX]
**Title:** [Action-oriented, max 8 words]
**Description:** The system shall [clear, single responsibility statement].
**Acceptance Criteria:**
  - Given [initial context or precondition]
  - When [user action or system event]
  - Then [expected system response]
  - And [secondary outcome, if any]
**Priority:** High / Medium / Low
**NFR Tag:** Performance / Security / Reliability / Usability / None
**Dependencies:** [REQ-IDs] or None
```

### Step 4: Quality Check
Before finalizing, verify every requirement against this checklist:

| Check | Pass? |
|-------|-------|
| Is it testable? (Can a QA write a test for it?) | ✅ / ❌ |
| Is it unambiguous? (Only one interpretation?) | ✅ / ❌ |
| Is it feasible? (Can it realistically be implemented?) | ✅ / ❌ |
| Is it necessary? (Does it solve a real business need?) | ✅ / ❌ |
| Does it have at least one acceptance criterion? | ✅ / ❌ |
| Is the REQ-ID unique and sequential? | ✅ / ❌ |

## Anti-Patterns to Avoid

❌ **Vague requirements:** "The system should be fast" → ✅ "The system shall return search results within 2 seconds for 95% of requests"

❌ **Compound requirements:** "The system shall authenticate users and log all access" → Split into REQ-001 (auth) and REQ-002 (audit logging)

❌ **Implementation specifications:** "The system shall use JWT tokens" → This is a design decision, not a requirement. Write: "The system shall maintain secure user sessions with configurable expiry"

❌ **Unmeasurable NFRs:** "The system shall be secure" → Specify what security means: "The system shall enforce HTTPS for all API calls and store passwords using bcrypt with salt factor ≥ 12"

## Example: Feature Input vs. Requirements Output

**Input:** "We want users to be able to search for products"

**Output:**
```
**REQ-ID:** REQ-001
**Title:** Full-Text Product Search
**Description:** The system shall allow registered and guest users to search the product catalog using keywords.
**Acceptance Criteria:**
  - Given any user is on the product listing page
  - When they enter at least 2 characters in the search bar
  - Then the system returns matching products within 1.5 seconds
  - And results are sorted by relevance score descending
**Priority:** High
**NFR Tag:** Performance
**Dependencies:** None

**REQ-ID:** REQ-002
**Title:** Search Filters for Product Category
**Description:** The system shall allow users to filter search results by product category, price range, and rating.
**Acceptance Criteria:**
  - Given search results are displayed
  - When the user applies one or more filters
  - Then results update without a full page reload within 500ms
  - And the applied filters are shown as removable chips above the results
**Priority:** Medium
**NFR Tag:** Usability
**Dependencies:** REQ-001

**REQ-ID:** REQ-003  
**Title:** Search Results Accessibility
**Description:** The system shall ensure search results meet WCAG 2.1 AA accessibility standards.
**Acceptance Criteria:**
  - Given search results are displayed
  - When a screen reader user navigates the results
  - Then all product names, prices, and links are correctly announced
  - And keyboard navigation moves through results in logical order
**Priority:** Medium
**NFR Tag:** Usability
**Dependencies:** REQ-001
```

## Reference
See [requirements-template.md](./requirements-template.md) for the printable blank template.
