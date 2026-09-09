# AGENTS.md

Guidance for coding agents working in this repository.

## What this repository is

`nebari-dev/governance` holds the Nebari project's governance artifacts: the Code of Conduct, the public roadmap, and the documentation analytics policy.

It is documentation only.
There is no application code, no dependency manifest, no build, no test suite, no linter, and no CI workflow.
Apart from the GitHub issue forms, the license, and dotfiles, every file is Markdown.

Two things follow from that:

- There are no build, lint, or test commands to run, and adding tooling for them is not a side effect of a content change.
- Verification means reading the diff for factual accuracy and confirming that relative links still resolve. See [checking your work](#checking-your-work).

## Structure, and why it is shaped this way

### The Code of Conduct is one document split across five files

`CODE_OF_CONDUCT.md` at the root is the entry point.
It states the commitment, names the reporting route, and links to the four parts under `code-of-conduct/`.

| File | Holds |
| ---- | ----- |
| `code-of-conduct/coc_details.md` | Expected and unacceptable behavior |
| `code-of-conduct/coc_diversity_statement.md` | Diversity statement |
| `code-of-conduct/coc_reporting.md` | How to report an incident |
| `code-of-conduct/coc_enforcement.md` | Committee membership and the enforcement manual |

Substantive changes belong in the relevant part file rather than in the root summary.
The root file and the parts cross-link with relative paths, and several of those links carry anchors, most often `coc_enforcement.md#the-code-of-conduct-committee`.
Renaming a heading in a part file silently breaks the anchors pointing at it from the other files, so grep for the old heading text before renaming one.

The committee names and email addresses in `coc_enforcement.md` are live reporting contacts, and `CODE_OF_CONDUCT.md`, `coc_details.md`, and `coc_reporting.md` all link to that section.
Change them only on explicit instruction, and update every reference in the same change.

### Roadmaps are append-only history

`roadmap.md` is the stable entry point.
It carries the project values, the annotation legend, and a Documents list linking to one file per year under `roadmaps/`.

The per-year files are a record, not a live board.
`roadmaps/roadmap_2023.md` says it continues the 2022 themes, links back to them, and carries forward the items that were still unfinished.
So:

- Update the current year's file. Leave earlier years as they were written, even where an item has since moved on.
- Starting a new year means adding `roadmaps/roadmap_<year>.md` plus a link to it from the Documents list in `roadmap.md`.

Status marks are shared vocabulary, not decoration.
The legend in `roadmap.md` defines 🗃 (not started), 📬 (scoped), 🏗 (ongoing), ✅ (complete), ⛔️ (blocked), and 🔮 (stretch goal), and the same marks are used on the project boards.
Reuse them exactly, and do not introduce new ones.

### Some files here are copies, and local edits to them get overwritten

`CONTRIBUTING.md`, `.github/PULL_REQUEST_TEMPLATE.md`, and everything under `.github/ISSUE_TEMPLATE/` are pushed into this repository by a sync bot from `nebari-dev/.github`.
Run `git log -- <path>` on any of them and you will see nothing but sync commits.

Editing those files here is lost on the next sync.
Send the change to `nebari-dev/.github` instead.

### Governance is documented in two places

Some processes live on the documentation site rather than in this repository, and the README links to them: [team structure and roles](https://www.nebari.dev/community/team-structure) and [decision making processes](https://www.nebari.dev/community/decision-making).

Before adding a process document here, check whether the site already covers it, and prefer a link over a restatement that can drift.

### Issues here are for discussion, not for bugs

Blank issues are disabled, and `.github/ISSUE_TEMPLATE/config.yml` routes people to the right place.
The trackers are separate:

- Nebari bugs and feature requests: `nebari-dev/nebari`
- Documentation issues: `nebari-dev/nebari-docs`
- Governance discussion: this repository, labelled `needs: discussion 💬`

Decisions are made through Request for Discussion issues, opened from `.github/ISSUE_TEMPLATE/RFD.md`.
An RFD is a GitHub issue with a status table at the top, not a file committed here.
That table has its own status vocabulary, separate from the roadmap legend: Draft 🚧, Open for comments 💬, Accepted ✅, Implemented 🚀, Obsolete 🗃, Rejected ⛔️.
Dates in it use `dd-MM-YYYY`.

## Writing conventions

Match the file you are editing. Across the repository:

- **One sentence per line.** Prose is not wrapped at a fixed column; each sentence gets its own line so diffs stay readable. Do not reflow paragraphs you are not otherwise changing, because it turns a one-line edit into a whole-paragraph diff.
- **Links are inline**, except in `CONTRIBUTING.md`, which collects reference-style definitions at the bottom under a `<!-- Links -->` comment.
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
Fill in the reference issue, tick the change type, and complete the access-centered content checklist.
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

Breaks reported in files you did not touch are pre-existing; fix them in their own change rather than folding them into an unrelated one.

That command does not check anchors, only paths.
If you renamed a heading, grep for the old anchor text yourself.
