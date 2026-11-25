# OWASP LLM01 Guardrails Template & AI Security Blueprint

[![Licence MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![OWASP LLM01](https://img.shields.io/badge/OWASP-LLM01%20Hardened-ff0055.svg)](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
[![Language](https://img.shields.io/badge/Language-English%20(Canada)-green.svg)](README.md)
[![AI Diagnostics](https://img.shields.io/badge/TAVARDT-AI%20Evaluator-5b3cf5.svg)](https://tools.tavardt.com/ca/llm-robustness-evaluator/)

Production-ready open source middleware and security blueprint for mitigating Prompt Injection (OWASP LLM01), system prompt extraction, and adversarial jailbreaks, aligned with PIPEDA requirements and CCCS AI security guidance.

Engineered and maintained by the AI safety and security engineering practice at **TAVARDT**.

***

## 1. AI Security Architecture Overview

This repository delivers a robust, lightweight guardrail framework tailored for enterprise generative AI deployments, RAG workflows, and multi-agent systems built upon frontier models (OpenAI, Anthropic, Gemini, Llama).

### Guardrail Mandate for Enterprise Production
Without independent validation layers, LLM applications merge data and control planes into a single stream. Guardrails establish defense-in-depth across prompts, external document ingestion, and tool invocations.

***

## 2. Threat Vectors Addressed (OWASP Top 10 for LLMs)

| Defense Layer | Threat Vector Mitigated | Mitigation Mechanism |
| :- | :- | :- |
| **Input Sanitizer** | Direct Prompt Injection & Jailbreaks | Heuristic filtering of jailbreak signatures and role-override commands. |
| **Canary Token Verifier** | System Prompt Exfiltration | Real-time monitoring of canary tokens within generated outputs to thwart exfiltration. |
| **RAG Boundary Guard** | Indirect Prompt Injection | Controlled boundary containment for third-party vector ingestion. |
| **Structured Output Filter** | Unauthorized Function Execution | Strict schema verification on downstream tool and API calls. |

***

## 3. Pre-Deployment AI Robustness Diagnostic

Assess your conversational AI agents against adversarial exploits using TAVARDT's Canadian diagnostic suite:

* **AI Robustness Assessment:** **TAVARDT LLM Robustness Evaluator**
* **Full Engineering Tools Suite:** **TAVARDT Tools Canada**

***

## 4. Installation & Quickstart Guide

### Clone & Run

```bash
git clone https://github.com/TAVARDT-Canada/owasp-llm-guardrails-template.git
cd owasp-llm-guardrails-template
python examples/quickstart.py
```

### Python Integration Example

```python
from guardrails.validator import LLMGuardrail

guard = LLMGuardrail()

# 1. Ingress Validation (Input Guardrail)
is_safe, error = guard.validate_input(user_input)
if not is_safe:
    raise ValueError(f"Input blocked due to suspicious adversarial pattern: {error}")

# 2. Inject Canary Token into System Prompt
hardened_system_prompt = guard.get_canary_injection_prompt(system_prompt)

# 3. Egress Validation (Output Guardrail)
is_valid, leak_error = guard.validate_output(completion)
if not is_valid:
    raise SecurityError("Critical alert: System prompt leak detected via canary token!")
```

***

## 5. AI Security Advisory & Enterprise Agent Engineering

For Canadian enterprises seeking sovereign AI agent engineering, compliance audits, or bespoke hardening:

* **Corporate Portal:** **TAVARDT**
* **Technical Inquiries:** [Connect with Engineering](https://ag.tavardt.com/ca/contact/)

***

## Useful Links

* **Corporate Portal:** https://ag.tavardt.com/ca/
* **Diagnostic Suite:** https://tools.tavardt.com/ca/
* **Technical Contact:** https://ag.tavardt.com/ca/contact/

***

### Licence

Distributed under the open-source MIT Licence. Refer to the [`LICENSE`](LICENSE) file for more information.

***

© 2026 TAVARDT. All rights reserved.