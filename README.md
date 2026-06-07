# GitHub Security Blueprint

A template repository for bootstrapping secure GitHub projects. Copy these files into a new repo to get baseline security tooling from day one.

## What's included

| File | Purpose |
|------|---------|
| `.github/workflows/security.yml` | CI pipeline: secret scanning (Gitleaks) + vulnerability/IaC scanning (Trivy); triggers on push, PR, and manual dispatch; Trivy findings uploaded to the GitHub Security tab; stale PR runs cancelled automatically |
| `.github/dependabot.yml` | Weekly automated dependency updates for GitHub Actions, Terraform, and Docker |
| `.gitleaks.toml` | Gitleaks configuration; add allowlist entries for test fixtures here |
| `.trivyignore` | Document accepted CVEs here with justification |
| `SECURITY.md` | Vulnerability disclosure policy |
| `.gitignore` | Excludes secrets, Terraform state, and editor noise |

## Usage

1. Click **Use this template** to create a new repository.
2. Update `SECURITY.md` with your contact details and response SLA.
3. Enable GitHub Actions in your new repo — the security workflow runs automatically.
4. Review `.trivyignore` and `.gitleaks.toml` and remove any entries that don't apply.

## Keeping actions up to date

All actions in `security.yml` are pinned to commit SHAs to prevent supply-chain attacks. Dependabot will open PRs when new versions are available — review and merge those to stay current.
