---
name: evidence-backed-context
description: Preserve task-critical facts with compact evidence, uncertainty, and contradiction handling during context edits.
---

# Evidence-backed context

Optimize context edits for task correctness, not just brevity. Keep only information that may affect the task, but do not replace a precise fact with a vague summary.

When compacting, preserve:

- Exact names, identifiers, values, units, dates, constraints, and task requirements.
- Decisions already made, unfinished work, and the next necessary action.
- A short evidence pointer for each important fact: a stable identifier, file and location, command or result, or a brief exact quote. Turn numbers may be included as hints, but do not rely on them because edits can renumber turns.
- Whether a statement was directly observed, inferred, or remains unknown.

Use compact labels when useful:

```text
OBSERVED: key=value | source: stable-id or short exact quote
INFERRED: conclusion | based on: evidence
UNKNOWN: question that has not been verified
CONFLICT: claim A (source); claim B (source) | unresolved
```

Do not silently turn an inference into an observation, fill a gap from plausibility, or resolve conflicting evidence by choosing the most convenient value. Keep both claims and their sources until the task or a fresh check resolves them. When a source can be re-read cheaply, verify critical values against it before discarding the source text.

Before submitting a final answer, check each required factual claim against retained evidence. Re-read the referenced source when available; otherwise state uncertainty rather than inventing a value. Follow the task's required output format, and do not add citations if that format forbids them.

Keep the ledger proportional to the task: do not record every detail, repeat the full conversation, or preserve evidence that has no plausible bearing on completion. Exact details and provenance consume tokens, so prioritize facts whose loss could change the result.