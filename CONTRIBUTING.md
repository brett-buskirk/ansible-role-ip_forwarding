# Contributing

- **No direct commits to `main`** — branch → PR (`gh pr create`) → green checks → merge.
- **AgentGate runs on every PR** — `secrets` + `dangerous_patterns` block; `scope` is advisory.
- **Commits are signed & Verified**; never commit secrets (`.env`, keys are gitignored).
- Branch naming: `feat/…`, `fix/…`, `docs/…`, `chore/…`.

Lint the role with `ansible-lint` and dry-run changes against a target host with
`ansible-playbook --check` before opening a PR.
