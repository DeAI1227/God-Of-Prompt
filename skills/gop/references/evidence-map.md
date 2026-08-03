# GOP v0.2 Evidence Map

Read this file for every GOP invocation. The maintainer-provided workshop PDF is the primary design source: **Starter → Context → Task → Examples → Output → Repeat**, with `MUST` / `SHOULD` / `MAY`, acceptance criteria, and failure handling. The five papers below fill operational gaps and bound claims. Do not append this map or its citations to GOP output unless the user asks.

## Workshop framework translated into the prompt

| PDF element | GOP implementation |
|---|---|
| Starter | One- or two-sentence mission; use a role only when it changes perspective or standards. |
| Context | Include only audience, facts, inputs, and boundaries that alter judgment. |
| Task | Use an executable mission, `MUST` / `SHOULD` / `MAY`, acceptance criteria, and safe failure handling. |
| Examples | Treat demonstrations as a reference distribution. Check quantity, ordering, label distribution, label quality, format, and similarity before using them. |
| Output | Declare the output container, field order, length, evidence treatment, and missing-information behavior. |
| Repeat | Re-state no more than one or two critical constraints. |
| RaR / Self-Ask | Use concise task rephrasing for material ambiguity and task decomposition for genuinely multi-hop work. Never request hidden chain-of-thought. |
| Robustness | Test template wording, language variants, and semantic/task variants separately. |

## Five-paper supplements and scope limits

| Paper | Required translation into GOP | Scope limit |
|---|---|---|
| Anam (2025), *Prompt Engineering and the Effectiveness of LLMs in Enhancing Human Productivity* | Make task, context, constraints, expected output, and revision targets explicit. | A 243-person voluntary convenience-sample survey supports self-reported associations, not universal causal productivity gains. https://arxiv.org/pdf/2507.18638 |
| Kusano, Akimoto, & Takeoka (2025), *Revisiting Prompt Engineering* | Begin with the smallest viable six-part baseline; add examples, rephrasing, decomposition, or tools only for a named failure and preserve quality/format/cost trade-offs. | Findings concern single-user personalized recommendation and cannot rank prompt methods generally. https://arxiv.org/pdf/2507.13525 |
| Chen et al. (2026), *Promptware Engineering* | Define functional and non-functional needs, safe failures, versioned changes, test cases, traces, monitoring, rollback, and human/authorization controls around the prompt. | It is a research roadmap, not empirical proof; prompt text cannot implement fine-grained access control. https://arxiv.org/pdf/2503.02400 |
| Sahoo et al. (2024), *A Systematic Survey of Prompt Engineering in Large Language Models* | Select techniques by their function: demonstrations for pattern learning, authorized retrieval/verification for external knowledge, and task-appropriate decomposition for complex tasks. | No technique removes hallucination, bias, or interpretability risks. https://arxiv.org/pdf/2402.07927 |
| Ye et al. (2024), *Prompt Engineering a Prompt Engineer (PE2)* | For repeated failures, use explicit failed cases and a diagnose/refine loop; keep optimization cases separate from final held-out evaluation. | Automated prompt optimization is model-dependent and may hallucinate or fail to follow instructions. https://aclanthology.org/2024.findings-acl.21.pdf |

## Operational evaluation minimum

For a reusable GOP prompt, retain a minimal baseline and compare any revision against representative development cases and held-out final cases. Record the prompt version, model and parameters, input category, authorized tools/sources, output, errors, latency, and cost when available. Test wording/template variation, relevant language versions, and semantic/task variants separately. Roll back a revision that regresses the agreed acceptance criteria or safety boundary.
