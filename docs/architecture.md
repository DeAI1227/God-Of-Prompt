# GOP v0.2 Architecture

## Purpose

GOP converts an informal requirement into a visible system prompt and immediately runs it. v0.2 makes the maintainer-provided workshop framework its fixed prompt skeleton and uses five papers to add limits, evaluation, and operational discipline.

## Canonical contract

Every GOP-generated prompt contains these XML sections in this order:

```xml
<starter>...</starter>
<context>...</context>
<task>...</task>
<examples>...</examples>
<output>...</output>
<repeat>...</repeat>
```

`task` always includes `MUST`, `SHOULD`, `MAY`, `acceptance_criteria`, and `failure_handling`. The Skill response itself always contains the full prompt first and immediate execution second.

## Section responsibilities

| Section | Include | Exclude |
|---|---|---|
| Starter | Short mission; role only when it changes standards or perspective. | Prestige labels and generic persona theatre. |
| Context | Audience, inputs, facts, and boundaries that change judgment. | Background that does not affect the decision. |
| Task | Executable mission, rule strength, acceptance, and safe failure path. | Vague verbs without a completion condition. |
| Examples | Representative examples checked for six few-shot dimensions; an explicit “none needed” declaration otherwise. | Examples chosen only because more prompting looks sophisticated. |
| Output | Container, schema, order, length, evidence, and missing-data behavior. | Formatting instructions scattered through unrelated prose. |
| Repeat | One or two highest-risk reminders. | Duplicated boilerplate. |

## Technique gates

| Technique | Use only when | Safeguard |
|---|---|---|
| Role | Perspective, domain standard, or authority changes the task. | Never use a title as a proxy for requirements. |
| Style | Presentation changes user value. | Keep style out of factual or permission rules. |
| Few-shot | Pattern, format, or classification needs demonstrations. | Check quantity, ordering, label distribution, label quality, format, and similarity. |
| Rephrase-and-respond | The user's wording has material ambiguity. | Give a concise visible interpretation; ask only when blocked. |
| Self-Ask / decomposition | Work has dependent subquestions. | Expose only requested or output-relevant checkpoints, never hidden chain-of-thought. |
| Retrieval / tools | Authorized external evidence or action is required. | Declare authority, freshness, attribution, conflict, and untrusted-data rules. |

## Evaluation and lifecycle

Keep a minimal baseline. A proposed addition is a hypothesis, not a presumed upgrade. For reusable deployments, compare it with the baseline on representative development cases and separate held-out cases; record prompt version, model/settings, inputs, tools/sources, output, errors, latency, and cost. Test wording/template, relevant language, and semantic/task variations separately. Diagnose repeated failures by task, context, evidence, format, safety, or cost; make at most three focused revisions, then re-evaluate or roll back.

Prompts are only one layer. Access controls, data isolation, secrets, tool authorization, observability, monitoring, and irreversible-action approvals belong in the surrounding system.

## Evidence posture

The workshop PDF determines the architecture. The five research papers add empirical and engineering constraints, but none proves that this architecture universally improves accuracy, security, productivity, or fairness. Exact mappings and scope limits live in [the evidence map](../skills/gop/references/evidence-map.md).
