# Contributing to God Of Prompt

Thanks for improving GOP.

## Before opening an issue

- Confirm that the behavior belongs in a reusable Codex Skill rather than a one-off prompt.
- Include a minimal requirement, the current output, the expected behavior, and any safety or cost trade-off.
- For research claims, link to the primary paper or official source and state its scope limit.

## Pull requests

- Keep GOP's strict output contract: one copy-ready system prompt only.
- Prefer the smallest change that solves a demonstrated failure.
- Do not add role-play, hidden chain-of-thought requests, RAG, examples, or iterative loops unless a concrete use case justifies them.
- Preserve the distinction between prompt rules and external authorization or access controls.
- Update the evidence map whenever a research translation changes.

## Review standard

Changes should improve at least one of: task clarity, contextual grounding, output adherence, safety, maintainability, latency, or cost—without creating a regression in another dimension.
