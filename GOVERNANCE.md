# Nebari governance

This document describes how the Nebari project is governed: who decides what, how those decisions are made, and how this document itself is changed.

It covers the [Nebari Kubernetes Platform](#scope) as a whole.
Detailed team membership requirements and the step-by-step decision process live on the Nebari website, which stays the canonical reference for both:

- [Team structure and roles](https://www.nebari.dev/community/team-structure)
- [Decision-making processes](https://www.nebari.dev/community/decision-making)

## Stewardship

Nebari is company-led, and this document says so plainly rather than describing a neutrality the project does not yet have.

OpenTeams employs the core maintainers, holds the Nebari trademark, and drives the platform roadmap.
The project operates on a benevolent-steward model: decisions rest with a small Core team, and that team is accountable for keeping the platform coherent.

Two things follow, and both are meant sincerely:

- Outside contributors and third-party software packs are genuinely welcome. The contract a pack builds against is public, and nothing in it requires the pack to live in this organization.
- A path toward broader community or foundation governance is left open. It is not claimed to exist today, because there is currently no multi-organization maintainership to support it.

## Scope

This governance applies to the [`nebari-dev`](https://github.com/nebari-dev) GitHub organization: the Nebari Infrastructure Core, the Nebari Operator, the official software packs, the software pack template, and this repository.

It does not govern third-party packs hosted outside the organization.
For those it defines only two things: the [Pack Specification](pack-policy.md#the-contract) they must satisfy in order to work, and the [naming rules](trademark-and-naming.md) they must respect so that they do not imply official endorsement.

## Architecture this governance assumes

The platform is federated, and the governance is shaped to match it.

- The **Nebari Infrastructure Core** provisions an opinionated Kubernetes cluster and the foundational layer: Keycloak for single sign-on, Envoy Gateway for routing, cert-manager for TLS, and the Nebari Operator.
- **Software packs** are Helm charts that register with the platform through a `NebariApp` custom resource and inherit authentication, routing, and TLS from it. Each pack lives in its own repository, on its own release cycle.
- The **Nebari Operator** defines the `NebariApp` custom resource and reconciles it into the underlying routes, certificates, policies, and identity-provider clients.

Authority is federated to match: pack maintainers own their repositories, and the Core team owns only the seams between them.

## Teams and roles

Access follows least privilege and is granted **per repository**.
There is no organization-wide blanket commit role.

| Team | Scope of authority | Access |
| ---- | ------------------ | ------ |
| **Core** | The cross-cutting seams: the Pack Specification, the single-sign-on, routing and TLS conventions, the security baseline, the official designation, trademark and naming, the platform roadmap, and the final call on platform RFDs | Per repository, as needed |
| **Owners** | Implements Core decisions in GitHub: organization membership, repository creation, rulesets | Organization administration |
| **Pack maintainers** | Their own repository: features, releases, and day-to-day decisions | Write or admin on that repository only |
| **Contributors** | Contribution by pull request | Commit or triage granted per repository by that repository's maintainers |
| **Code of Conduct Response** | Enforcing the [Code of Conduct](CODE_OF_CONDUCT.md) | Organization-wide, for that purpose |
| **Emeritus** | Recognition for members who have stepped back, with a path to return | None |

Notes on what changed and why:

- **Core keeps its name, and its mandate is narrower.** Core owns the seams, not every repository. The name is kept for continuity with the project's history, which was judged more valuable than the clearer signal a rename to something like "Steering" would have given.
- **Pack maintainers are listed in each repository's `MAINTAINERS.md`.** That file, not this document, is the authoritative list for a given pack.
- **Special Interest Groups are retired** as a standing concept, because the pack repository is now the natural working-group unit. Core may still convene an ad-hoc working group for a genuinely cross-cutting topic such as security or documentation.
- **Triage is a per-repository grant, not a standing team.** Triage access is given by a repository's maintainers on the same basis as commit access. Members of the previous organization-wide Triage team keep triage access on the repositories they are active in.
- At least one member of the Code of Conduct Response team also sits on Core, and all of its members are trained.

## Decision-making

There are two lanes, and the first one covers the overwhelming majority of decisions.

### Pack-local decisions

Anything confined to a single repository is decided by that repository's maintainers, through ordinary issue and pull request review.
This includes the pack's features, its dependencies, its release timing, and its own maturity level.
No RFD is required, and nothing needs to be routed through Core.

### Platform RFDs

A Request for Discussion is required only for a change that crosses repository boundaries or alters a contract other repositories depend on:

- the Pack Specification or the `NebariApp` custom resource
- the single-sign-on, routing, or TLS conventions
- the security baseline
- the [repository standards](repository-standards.md)
- the [pack maturity model](pack-policy.md#maturity-and-release-readiness)
- this governance, and the policies in this repository
- behavior in the Nebari Infrastructure Core that packs rely on

A platform RFD is filed as an issue in this repository, discussed openly, and decided by Core through the consent-based process on the website.
A proposal is accepted when more than half of Core votes yes.

The mechanics are spelled out here so that anyone can reproduce a tally from the issue itself, months later, without asking who counted what:

- **A yes vote** is a 👍 or ❤️ reaction on the issue from a Core member. Both count.
- **👀 is not a vote.** Neither is any other reaction.
- **The denominator** is the human membership of the [`core-team`](https://github.com/orgs/nebari-dev/teams/core-team) GitHub team. Bot accounts in that team, such as `nebari-sensei`, are excluded from it. That team is the authoritative record of who Core is, so it needs to be accurate.
- **Where a decision is taken synchronously**, in a meeting rather than by reaction, the outcome is recorded as a comment on the issue naming the date and who was present. An unrecorded meeting decision cannot be audited later, and is treated as not yet decided.

### RFD lifecycle

The issue template and the website previously described RFD state in two different vocabularies, which drifted.
The status values below are canonical.
Each one maps to exactly one label, and an RFD carries **exactly one** status label at a time.

| Status | Label on the issue | Meaning |
| ------ | ------------------ | ------- |
| Draft 🚧 | `type: RFD 🗳` alone | Filed, not yet ready for comment |
| Open for comments 💬 | `needs: discussion 💬` | Open for discussion and objections |
| Being voted 🗳 | `status: being voted 🗳` | Comments addressed, Core is voting |
| Accepted ✅ | `status: approved 💪🏾` | Passed the vote, implementation not finished |
| Implemented 🚀 | `status: approved 💪🏾`, issue closed | Landed |
| Rejected ⛔️ | `status: declined 🙅🏻‍♀️` | Did not pass, or was withdrawn |
| Obsolete 🗃 | `status: declined 🙅🏻‍♀️`, issue closed | Overtaken by events |

Every RFD also carries `type: RFD 🗳` for its whole life.
Where the Status row in the issue body and the labels disagree, the Status row is authoritative and the labels should be corrected to match it.

## Amending this governance

This governance, and every policy document in this repository, is changed through the platform RFD process described above.

That means: file an RFD issue in this repository, let it be discussed, and have Core decide it.
A pull request that changes these documents should reference the RFD that authorized it.

## Policies in this repository

| Document | Covers |
| -------- | ------ |
| [Code of Conduct](CODE_OF_CONDUCT.md) | Expected behavior, and how to report an incident |
| [Pack policy](pack-policy.md) | Official and community tiers, maturity, and the platform contract |
| [Repository standards](repository-standards.md) | Licensing, branch protection, required files, and shared conventions |
| [Trademark and naming](trademark-and-naming.md) | Use of the Nebari name and brand |
| [Platform roadmap](roadmap.md) | Cross-cutting platform direction |
| [Documentation analytics](analytics.md) | What is measured on the documentation site, and who can see it |
