# ⚡ God Of Prompt — OpenAI Codex System Prompt Generator

[![Codex Skill](https://img.shields.io/badge/Codex-Skill-000000?logo=openai&logoColor=white)](https://github.com/openai/codex)
[![License: MIT](https://img.shields.io/badge/License-MIT-f5de53.svg)](LICENSE)
[![PDF-led Architecture](https://img.shields.io/badge/Architecture-PDF--led-0a7ea4.svg)](docs/architecture.md)
[![Research Grounded](https://img.shields.io/badge/Research-Grounded-6f42c1.svg)](#evidence-and-boundaries)

**Turn a rough requirement into a visible, expert-grade XML system prompt—then execute it immediately.**

God Of Prompt (GOP) is an installable **OpenAI Codex Skill**, system-prompt generator, and AI-agent prompt template. It turns a rough product idea, chatbot brief, workflow, tutor, automation, or LLM instruction into a practical six-part system prompt: **Starter → Context → Task → Examples → Output → Repeat**. GOP shows the complete prompt, then applies it in the same response without waiting for approval.

[繁體中文](README.zh-TW.md) · [Quick start](#quick-start) · [Architecture](docs/architecture.md) · [Examples](#examples) · [Launch kit](docs/launch-playbook.md)

## Quick start

```text
$gop Build an assistant that turns meeting notes into a concise weekly project update for a product team.
```

GOP returns exactly two sections: `完整 System Prompt`, then `執行結果`. It never adds a prompt-approval turn.

## Install in Codex

```powershell
git clone https://github.com/DeAI1227/God-Of-Prompt.git
Copy-Item -Recurse -Force .\God-Of-Prompt\skills\gop "$env:USERPROFILE\.codex\skills\gop"
```

Restart Codex if the Skill list does not refresh immediately, then invoke `$gop` followed by the requirement.

## Use the same Skill in Claude Code or Cursor

GOP's core is a portable `SKILL.md` directory with supporting references. Claude Code and Cursor both support Agent Skills built around `SKILL.md`; copy the complete `skills/gop` directory to the skill location for the client you use.

```text
Claude Code project: .claude/skills/gop/
Cursor project:      .cursor/skills/gop/
```

For Claude Code, invoke it as `/gop` or let Claude load it when the request matches its description. For Cursor, invoke or allow the Agent to load the `gop` skill according to your Cursor Skills settings. The optional `agents/openai.yaml` file is Codex metadata; other clients can ignore it.

## What can I build with this prompt generator?

Use GOP when you need a reusable system prompt for:

- An AI agent, chatbot, customer-support assistant, or internal copilot.
- An automation workflow that turns notes, documents, or structured input into a defined deliverable.
- An LLM tutor, coach, analyst, research brief writer, or content workflow.
- A prompt template with a reliable output schema, source boundary, uncertainty behavior, and safety limits.

It is designed for people searching for a Codex Skill, system prompt template, AI-agent prompt, LLM prompt engineering workflow, or XML prompt structure—not for one-off decorative prompts.

## The GOP v0.2 prompt architecture

| Section | What it controls |
|---|---|
| `starter` | A short mission or role that genuinely changes perspective or standards. |
| `context` | Only the user, facts, inputs, and boundaries that change judgment. |
| `task` | Executable work, `MUST` / `SHOULD` / `MAY`, acceptance criteria, and failure handling. |
| `examples` | Representative demonstrations—or an explicit declaration that none are needed. |
| `output` | Container, fields, order, length, evidence treatment, and missing-data behavior. |
| `repeat` | One or two critical reminders, not duplicated boilerplate. |

The prompt is XML so its parts are inspectable and stable. It is not verbose for its own sake: GOP starts with the smallest viable six-part baseline and adds a technique only when the task justifies it.

## Conditional techniques, not decoration

- Use examples only after checking quantity, ordering, label distribution, label quality, format, and similarity.
- Use concise task rephrasing for material ambiguity; ask one targeted question only when safe completion is blocked.
- Use task decomposition for genuinely multi-hop work, exposing only requested or output-relevant checkpoints—not hidden chain-of-thought.
- Use authorized retrieval only with source, freshness, conflict, attribution, and uncertainty rules.
- For recurring failures, diagnose the failed dimension, make up to three focused revisions, and evaluate against held-out cases.

## Examples

Every example includes the requirement, the full six-part GOP prompt, and the immediate execution result:

- [High-school inequality tutor](examples/high-school-inequality-tutor.md)
- [Meeting notes → weekly update](examples/meeting-notes-weekly-update.md)
- [Grounded research brief](examples/grounded-research-brief.md)

## Evidence and boundaries

GOP follows the maintainer-provided workshop framework and uses five papers to strengthen its operational limits: explicit task and context, minimal baselines, controlled technique selection, Promptware lifecycle practices, and evaluation from failed cases. See the full [evidence map](skills/gop/references/evidence-map.md).

This does **not** promise universal productivity, correctness, security, fairness, or hallucination elimination. A prompt does not replace real access control, data isolation, secret management, tool authorization, monitoring, or human accountability.

## Repository map

```text
God-Of-Prompt/
├── skills/gop/                  # Installable Codex Skill
│   ├── SKILL.md                 # Six-part prompt-generation behavior
│   ├── agents/openai.yaml       # Codex UI metadata
│   └── references/evidence-map.md
├── docs/                        # Architecture and launch materials
├── examples/                    # Input / prompt / execution examples
├── CONTRIBUTING.md
├── SECURITY.md
└── LICENSE
```

## Contributing

Contributions are welcome. Read [CONTRIBUTING.md](CONTRIBUTING.md) before opening an issue or pull request. Support behavioral claims with a reproducible example and keep changes aligned with the architecture and evidence limits.

## License

Released under the [MIT License](LICENSE).
