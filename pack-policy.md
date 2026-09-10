# Software pack policy

Nebari is a platform plus a set of independently developed software packs.
This document is the policy about those packs: which ones the project endorses, what they must satisfy, and who may change the rules.

It deliberately does not restate the technical contract or the promotion checklist.
Those live with the code that enforces them, and this document points at them so there is only one copy of each.

## Tiers

There are two tiers, on a single axis: where the pack lives, and whether the project endorses it.

### Official packs

Official packs live in the [`nebari-dev`](https://github.com/nebari-dev) organization.
They carry the Nebari name and brand, and in exchange they must:

- satisfy the [Pack Specification](#the-contract)
- adopt the [maturity model](#maturity-and-release-readiness) and declare a level
- meet the [repository standards](repository-standards.md)

The `nebari-dev` organization contains only official packs.
Placing a pack there is the act that makes it official, and that decision belongs to Core.

### Community packs

Community packs live anywhere outside the organization.
They must:

- satisfy the [Pack Specification](#the-contract), which is simply what it takes to work
- follow the [naming rules](trademark-and-naming.md), so that they do not imply official endorsement

They are not required to adopt the maturity model, and the project makes no claim about their quality or support.

### What does not exist yet

**There is no public catalog of community packs.** Publishing one would mean signaling something about the security and maintenance of software the project does not maintain, and would read as endorsement whatever the disclaimer said. This is deferred rather than ruled out.

The [pack dashboard](https://github.com/nebari-dev/software-pack-dashboard) is a different thing: it is an internal view of official packs only, built from their metadata files.

**There is no process for promoting a community pack to official.** The project intends to define one, and records that intent here so it is not forgotten. Until it exists, a pack becomes official only by Core deciding to adopt it into the organization.

## Maturity and release readiness

Maturity is **orthogonal to tier**.
The tier says where a pack lives and whether it is endorsed; the maturity level says how production-ready it is.
An official pack can be Experimental, and saying so plainly is the point of the model.

The authority for maturity levels and promotion requirements is the [release readiness checklist](https://github.com/nebari-dev/software-pack-template/blob/main/docs/release-readiness-checklist.md) in the software pack template.
It is required for every official pack, which per the tiers above means every pack in the organization.

In outline: a pack moves through **Experimental**, **Alpha**, **Beta**, and **GA**, with **Deprecated** as an orthogonal status that can apply at any level.
Each pack declares its state in a `pack-metadata.yaml` file at its repository root.
Promotion is a pull request against that file, gated by a checklist whose items escalate with the target level.

### Sign-offs are operational roles, not governance roles

The checklist requires named sign-offs to promote a pack.
Those roles - product owner and tech lead - are operational, and this governance does not create or define them.
The checklist is the single authority for who signs off on what, so that the two documents cannot drift.

Pre-sales lead is **not** a sign-off role. It is a commercial function with no bearing on whether software is ready to release.

### Revisions adopted here

These are policy decisions about the maturity model. The corresponding edits to the checklist and metadata schema land with that work, in the repositories that own them.

- **Versioning is stated in [EffVer](https://jacobtomlinson.dev/effver/) terms.** Experimental, Alpha, and Beta sit on the `0.x` line; GA means `1.0.0` and above. "GA (v1.0+)" is the same rule said less precisely, and EffVer is the organization-wide convention in the [repository standards](repository-standards.md#shared-conventions).
- **Integration checks point at the contract.** The `nebariapp_integration` field and every integration item reference the [Pack Specification](#the-contract) rather than restating what integration means.
- **Security items point at the security baseline.** The checklist references the single Core-owned baseline instead of maintaining a parallel list that can fall behind it.
- **Metadata declares a target Pack Specification version.** This ties a pack's maturity tracking to the version of the contract it was built against, so an upgrade to the contract shows up as work the pack owes.

## The contract

The contract between the platform and the packs is the **`NebariApp`** custom resource.
A pack registers with the platform by creating one, and inherits single sign-on, routing, and TLS from the operator that reconciles it.

`NebariApp` is the canonical name.
Older `NicApp` references in the infrastructure core's documentation are stale and are being corrected.

Where things live, and why:

- The **Pack Specification** lives with [`nebari-operator`](https://github.com/nebari-dev/nebari-operator), alongside the custom resource definition it describes and the reconcilers that enforce it. Specification and implementation version together and cannot silently drift.
- **This repository holds the policy about the specification**: that Core owns it, that changing it requires a platform RFD, and how it relates to tiers and maturity. It does not hold the specification text.

The specification is versioned with EffVer and covers the `NebariApp` resource and registration, single sign-on through Keycloak, routing through Envoy Gateway, TLS through cert-manager, and the security baseline.

## Changing this policy

Core owns this document, the Pack Specification, and the maturity model.
All three are changed through the [platform RFD process](GOVERNANCE.md#platform-rfds).
