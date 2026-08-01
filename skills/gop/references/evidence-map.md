# GOP Evidence Map

Read this file for every GOP invocation. Translate the findings into the generated prompt; never append this map or its citations to GOP output unless requested.

| Paper | Required translation into GOP | Scope limit |
|---|---|---|
| Anam (2025), *Prompt Engineering and the Effectiveness of LLMs in Enhancing Human Productivity* | Make task, context, constraints, and expected output explicit; revise against failures. | A 243-person voluntary convenience-sample survey supports self-reported associations, not universal causal productivity gains. https://arxiv.org/pdf/2507.18638 |
| Kusano, Akimoto, & Takeoka (2025), *Revisiting Prompt Engineering* | Begin with the smallest viable prompt; add Rephrase, Step-Back, ReAct-like decomposition, or examples only for a named need; preserve quality/format/cost trade-offs. | Findings concern single-user personalized recommendation and cannot rank prompt methods generally. https://arxiv.org/pdf/2507.13525 |
| Chen et al. (2026), *Promptware Engineering* | Specify functional and non-functional needs, source and instruction boundaries, testable outputs, safe failure behavior, versionable changes, and human/authorization controls. | It is a research roadmap, not empirical proof; prompt text cannot deliver fine-grained access control. https://arxiv.org/pdf/2503.02400 |
| Sahoo et al. (2024), *A Systematic Survey of Prompt Engineering in Large Language Models* | Select techniques by function: examples for demonstrations, authorized retrieval/verification for external knowledge, and task-specific reasoning only when justified. | No technique removes hallucination, bias, or interpretability risks. https://arxiv.org/pdf/2402.07927 |
| Ye et al. (2024), *Prompt Engineering a Prompt Engineer (PE2)* | For repeated failures, use explicit context plus a two-step diagnose/refine loop; separate optimization examples from final evaluation. | Automated prompt optimization is model-dependent and may hallucinate or fail to follow instructions. https://aclanthology.org/2024.findings-acl.21.pdf |
