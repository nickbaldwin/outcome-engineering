5-types-of-automated-evals.md



# 5 types of automated evals

Last week we covered common eval mistakes. This week’s flashcard answers a natural follow-up: once you’ve done error analysis and identified failures worth tracking, what types of automated evaluators should you build?

There are three main types, each with different tradeoffs.

1. Code-based assertions

These check for objective, rule-based failures: valid JSON, SQL syntax, presence of required keywords, tool execution errors. They’re fast, cheap, deterministic, and interpretable. Use them whenever possible.

2. LLM-as-a-judge

These use an LLM to assess subjective or nuanced criteria that code can’t capture: tone, helpfulness, whether a response adequately addresses the user’s concern.

LLM judges are powerful but expensive. They require labeled examples to validate, ongoing maintenance, and coordination between developers and domain experts. Reserve them for failure modes where code-based checks genuinely can’t work.

3. Guardrails

Guardrails are evaluators that run in the request/response path, blocking failures before they reach the user. If a guardrail triggers, the system can redact, refuse, or regenerate.

Because guardrails run synchronously, they must be fast and have low false positive rates. A guardrail that incorrectly blocks valid responses is a production bug. For this reason, guardrails are typically code-based checks or small classifiers, not LLM judges.