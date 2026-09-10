# Repository standards

Every public repository in the [`nebari-dev`](https://github.com/nebari-dev) organization meets the standards below.

The point is that nobody re-decides the basics per repository.

How a repository comes to meet them depends on what it is:

- **New packs inherit them.** The [software pack template](https://github.com/nebari-dev/software-pack-template) carries the defaults, so a new pack starts compliant instead of being brought into line later.
- **Everything else has them applied directly.** There is no non-pack template repository, so a repository like this one gets the required files seeded into it and is held to the standard by [enforcement](#how-this-is-enforced-and-where-enforcement-stops) rather than by inheritance.

That asymmetry is worth being explicit about, because the standards apply to every public repository in the organization while only one kind of repository inherits them automatically.

## Licensing

All public repositories in the organization are licensed **Apache-2.0**.

## Branch protection

On the default branch, the following are **required**:

- a pull request before merge, with no direct pushes
- at least one approving review, from a maintainer or a `CODEOWNERS` owner
- passing status checks for lint and tests
- stale approvals dismissed when new commits are pushed
- force-push and branch deletion blocked

Squash-merge is the default merge style.

The following are **recommended but not required**, deliberately:

- **Signed commits.** Real friction for a team of this size, and enforcement tends to block contributors at the worst moment.
- **Strictly up-to-date branches before merge.** Causes merge queues to thrash on small teams.
- **Linear history.** Conflicts with the squash-merge default above.

Owners may bypass protection in an emergency.
When they do, they say so in the pull request or an issue, and say why.
An undocumented bypass is the thing this rule exists to prevent.

## Required files

Every public repository has:

| File | Purpose |
| ---- | ------- |
| `README.md` | What this is, and how to get started |
| `LICENSE` | Apache-2.0 |
| `CODE_OF_CONDUCT.md` | The organization [Code of Conduct](CODE_OF_CONDUCT.md), or a link to it |
| `CONTRIBUTING.md` | How to contribute, pointing at the organization governance |
| `MAINTAINERS.md` | Who maintains this repository. The authoritative list for it |
| `SECURITY.md` | How to report a vulnerability |
| `GOVERNANCE.md` | A stub linking to [the organization governance](GOVERNANCE.md), stating the repository's tier and the Pack Specification version it targets |
| `.github/` | Issue and pull request templates, `CODEOWNERS`, and CI workflows |

Software packs additionally carry `pack-metadata.yaml` at the repository root, as described in the [pack policy](pack-policy.md#maturity-and-release-readiness).

## Documentation layout

- `docs/` holds narrative documentation.
- `docs/adr/` holds architecture decision records. The infrastructure core already works this way, and it is the standard for the organization.
- Releases carry notes, and repositories keep a changelog.

## Shared conventions

**Labels.** Repositories use the organization's existing label set, with the `type:`, `status:`, `needs:`, `area:`, `impact:`, and `priority:` prefixes. The RFD labels in particular are shared across the organization rather than redefined per repository, so that the [RFD lifecycle](GOVERNANCE.md#rfd-lifecycle) means the same thing everywhere.

**Versioning.** Releases use [EffVer](https://jacobtomlinson.dev/effver/), written `Macro.Meso.Micro` and tagged with a leading `v`. The numbers describe the effort an upgrade costs the people consuming the release, not how much work it was to build:

| Segment | Means |
| ------- | ----- |
| Micro | A drop-in. No action needed by existing users |
| Meso | Some effort. A small breaking change or a larger fix |
| Macro | Significant effort. Users should plan time to upgrade |

Before `1.0.0`, EffVer collapses to `0.Macro.Micro`.
Tags are not prefixed with the repository name: one repository, one tag scheme.

**Contract version.** Packs declare which [Pack Specification](pack-policy.md#the-contract) version they target.

## How this is enforced, and where enforcement stops

This section is deliberately honest about the limits, because a standard that claims more enforcement than it has is worse than one that admits the gap.

- **GitHub organization rulesets** enforce the branch-protection items wherever they technically can. This is the strongest layer and needs no human attention.
- **A shared repository-conformance check** covers what rulesets cannot see: that the required files are present, that the license really is Apache-2.0, and that `pack-metadata.yaml` validates against its schema.
- **The [release readiness checklist](pack-policy.md#maturity-and-release-readiness)** is the human backstop for everything neither of the above can judge.

Nothing here can verify that a `README.md` is *useful* or that a `SECURITY.md` describes a process anyone follows.
That is what review is for.

**Open question: whether to stand up a non-pack template repository.** Today the inheritance path only exists for packs, so every other repository depends on the enforcement layers above plus a one-time seeding of the required files. A second template would close that gap for new non-pack repositories, at the cost of another repository to maintain. Raised by @viniciusdc on the RFD and not settled by it.

## Changing these standards

These standards are changed through the [platform RFD process](GOVERNANCE.md#platform-rfds).
