# Live document-intelligence eval results

Run: `live-document-intelligence-2026-06-13T22-50-31Z`  
Source PR: https://github.com/EntityProcess/legal-document-agent-evals/pull/1  
Target: `document-intelligence` / `legal-document-agent-stateful-swarm`  
Provider: local OpenAI-compatible endpoint, endpoint and key not published; model `gpt-5.4-mini`  
Result: 4/4 cases completed with `execution_status: ok`; mean score 40.0%.

This is a green live integration check for the AgentV-native document-intelligence/stateful-swarm target: live target calls, live LLM grading, and AgentV artifact generation completed. It is not a claim that the model output quality is high.

| Case | Score | Rubric checks | Email source |
| --- | ---: | ---: | --- |
| `corporate-ma-extract-change-of-control-provisions` | 43.6% | 24/55 | none |
| `litigation-dispute-resolution-compare-document-production-against-discovery-requests` | 23.9% | 11/46 | `documents/meet-confer-emails.eml` |
| `data-privacy-cybersecurity-assess-breach-notification-obligations-across-affected-jurisdictions` | 43.5% | 20/46 | `documents/client-notification-email-thread.eml` |
| `banking-finance-compare-credit-agreement-against-term-sheet` | 48.5% | 16/33 | `documents/lender-counsel-transmittal.eml` |

## Published artifacts

- `index.jsonl` — AgentV per-case result index and grader summaries.
- `benchmark.json` — aggregate run metadata and grader summary.
- `timing.json` — aggregate timing/token counters.
- `transcript.jsonl` — public-safe task/response transcript.
- `legal-document-agent/<test-id>/` — per-case input, response, grading, timing, and task config artifacts.

## Sanitization notes

- Provider logs, local live-run logs, `.env` files, OAuth files, and raw `.agentv/harness-artifacts/` directories are not published.
- The local absolute eval path in `benchmark.json` was rewritten to `evals/legal-document-agent.eval.yaml`.
- Transcript metadata fields that pointed at raw harness-artifact directories were redacted.
- No loopback provider endpoint or API key value is included in this published run.
