# legal-document-intelligence-evals-results

Public-safe AgentV result artifacts for the `legal-document-intelligence-evals` project.

Source eval definitions live in `EntityProcess/legal-document-intelligence-evals`. This repository stores Dashboard-ready artifacts under `.agentv/results/runs/` only.

Before pushing live artifacts, run a public-artifact leakage check for:

- API keys, bearer tokens, cookies, and provider credentials
- resolved provider endpoints or private network hosts
- private filesystem paths
- `.env` contents
- non-public client, matter, or user data
- raw model/provider logs that may include secrets

Writer credentials should come from a local git/gh session or a token scoped only to this repository where possible. Reader mode is anonymous HTTPS clone/pull.

## Static HTML report

- [Dashboard-style static report](docs/index.html) — generated with `agentv results report .agentv/results/runs/live-document-intelligence-2026-06-13T22-50-31Z --out docs/index.html`.
- Published GitHub Pages URL: https://entityprocess.github.io/legal-document-intelligence-evals-results/

GitHub Pages serves the `docs/` directory as the project homepage. The HTML is self-contained and read-only; no AgentV Dashboard server is required.

## Layout

```text
.agentv/results/runs/
  .gitkeep
  <experiment>/
    <timestamp>/
      benchmark.json
      index.jsonl
      transcript.jsonl
      <suite>/<test-id>/...
```

Keep `auto_push: false` in local AgentV config until a human approves publication of a run.
