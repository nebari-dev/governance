# AGENTS.md

Guidance for coding agents working in this repository.

## What this repository is

`nebari-dev/governance` holds the governance for the Nebari Kubernetes Platform: the governance document itself, the software pack policy, the repository standards, the trademark and naming policy, the Code of Conduct, the platform roadmap, and the documentation analytics policy.

It is documentation only.
There is no application code, no dependency manifest, no build, no test suite, no linter, and no CI workflow.
Apart from the GitHub issue forms, the license, and dotfiles, every file is Markdown.

Two things follow from that:

- There are no build, lint, or test commands to run, and adding tooling for them is not a side effect of a content change.
- Verification means reading the diff for factual accuracy and confirming that relative links still resolve. See [checking your work](#checking-your-work).

## The one rule that is easy to get wrong

**Everything in this repository is normative, and changing it requires an accepted RFD.**

These documents are not descriptions that can be tidied up to match reality. They are the policy that reality is measured against. A wording change to `GOVERNANCE.md`, `pack-policy.md`, `repository-standards.md`, or `trademark-and-naming.md` is a governance change, even when it looks editorial.

So before changing any of them, find the RFD that authorizes it, and reference that RFD in the pull request.
If there is no RFD, the change is either a genuine typo fix or it is out of scope, and it is worth asking which.

Fixing a broken link, a typo, or a stale cross-reference does not need an RFD.
Rewording a requirement does, including turning a "should" into a "must".

## Structure, and why it is shaped this way

### Policy is split by topic, and cross-references are load-bearing

| File | Holds |
| ---- | ----- |
| `GOVERNANCE.md` | Stewardship, scope, teams and roles, the two decision lanes, the RFD lifecycle, the amendment clause |
| `pack-policy.md` | Official and community tiers, pack maturity, the `NebariApp` contract |
| `repository-standards.md` | Licensing, branch protection, required files, docs layout, shared conventions, enforcement |
| `trademark-and-naming.md` | Use of the Nebari name and brand |
| `CODE_OF_CONDUCT.md` | Entry point for the Code of Conduct, which is split further (below) |
| `roadmap.md` | Cross-cutting platform direction only |

These files link to each other by anchor, and the anchors carry meaning: `pack-policy.md` points at `repository-standards.md#shared-conventions`, several files point at `GOVERNANCE.md#platform-rfds`, and `README.md` points at most of them.
Renaming a heading silently breaks those links, so grep for the old anchor before renaming one.

### Authority lives next to what it governs, deliberately

Much of the material these documents refer to is intentionally **not** here, and moving it here would be a governance change rather than a cleanup:

- **Team membership requirements and the step-by-step decision process** live on the website, at `nebari.dev/community/team-structure` and `nebari.dev/community/decision-making`.
- **The `NebariApp` Pack Specification** lives with `nebari-operator`, so the contract and the code that enforces it version together.
- **The pack release readiness checklist** lives in `software-pack-template`, and the `pack-metadata.yaml` schema in `software-pack-dashboard`.

When a document here describes one of those, it should point at it rather than restate it.
If you find this repository and one of those sources disagreeing, the source next to the implementation usually wins, and the drift is worth reporting rather than silently patching.

Note that the real repository names are unprefixed: `software-pack-template`, `mlflow-pack`, `data-science-pack`. Only the platform components carry a `nebari-` prefix, as in `nebari-operator`.

### The Code of Conduct is one document split across five files

`CODE_OF_CONDUCT.md` at the root is the entry point.
It states the commitment and the scope, names the reporting route, and links to the four parts under `code-of-conduct/`.

Substantive changes belong in the relevant part file rather than in the root summary.
The scope paragraph is duplicated in `CODE_OF_CONDUCT.md` and `code-of-conduct/coc_details.md`, so a change to scope has to touch both.

The committee names and email addresses in `coc_enforcement.md` are live reporting contacts, and `CODE_OF_CONDUCT.md`, `coc_details.md`, and `coc_reporting.md` all link to that section.
Change them only on explicit instruction, and update every reference in the same change.

### The roadmap is thin on purpose, and the old ones are frozen

`roadmap.md` covers only cross-cutting platform direction.
Detailed roadmaps live in each pack's own repository, so resist the pull to make this file comprehensive.

`roadmaps/roadmap_2022.md` and `roadmaps/roadmap_2023.md` covered Nebari Classic, the previous monolithic architecture.
They are archived, carry a banner saying so, and are not maintained.
Do not update their status marks, and do not migrate their content forward.

The status marks are shared vocabulary, not decoration.
The legend in `roadmap.md` defines 🗃 (not started), 📬 (scoped), 🏗 (ongoing), ✅ (complete), ⛔️ (blocked), and 🔮 (stretch goal), and the same marks are used on the project boards and in per-repository roadmaps.
Reuse them exactly, and do not introduce new ones.

### Some files here are copies, and local edits to them get overwritten

A sync bot pushes several files into this repository from `nebari-dev/.github`.
Editing them here is lost on the next sync, so the change belongs upstream instead.
`.github/sync.yml` in that repository is the authority for what is synced where; as of this writing it covers:

| File here | Notes |
| --------- | ----- |
| `LICENSE` | Synced today, which means one edit upstream relicenses seven repositories at once. [nebari-dev/.github#50](https://github.com/nebari-dev/.github/pull/50) removes it from the sync so each repository owns its own license |
| `CONTRIBUTING.md` | Shared across the same group |
| `.github/PULL_REQUEST_TEMPLATE.md` | Shared across the same group |
| `.github/ISSUE_TEMPLATE/*` | Shared, except `RFD.md`, which has its own rule targeting only this repository |

Run `git log -- <path>` on any of them and you will see nothing but sync commits.

Two places where this bites:

- **The RFD issue template.** Its status values are governed by the [RFD lifecycle](GOVERNANCE.md#rfd-lifecycle) here, but the template itself can only be changed upstream. Reconciling the two means a policy change here and a template change there.
- **`LICENSE`.** While it is still synced, changing it here alone does not stick, and changing it upstream relicenses every repository in the sync group at once. Once [nebari-dev/.github#50](https://github.com/nebari-dev/.github/pull/50) merges, this file is repository-local and the entry above goes away.

`CODE_OF_CONDUCT.md` is the reverse case, and worth knowing about.
It is **not** synced into this repository, so the copy here is editable and is the canonical one.
But `nebari-dev/.github` holds its own copy that is pushed to the other repositories, so a change made here does not reach them.
Keeping the two aligned is a manual step.

### Issues here are for discussion, not for bugs

Blank issues are disabled, and `.github/ISSUE_TEMPLATE/config.yml` routes people to the right place.
The trackers are separate:

- Nebari bugs and feature requests: `nebari-dev/nebari`
- Documentation issues: `nebari-dev/nebari-docs`
- Governance discussion and RFDs: this repository

An RFD is a GitHub issue, not a file committed here.
Its status vocabulary and the label that goes with each status are defined in `GOVERNANCE.md`, and that table is the authority when anything disagrees.
Dates in an RFD's status table are day-first, as `dd-MM-YYYY`.

## Writing conventions

Match the file you are editing. Across the repository:

- **One sentence per line.** Prose is not wrapped at a fixed column; each sentence gets its own line so diffs stay readable. Do not reflow paragraphs you are not otherwise changing, because it turns a one-line edit into a whole-paragraph diff.
- **Links are inline**, except in `CONTRIBUTING.md`, which collects reference-style definitions at the bottom under a `<!-- Links -->` comment.
- **Policy prose is plain and direct.** These documents state what is required, what is recommended, and what does not exist yet. Keep those three distinct, and prefer admitting a gap to papering over it.
- **The accessibility rules are a review gate**, not advice. The pull request template makes contributors confirm them, so write to them the first time:
  - plain language
  - exactly one level-one heading per file
  - link text that describes its destination, so no "click here" and no bare URLs
  - alt text on every image, and no information carried only by an image
  - no more than three emojis in a row
  - no flashing GIFs or videos
  - content that still makes sense read as plain text

## Making changes

Work on a branch and open a pull request.
`main` is protected: it takes a pull request with one approving review, and force pushes and branch deletion are blocked.
The core team can bypass the review requirement, so being able to merge your own change does not mean you should.

The pull request body comes from `.github/PULL_REQUEST_TEMPLATE.md`.
Fill in the reference issue, which for a policy change is the authorizing RFD, tick the change type, and complete the access-centered content checklist.
For a content-only change the testing boxes do not apply, so say that explicitly rather than leaving them ambiguous.

### Checking your work

The repository ships no link checker. This resolves every relative Markdown link against the file that contains it:

```bash
grep -rnoE '\]\([^)#][^)]*\.md[^)]*\)' --include='*.md' . \
  | sed -E 's|^\./||; s|:[0-9]+:\]\(|:|; s|\)$||' \
  | while IFS=: read -r file link; do
      target="${link%%#*}"
      case "$target" in http*) continue;; esac
      [ -e "$(dirname "$file")/$target" ] || echo "BROKEN: $file -> $link"
    done
```

It should report nothing.
Breaks in files you did not touch are worth fixing, since there is no CI to catch them.

That command does not check anchors, only paths.
If you renamed a heading, grep for the old anchor text yourself.
