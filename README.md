# ⚡ God Of Prompt

[![Codex Skill](https://img.shields.io/badge/Codex-Skill-000000?logo=openai&logoColor=white)](https://github.com/openai/codex)
[![License: MIT](https://img.shields.io/badge/License-MIT-f5de53.svg)](LICENSE)
[![Research Grounded](https://img.shields.io/badge/Research-Grounded-6f42c1.svg)](#research-foundations)

**Turn a rough requirement into a visible, copy-ready system prompt—then execute it immediately.**

God Of Prompt (GOP) is an installable Codex Skill for people who want a reliable system prompt, not a prompt-engineering report. Give it a product idea, workflow, agent, chatbot, or business requirement; it shows the complete system prompt, then applies it in the same response without waiting for approval.

[繁體中文](README.zh-TW.md) · [Quick start](#quick-start) · [Example](examples/high-school-inequality-tutor.md) · [Research](#research-foundations)

## Why GOP

Most prompt generators compensate for ambiguity with more text: roles, multi-agent theatre, generic chain-of-thought demands, and unearned claims. GOP takes the opposite approach:

- Start with a minimal, contextual prompt.
- Add examples, retrieval, decomposition, or refinement only when the requirement justifies them.
- Define data boundaries, unknown-information behavior, instruction hierarchy, and output format.
- Make the full prompt visible, then execute it immediately.

## Quick start

```text
$gop Build an assistant that turns meeting notes into a concise weekly project update for a product team.
```

GOP responds in two sections: the complete copy-ready system prompt, followed immediately by its execution result. It never waits for a prompt-approval turn.

## Install

```powershell
git clone https://github.com/DeAI1227/God-Of-Prompt.git
Copy-Item -Recurse -Force .\God-Of-Prompt\skills\gop "$env:USERPROFILE\.codex\skills\gop"
```

Restart Codex if the Skill list does not refresh immediately, then invoke `$gop` followed by your requirement.

## What GOP puts in the prompt

| Requirement signal | Prompt behavior |
|---|---|
| A precise deliverable | Stable output contract, schema, and an example only when it prevents ambiguity |
| Facts or external knowledge | Authorized sources, attribution, freshness, conflict, and uncertainty rules |
| Tool or retrieved content | Treats it as untrusted data, never higher-priority instructions |
| A difficult multi-step task | Observable checkpoints tied to the requested deliverable—not hidden chain-of-thought requests |
| Repeated failures | Diagnosis of task, context, evidence, format, safety, or cost; at most three focused revisions |
| High-stakes or irreversible action | Human review, authorization limits, escalation, and no autonomous irreversible decision |

GOP also ensures that the target system treats quoted text, files, retrieved material, and tool output as data. Prompt text is never presented as a substitute for real access control, data isolation, or authorization checks.

## Example

See [High-school inequality tutor](examples/high-school-inequality-tutor.md) for a real input, the complete system prompt, and the immediate first response.

## Research foundations

GOP translates the following five sources into operational prompt constraints. They are not used to promise universal productivity, accuracy, or hallucination elimination.

1. Anam (2025), [*Prompt Engineering and the Effectiveness of Large Language Models in Enhancing Human Productivity*](https://arxiv.org/pdf/2507.18638) — explicit task, context, constraints, and expected output.
2. Kusano, Akimoto, and Takeoka (2025), [*Revisiting Prompt Engineering: A Comprehensive Evaluation*](https://arxiv.org/pdf/2507.13525) — compare a minimal baseline with justified additions; account for quality, format, and cost.
3. Chen et al. (2026), [*Promptware Engineering: Software Engineering for Prompt-Enabled Systems*](https://arxiv.org/pdf/2503.02400) — requirements, safe failure behavior, versionable prompts, and operational boundaries.
4. Sahoo et al. (2024), [*A Systematic Survey of Prompt Engineering in Large Language Models*](https://arxiv.org/pdf/2402.07927) — choose techniques for their task-specific function rather than by fashion.
5. Ye et al. (2024), [*Prompt Engineering a Prompt Engineer*](https://aclanthology.org/2024.findings-acl.21.pdf) — use failed cases and explicit context to diagnose and refine prompts.

Read the exact translations and scope limits in [the evidence map](skills/gop/references/evidence-map.md).

## Repository map

```text
God-Of-Prompt/
├── skills/gop/                  # Installable Codex Skill
│   ├── SKILL.md                 # Prompt-generation behavior
│   ├── agents/openai.yaml       # Codex UI metadata
│   └── references/evidence-map.md
├── examples/                    # Input/output examples
├── .github/ISSUE_TEMPLATE/      # Community reporting template
├── CONTRIBUTING.md
├── SECURITY.md
└── LICENSE
```

## Boundaries

- GOP does not guarantee that a model is correct, secure, unbiased, or more productive.
- GOP shows the generated system prompt but does not expose drafting analysis or hidden reasoning.
- GOP does not make unauthorized tools, data, or actions safe merely by mentioning them in a prompt.
- For consequential domains, validate outputs and keep a responsible human in the decision loop.

## Contributing

Contributions are welcome. Read [CONTRIBUTING.md](CONTRIBUTING.md) before opening an issue or pull request. Please support behavioral claims with a reproducible example or a credible source.

## License

Released under the [MIT License](LICENSE).
