# Trademark and naming policy

OpenTeams holds the Nebari trademark.
This document explains how the name may be used, so that people can tell at a glance whether software is endorsed by the project.

Its aim is narrow: prevent confusion about endorsement, without discouraging anyone from building on the platform or saying truthfully that they have.

## Official packs and repositories

Repositories in the [`nebari-dev`](https://github.com/nebari-dev) organization may use the Nebari name and brand freely.
Being in the organization is what makes a pack [official](pack-policy.md#official-packs), and the name follows from that rather than the other way around.

The organization's own convention is that a pack repository is named for what it integrates, with a `-pack` suffix and no prefix, as in `mlflow-pack` or `data-science-pack`.
The `nebari-` prefix is used for the platform components themselves, such as `nebari-operator` and `nebari-infrastructure-core`.

## Community packs and other downstream work

You do not need permission to build a pack, run the platform, or write about either.

**What is reserved.** Do not use "Nebari" as the leading word of your project's name, as a prefix, or as your own product or company name. A pack called `nebari-forecasting` or a product called "Nebari Pro" reads as something the project publishes, whoever wrote it.

**What is always fine.** Describe what your software does, accurately:

- "a software pack for Nebari"
- "Nebari-compatible"
- "works with Nebari"
- "built on the Nebari Kubernetes Platform"

The distinction is grammatical, and it is a reliable guide: using the word "Nebari" to describe what your project *works with* is fine, and using it to *name* your project is not.

**Also reserved.** Do not use the Nebari logo or brand assets as your project's own logo or icon, and do not describe your work as official, certified, endorsed, or supported by Nebari unless the project has said so in writing.

## Reporting and requests

If you are unsure whether a name is acceptable, or want to ask for an exception, open an issue in this repository and label it `area: governance 🧭`.
For anything you would rather not discuss in public, contact a member of the Core team directly.

Core resolves naming questions.
Where a name is genuinely ambiguous, the project's preference is to ask the author to adjust it, not to escalate.

## Scope and status

This is a project policy about avoiding confusion, not a grant of rights and not legal advice.
Trademark law applies independently of anything written here, and where the two appear to conflict, the trademark holder's position governs.

This policy is changed through the [platform RFD process](GOVERNANCE.md#platform-rfds).
