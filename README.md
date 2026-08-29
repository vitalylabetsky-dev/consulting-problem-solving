# Consulting Problem Solving (Codex)

Short
This repository contains a consulting problem‑solving skill adapted for Codex: codeable templates, programmatic prompts, and example cases to produce structured analyses and client recommendations.

Коротко (RU)
Репозиторий — набор шаблонов и кейсов для Codex, чтобы автоматически генерировать структурированные выводы по консалтинговым задачам.

Repository structure
- examples/      — ready-made cases and input prompts
- templates/     — prompt templates and JSON output schemas
- tests/         — deterministic test prompts and expected outputs
- scripts/       — utilities for running tests and examples
- CONTRIBUTING.md — contribution guidelines (recommended)
- LICENSE         — project license (suggested: MIT)

Quick start — Codex (curl)
Replace $OPENAI_API_KEY and <PROMPT> accordingly.

curl https://api.openai.com/v1/completions \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "code-davinci-002",
    "prompt": "<PROMPT>",
    "max_tokens": 400,
    "temperature": 0.2,
    "stop": ["###"]
  }'

Prompt template for Codex (recommended)
Use a clear instruction, an explicit output schema (prefer JSON), and one or two short examples.

Example prompt (template):
You are Codex. Given the consulting case below, produce a JSON object with fields:
- context: short summary
- facts: bullet list
- hypotheses: array of hypotheses (1–5)
- analysis_plan: steps to validate hypotheses
- recommendations: array of 3 client-ready recommendations (each with rationale)
- next_steps: 3 actionable next steps

Case:
{client_name: "<CLIENT>", industry: "<INDUSTRY>", goal: "<GOAL>", constraints: "<CONSTRAINTS>", data: "<KEY_FACTS>"}

Desired output (JSON):
{
  "context": "...",
  "facts": ["..."],
  "hypotheses": ["..."],
  "analysis_plan": ["..."],
  "recommendations": [
    {"recommendation":"...","rationale":"..."}
  ],
  "next_steps": ["..."]
}

Example minimal invocation (replace placeholders programmatically)

```python
prompt = TEMPLATE.replace("<CLIENT>", client).replace("<GOAL>", goal)
# send prompt to OpenAI/Codex completion endpoint
```

Testing + CI
- Put deterministic test prompts in tests/ and expected JSON outputs in tests/expected/.
- CI job: call Codex with test prompts and compare parsed JSON to expected (order-insensitive key comparison).
- Use low temperature (0.0–0.2) for deterministic results.

Guidelines for adding templates
- Always provide an explicit schema (JSON) for outputs.
- Provide 1–2 examples demonstrating edge cases.
- Keep prompts idempotent and include constraints (token limits, style).

Contributing
See CONTRIBUTING.md — include guidelines for prompt formatting, test creation, and how to add new example cases.

License
Add LICENSE (suggested: MIT).

Contact
vitalylabetsky-dev — for questions and suggestions.
