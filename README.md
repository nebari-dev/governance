<p align="center">
<picture>
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/nebari-dev/nebari-design/main/logo-mark/horizontal/Nebari-Logo-Horizontal-Lockup.svg">
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/nebari-dev/nebari-design/main/logo-mark/horizontal/Nebari-Logo-Horizontal-Lockup-White-text.svg">
  <img alt="Nebari logo mark - text will be black in light color mode and white in dark color mode." src="https://raw.githubusercontent.com/nebari-dev/nebari-design/main/logo-mark/horizontal/Nebari-Logo-Horizontal-Lockup-White-text.svg" width="50%"/>
</picture>
</p>

---

# Governance

This repository holds the governance for the **Nebari Kubernetes Platform**: a stable infrastructure core plus a set of independently developed software packs, each in its own repository.

Authority is federated to match that shape.
Pack maintainers own their repositories, and a small Core team owns the seams between them: the platform contract, the shared conventions, the security baseline, the official designation, and the trademark.

## Start here

⚖️ [Governance](GOVERNANCE.md) - stewardship, scope, teams and roles, how decisions get made, and how to change any of it

📦 [Software pack policy](pack-policy.md) - official and community packs, pack maturity, and the `NebariApp` contract

📋 [Repository standards](repository-standards.md) - licensing, branch protection, required files, and shared conventions

™️ [Trademark and naming](trademark-and-naming.md) - how the Nebari name may be used

## Also here

🤝 [Code of Conduct](CODE_OF_CONDUCT.md) - the complete Code of Conduct, and how to report an incident

🚀 [Platform roadmap](roadmap.md) - cross-cutting direction only. Detailed roadmaps live in each repository

📈 [Documentation analytics](analytics.md) - what is measured on the documentation site, and who can see it

💬 [Requests for Discussion](https://github.com/nebari-dev/governance/issues?q=is%3Aissue+is%3Aopen+label%3A%22type%3A+RFD+%F0%9F%97%B3%22) - open RFD issues

## Elsewhere

Some governance material lives outside this repository, next to the thing it describes:

| What | Where |
| ---- | ----- |
| Team membership requirements, and the step-by-step decision process | [nebari.dev/community/team-structure](https://www.nebari.dev/community/team-structure) and [nebari.dev/community/decision-making](https://www.nebari.dev/community/decision-making) |
| The `NebariApp` Pack Specification | [`nebari-operator`](https://github.com/nebari-dev/nebari-operator) |
| The pack release readiness checklist and metadata schema | [`software-pack-template`](https://github.com/nebari-dev/software-pack-template) and [`software-pack-dashboard`](https://github.com/nebari-dev/software-pack-dashboard) |
| Contribution guidelines | [nebari.dev/community](https://nebari.dev/docs/community) |

## Changing anything in this repository

Everything here is changed through the [platform RFD process](GOVERNANCE.md#platform-rfds): open an RFD issue, let it be discussed, and have Core decide it.
A pull request against these documents should reference the RFD that authorized it.
