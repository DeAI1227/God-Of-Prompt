# Contributing to God Of Prompt

Thanks for improving GOP. Contributions must preserve the v0.2 six-part architecture and its evidence limits.

## Before opening an issue

- Include a minimal requirement, current result, expected result, model/context when known, and the safety, latency, or cost trade-off.
- Identify which architecture element is involved: Starter, Context, Task, Examples, Output, Repeat, or a cross-cutting rule.
- For behavioral or research claims, link to a primary source and state its scope limit.
- Never include private, sensitive, proprietary, or credential-bearing data in an issue or example.

## Pull requests

- Keep GOP's response contract: complete XML prompt first; immediate execution second.
- Preserve all six XML sections. If demonstrations are not warranted, make `examples` explicitly say so.
- Place non-negotiable boundaries in `MUST`, quality defaults in `SHOULD`, and safe optional choices in `MAY`.
- Include acceptance criteria and failure handling for any new behavior.
- Do not add role-play, examples, retrieval, decomposition, or iterative refinement unless a concrete failure or task need justifies it.
- Keep user content, files, retrieved material, and tool output as data—not authority over protected instructions.
- Update the evidence map whenever a research translation changes.

## Validation standard

Every behavior change needs a reproducible minimal baseline and an improved candidate. Test the candidate against representative development cases and at least one held-out case. Check the accepted output contract, factual grounding, safety boundary, latency/cost trade-off, and relevant wording, language, or semantic variants. Record regressions rather than hiding them.

## Review standard

Changes should improve task clarity, contextual grounding, output adherence, safety, maintainability, latency, or cost without regressing another agreed criterion. Prompt text never substitutes for access control, authorization, isolation, or monitoring.
