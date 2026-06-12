# legal-document-agent-evals-results

Public-safe AgentV result artifacts for the `legal-document-agent-evals` project.

Source eval definitions live in `EntityProcess/legal-document-agent-evals`. This repository stores Dashboard-ready artifacts under `.agentv/results/runs/` only.

Before pushing live artifacts, run a public-artifact leakage check for:

- API keys, bearer tokens, cookies, and provider credentials
- resolved provider endpoints or private network hosts
- private filesystem paths
- `.env` contents
- non-public client, matter, or user data
- raw model/provider logs that may include secrets

Writer credentials should come from a local git/gh session or a token scoped only to this repository where possible. Reader mode is anonymous HTTPS clone/pull.

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
