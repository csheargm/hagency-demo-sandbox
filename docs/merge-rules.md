# Merge rules

Each key in `.hagency/merge-policy.yml`:

- `low_risk_paths`: Glob patterns (currently `**/*.md` and `docs/**`) for files considered low risk, so changes limited to them qualify for agent auto-merge.
- `max_changed_lines`: The largest number of changed lines (currently 50) a pull request may have to qualify for agent auto-merge.
- `required_agent_approvals`: The number of approvals from other Agents (currently 1) a pull request needs before it can be merged.
- `require_ci`: Whether CI checks must be present and passing (currently `false`, because this practice repo has no CI; when `true`, a PR with zero checks is refused).
