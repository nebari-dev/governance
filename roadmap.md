# Nebari platform roadmap

This is the **platform** roadmap.
It covers only cross-cutting direction: work that spans repositories, or that changes a contract other repositories depend on.

It is deliberately thin.
The Nebari Kubernetes Platform is a stable infrastructure core plus many independently developed software packs, and each of those repositories keeps its own detailed roadmap.
If you are looking for what a particular pack is doing next, look at that pack's repository, not here.

## Values

These guide platform development.

- We strive for a smooth and productive experience for end-users. This places user experience at the core of everything we build.
- Performance trumps functionality.
- The documentation must be as transparent and accessible as possible.
- We build on open source software. Any changes we make to open source software will be made in public and contributed upstream, so our users continue to have access to them regardless of where their infrastructure is.
- We must not directly depend on proprietary, cloud-vendor-specific products or APIs. This ensures users can port their infrastructure to any cloud provider of their choice, or run it on their own hardware with purely open source software.

Definitions of `MUST`, `MUST NOT`, `SHOULD`, and `MAY` are in [RFC 2119](https://tools.ietf.org/html/rfc2119).

## Legend of annotations

These marks are shared across the project boards and the per-repository roadmaps, so that planning reads the same way everywhere.

| Mark | Description |
| ---- | ----------- |
| 🗃 | work not started, usually in the backlog |
| 📬 | scoped and due to work on |
| 🏗 | ongoing work |
| ✅ | work completed |
| ⛔️ | blocked item |
| 🔮 | stretch goal |

## Current platform direction

Establishing the federated governance model and the contracts it depends on.

### Governance and standards

- 🏗 Adopt federated governance with central contracts
  - ✅ Governance, pack policy, repository standards, and naming policy published in this repository
  - 📬 Rewrite the team structure and decision-making pages on the website to match
  - 📬 Reconcile the RFD issue template with the canonical [RFD lifecycle](GOVERNANCE.md#rfd-lifecycle)
- 📬 Roll out the [repository standards](repository-standards.md) across the organization
  - 📬 Apply organization rulesets for branch protection
  - 📬 Stand up the shared repository-conformance check
  - 🗃 Seed missing required files in existing repositories
  - 🗃 Relicense the remaining repositories to Apache-2.0

### The platform contract

- 📬 Publish the versioned `NebariApp` Pack Specification with the operator
- 📬 Encode the repository-standard defaults and the revised maturity model in the software pack template
- 🗃 Correct the stale `NicApp` references in the infrastructure core

### Deferred

Recorded so they are not mistaken for oversights. Both are described in the [pack policy](pack-policy.md#what-does-not-exist-yet).

- 🔮 A public catalog of community packs
- 🔮 A process for promoting a community pack to official

## Archived roadmaps

The roadmaps below covered **Nebari Classic**, the single monolithic platform shipped from one repository.
That architecture has been replaced, and their content is specific to it, so they are kept as history and are not carried forward.

- [Roadmap for 2023 (archived)](roadmaps/roadmap_2023.md)
- [Roadmap for 2022 (archived)](roadmaps/roadmap_2022.md)
