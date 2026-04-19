# Platform Engineering Gists

Gists for running software in production eg Kubernetes, AWS, observability pipelines, CI/CD, and the developer tooling that makes it livable day to day.

---

## CI/CD

| Gist | What it shows |
|------|---------------|
| [GitHub Actions — monorepo CI + safe deploys](https://gist.github.com/nehasriva/d886232433f1870ca34cececf1305ff7) | `paths-filter` runs only relevant jobs per changed directory; `environment:` scopes secrets AND gates required reviewers; matrix `continue-on-error` for nightly/experimental versions |
| [CircleCI: inject into orb jobs via pre-steps](https://gist.github.com/nehasriva/deb1c82ddda0b8630e17cb02e4af8e91) | `pre-steps`/`post-steps` inject `circleci tests split --split-by=timings` into a prebuilt orb job without forking it; `$BASH_ENV` passes the shard list into the orb's own test command |

---

## Developer Experience

| Gist | What it shows |
|------|---------------|
| [Git hooks + DX shell functions](https://gist.github.com/nehasriva/36f4738cf6a4f8e660c6f5feed383ba4) | `git-summary` one-liner (branch, ahead/behind, staged count, recent commits); pre-push lints only changed files; `prepare-commit-msg` extracts Jira ticket from branch name; `direnv` + 1Password secrets pattern |
| [zsh stopwatch](https://gist.github.com/nehasriva/33bfc4999e6e44e26067610f4955c91e) | cross-platform stopwatch |
| [Slack → KB autodoc config](https://gist.github.com/nehasriva/9a42ba93cb873d53f3c0d6149a88de91) | Regex pattern matching for FAQ/decision/troubleshooting detection; frequency thresholds; KB taxonomy |

---

## Kubernetes & AWS

| Gist | What it shows |
|------|---------------|
| [Deployment probes + rolling update](https://gist.github.com/nehasriva/71bdce909400b170a06ccdb297ac0dd0) | `maxUnavailable: 0` for zero-downtime; `startupProbe` vs inflating `initialDelaySeconds`; CPU throttle vs memory OOMKill distinction |
| [AWS SSM + multi-region Lambda audit](https://gist.github.com/nehasriva/b594053742854668f7cc2e114a50e94a) | `ssm_to_ec2` by Name tag (no SSH, no bastion); `ssm_to_pod` by label; `lambda_audit` fans out across all regions 8-wide with `xargs -P` |

---

## Observability

| Gist | What it shows |
|------|---------------|
| [Sentry recursive PII scrubber](https://gist.github.com/nehasriva/ecd7a5a79efe2ec75462dfebc20d941a) | `before_send` + `before_breadcrumb` hooks; regex key matching + value-pattern scrubbing (email, card, bearer token) across headers, POST body, stack frame locals, and breadcrumbs |
| [Grafana + Tempo datasource provisioning](https://gist.github.com/nehasriva/5e5ef8e1db8e54a89eba5bb3e8859a9d) | Trace-to-log derived field linking Tempo spans to Loki lines; TraceQL reference card; exemplar links from Prometheus graphs |

---

## By Language

| Language | Gists |
|----------|-------|
| **Shell** | AWS SSM helpers · Git hooks & DX toolkit · zsh toolkit |
| **YAML** | Grafana/Tempo provisioning · K8s deployment probes · GitHub Actions CI · CircleCI dynamic matrix · Slack autodoc config |
| **Python** | Sentry PII scrubber |

---

## Tags

`kubernetes` `k8s` `aws` `eks` `ssm` `observability`
`rolling-update` `probes`
`sentry` `grafana` `tempo` `loki` `tracing`
`github-actions` `circleci` `ci-cd` `monorepo`
`direnv` `git-hooks` `dx` `shell` `zsh`
