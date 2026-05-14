## CI/CD & Deployment Guidelines — Fun Summary 🎉

Hey there 👋

Welcome to the short and friendly edition of Tzu Chi Foundation Malaysia's CI/CD & Deployment Guidelines. Think of this as the TL;DR that helps you ship confidently, securely, and with a little joy.

### Quick Snapshot

- ⚡ Automation: Let pipelines handle builds, tests, scans, and pushes—robots FTW.
- 🔒 Security: Never store secrets in code; use Azure Key Vault or Kubernetes Secrets.
- 🧭 Governance: Tzu Chi DevOps owns the CI/CD platform—follow the playbook.

### Do's (high-five-worthy actions)

- Branch like a pro: `main`, `develop`, `feature/*`, `hotfix/*`.
- Run tests and linters locally—your future self will thank you.
- Build images via CI (multi-stage + non-root runtime users).
- Tag images `{project}:{git-commit-sha}` or `{project}:{buildid}` and let CI push to ACR.
- Keep Kubernetes manifests in `/k8s` and set resource requests/limits.
- Add health and readiness endpoints—probes keep rollouts smooth.
- Inject secrets at runtime (Azure Key Vault or Kubernetes CSI driver).
- Put migration scripts in the repo and run them from the pipeline.
- Use pipeline approvals for staging/production and monitor deploys.
- Configure automated rollback so mistakes become small stories.

### Don'ts (seriously, don't 😬)

- 🚫 Don't commit secrets, API keys, certificates, or private keys.
- 🚫 Don't push images to ACR from your laptop—CI does it for a reason.
- 🚫 Don't bypass or alter pipeline logic without DevOps approval.
- 🚫 Don't make manual production changes or untracked DB edits.
- 🚫 Don't skip health probes or forget resource limits.

### Want the full manual?

For the full technical guidance (architecture, container standards, repo/Kubernetes rules, DB migration policies, and governance), open the original doc: [CI_CD and Deployment Guidelines for Developers.docx](../CI_CD%20and%20Deployment%20Guidelines%20for%20Developers.docx).

Last updated: 2026-05-14
