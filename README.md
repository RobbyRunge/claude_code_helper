# Claude Code Helper

A collection of structured prompt guides for [Claude Code](https://claude.ai/code) that turn the CLI into a consistent, context-aware coding assistant.

Each guide is fetched on-demand via a keyword trigger in your `~/.claude/CLAUDE.md`.

---

## Setup

Add trigger lines to `~/.claude/CLAUDE.md`:

```
Wenn ich "debugging" sage, fetche und befolge: https://raw.githubusercontent.com/RobbyRunge/claude_code_helper/main/debugging_guide.md
Wenn ich "review" sage, fetche und befolge: https://raw.githubusercontent.com/RobbyRunge/claude_code_helper/main/code_review_guide.md
Wenn ich "planning" sage, fetche und befolge: https://raw.githubusercontent.com/RobbyRunge/claude_code_helper/main/feature_planning_guide.md
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

---

## Planned guides

- `explain_guide.md` — get concept explanations tailored to your level

---

## Stack support

All guides currently support:

- Angular / TypeScript
- Django / Python
- React / TypeScript
