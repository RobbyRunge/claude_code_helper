# Claude Code Helper

A collection of structured prompt guides for [Claude Code](https://claude.ai/code) that turn the CLI into a consistent, context-aware coding assistant.

Each guide is fetched on-demand via a keyword trigger in your `~/.claude/CLAUDE.md`.

---

## Quick Reference

| Keyword | Guide |
|---------|-------|
| `debugging` | Debug a problem step by step |
| `review` | Review code for quality, security & performance |
| `planning` | Plan a feature before writing any code |
| `explain` | Get a concept explained at your level |
| `refactor` | Restructure code without changing behavior |
| `testing` | Write meaningful tests for your code |

---

## Setup

Add trigger lines to `~/.claude/CLAUDE.md`:

```
Wenn ich "debugging" sage, fetche und befolge: https://raw.githubusercontent.com/RobbyRunge/claude_code_helper/main/debugging_guide.md
Wenn ich "review" sage, fetche und befolge: https://raw.githubusercontent.com/RobbyRunge/claude_code_helper/main/code_review_guide.md
Wenn ich "planning" sage, fetche und befolge: https://raw.githubusercontent.com/RobbyRunge/claude_code_helper/main/feature_planning_guide.md
Wenn ich "explain" sage, fetche und befolge: https://raw.githubusercontent.com/RobbyRunge/claude_code_helper/main/explain_guide.md
Wenn ich "refactor" sage, fetche und befolge: https://raw.githubusercontent.com/RobbyRunge/claude_code_helper/main/refactor_guide.md
Wenn ich "testing" sage, fetche und befolge: https://raw.githubusercontent.com/RobbyRunge/claude_code_helper/main/testing_guide.md
```

Claude will fetch the matching guide whenever you use the keyword in a conversation.

---

## Guides

### `debugging_guide.md` — triggered by `debugging`

A step-by-step debugging workflow that adapts to your goal:

- Clarifies project type (learning / professional / exam)
- Selects stack (Angular, Django, React, other)
- Chooses mode: **J** (guided learning) or **N** (direct solution)
- Always explains the root cause, never just fixes the symptom
- Ends with a link to the official documentation

### `code_review_guide.md` — triggered by `review`

A structured code review that covers all the areas that matter:

| Area | Focus |
|------|-------|
| **S** Security | Injection, auth gaps, data leaks |
| **P** Performance | N+1 queries, unnecessary re-renders |
| **Q** Quality | Naming, structure, readability |
| **B** Best Practices | Stack conventions, typing, error handling |

Supports the same two modes as the debugging guide — learn-focused or straight to the fix.

### `feature_planning_guide.md` — triggered by `planning`

A structured planning session before writing any code:

- Covers backend (models, migrations, endpoints, serializers, signals) and frontend (components, state, routing, error handling)
- Explicitly walks through edge cases and risks
- Delivers a prioritized checklist with recommended implementation order
- Supports learn mode (think it through together) and direct mode (give me the plan)

### `explain_guide.md` — triggered by `explain`

Concept explanations tailored to your current knowledge level:

- Asks what you already know before explaining — no re-explaining the obvious
- Three depth levels: **O** (overview), **D** (internals), **P** (practical example in your project context)
- Always includes an analogy and a comprehension check at the end
- Distinguishes when to use one concept vs. another

### `refactor_guide.md` — triggered by `refactor`

Structured refactoring that improves code structure without changing behavior:

- Identifies candidates: readability, duplication, responsibility, complexity, framework anti-patterns
- Names the refactoring technique used (Extract Function, Rename, etc.)
- Always includes a behavior-check at the end to confirm nothing broke
- Supports learn mode (explain each step) and direct mode (deliver the refactored code)

### `testing_guide.md` — triggered by `testing`

Helps write tests that give real confidence, not just coverage numbers:

- Recommends the right test type (unit / integration / E2E) for the code at hand
- Follows Arrange / Act / Assert structure throughout
- Explicitly calls out what NOT to test (framework behavior, trivial getters)
- Includes a coverage-check at the end: what's missing and what to tackle next

---

## Planned


- `git_guide.md` — commit messages, branch naming, PR descriptions, when to squash
- `security_guide.md` — OWASP checklist, Django security pitfalls, JWT edge cases
- `performance_guide.md` — profiling-first approach, DB query optimization, frontend render performance

---

## Stack support

All guides currently support:

- Angular / TypeScript
- Django / Python
- React / TypeScript
