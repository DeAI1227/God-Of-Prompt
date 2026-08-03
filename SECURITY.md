# Security Policy

## Reporting a vulnerability

Do not disclose a suspected security issue in a public issue. Use GitHub's private vulnerability reporting for this repository. Include a minimal reproduction, affected file or behavior, impact, model/tool context if known, and a proposed mitigation if known. Remove secrets and sensitive data before reporting.

## Prompt-level boundary

GOP requires generated prompts to separate instructions from untrusted user text, quoted material, files, retrieved documents, and tool output. It also requires explicit source, uncertainty, failure, and escalation behavior where relevant.

These are defense-in-depth prompt rules only. GOP cannot enforce external permissions, data isolation, secret management, network policy, tool authorization, audit logging, monitoring, or model-provider controls. Implement and test those controls outside the prompt, and keep a human approval boundary for consequential or irreversible actions.

## Safe change review

Security-relevant changes must identify the affected XML section, preserve `MUST` boundaries and failure handling, and include a minimal prompt-injection or authority-confusion regression case. Do not claim that a prompt alone makes a system secure.
