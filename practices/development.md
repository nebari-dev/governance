# Development and backlog workflow

This section describes how our development team carries out its planning and day-to-day work.

- [Development and backlog workflow](#development-and-backlog-workflow)
  - [:running_woman: Team Sprints](#running_woman-team-sprints)
    - [Sprint cadence](#sprint-cadence)
    - [Sprint planning meeting](#sprint-planning-meeting)
    - [The `🏃🏻 - Sprint board`](#the----sprint-board)
  - [:package: Deliverables and work issues](#package-deliverables-and-work-issues)
    - [How are deliverables structured?](#how-are-deliverables-structured)
  - [:card_file_box: The Team Backlog](#card_file_box-the-team-backlog)
    - [Assigning to an issue](#assigning-to-an-issue)
    - [Backlog item limits](#backlog-item-limits)
    - [Adding backlog items](#adding-backlog-items)
    - [How to prioritize backlog items](#how-to-prioritize-backlog-items)
    - [Working on backlog items](#working-on-backlog-items)
    - [Tracking upstream issues](#tracking-upstream-issues)
  - [:eyes: Merging and Reviewing policy](#eyes-merging-and-reviewing-policy)
    - [Policy for changes to running infrastructure](#policy-for-changes-to-running-infrastructure)
    - [Policy for team compass changes](#policy-for-team-compass-changes)
  - [:pencil2: How to keep track of projects](#pencil2-how-to-keep-track-of-projects)
    - [Meta issues](#meta-issues)
    - [Project Backlogs](#project-backlogs)
  - [:mega: How we make decisions](#mega-how-we-make-decisions)
    - [Resources to learn about consent-based decision making](#resources-to-learn-about-consent-based-decision-making)

## :running_woman: Team Sprints

The Nebari team uses Sprints to coordinate with one another in focused cycles of work.
To begin each sprint, we collectively choose items to work on in the next sprint.
Each item should have a person assigned to it, who will be responsible for ensuring that the work gets done.
However, our work within a sprint is a **team commitment**, and we are all responsible for helping one another accomplish our tasks.

### Sprint cadence

Our team works in **two-week sprints**.
Here is a brief overview of each sprint.

1. **Tuesday (beginning of sprint)**
   - All the sprints begins with a sprint planning meeting.
   - In this meeting we discuss major accomplishments in the previous sprint. We then prioritize and assign the items that each team member will work on for the next sprint, and review items that require discussion and planning.

2. **During the sprint**
   - Team members work on the items assigned to them at the sprint planning meeting.
   - We use the [🏃🏻 - Sprint board][sprint-board] to coordinate our activities during the sprint.
   - We provide updates about what we've been up to, what we're doing next, and where we need help via regular **team progress meetings**.

3. **Monday of week 2 (end of sprint)**
   - By the end of the day, team members should have completed all of their items for that sprint.

### Sprint planning meeting

- The team conducts a Sprint Planning meeting for 60 minutes at the beginning of each sprint.
- The goal of this meeting is to review our major work items, synchronize with one another, and prioritize work across team members.
- Our **Project Manager** leads these meetings.

<!-- TODO: add template -->
:link: See [the Sprint Planning issue template](***) for the agenda / structure of these meetings.

### The `🏃🏻 - Sprint board`

The [`🏃🏻 - Sprint board`][sprint-board] is a place to keep track of the tasks and other deliverables our team intends to work on for the sprint.
The team's goal is to complete all items on the Sprint Board by the end of the Sprint.
This is a team commitment - while one person may be assigned to a deliverable, we all commit to working together to get the work done.

**The Sprint Board should...**

- Have enough items to keep the team occupied for the sprint
- Not have so many items that a team member gets overwhelmed
- Under-estimate our team's total capacity, to provide room for unexpected work (e.g., support work) and time off
- Have a team member assigned to each item on the board

The Sprint Board is broken down into these columns:

- `Todo - ready to work 📬` items that are ready to be worked on.
- `In progress 🏗` an item that a team member is currently working towards.
- `PR opened 📥` items that have a PR opened and are waiting for review.
- `In review/QA 👀` items that are being reviewed by a team member.
- `Done 💪🏾` items that have been completed. These should be celebrated archived in the next Sprint Planning meeting.

> **Note**
> 👉🏽 [Here is a status view of the items in this sprint](https://github.com/orgs/nebari-dev/projects/4/views/4)
> 👉🏽 [If you prefer a Kanban view you can check it here](https://github.com/orgs/nebari-dev/projects/4/views/7)

In addition, we have a few other pieces of metadata to signal different kind of actions that would be needed

## :package: Deliverables and work issues

Deliverables represent incremental amounts of value we can deliver to a particular stakeholder.
They are **encoded as GitHub Issues** and updated over time as we learn more about the particular deliverable.
Most issues in our repositories are deliverables, in varying states of readiness.

> **Note**
> We use the word "deliverable" loosely here - some issues may be more like tasks rather than an end-product.
> The important thing is that they have high-quality information and structure, highlight the value of such item, and are actionable.

### How are deliverables structured?

There are a few special sections of a deliverable issue.
Not all of them are strictly required, but are particularly useful for more complex or long-lasting deliverables.

See [this Github Issue template](******) for an example of a deliverable's structure.
Below are some major sections that are common:

1. **Top Comment**

   - The top comment of a deliverable has meta information associated with that deliverable.
   - This includes background information, user stories, task lists, etc.
   - **The top comment should be frequently updated** by anybody on the team with relevant information to add.
   - Do not hesitate to update somebody's top comment with new information, even if you didn't open the issue (though you're encouraged to leave a comment noting what has changed!).

1. **Benefit**

   - What is the benefit for completing this deliverable?
   - This should be in the form of [user stories](https://www.atlassian.com/agile/project-management/user-stories) that explicitly define the stakeholders that care about a deliverable, and why.

1. **Tasks to complete**

   - Use task lists encode discrete steps to take in order to complete a deliverable.
   - All deliverables should have either a set of concrete steps to take to meet the deliverable, or at least one task with the **acceptance criteria** for when the deliverable will be complete.
   - Task lists should be in the top comment of the deliverable, and are encoded as markdown tasks lists (e.g. with `- [ ]`).
   - Task lists should be updated over time as we learn the steps needed to close the deliverable.
   - For more complex deliverables, these tasks may be what goes onto the Sprint Board, rather than the deliverable itself.

## :card_file_box: The Team Backlog

:link: - [Click here to go to the Team Backlog][backlog-board].

The Team Backlog is a GitHub Projects Board with a list of Deliverables and tasks across all of our active projects and repositories.
This represents the work that the team is planning to do in the near future.
These items adhere to the following principles:

- The order of items should be roughly according to priority, with higher priority items at the top of lists.
- Items on the board should have a **status** that signals whether they are ready to work or need more refinement before working.
- If an item has multiple components or would otherwise take longer than a sprint to complete, create new issues as sub-tasks, and add *them* to the Sprint Board. Meta issues are useful to track these types of items.

### Assigning to an issue

Only assign a backlog issue to somebody if it is **actively being worked on**.
We assume that once somebody is assigned to an issue, it is part of an active sprint.
Note that **all** issues on our Sprint Backlog should have somebody assigned to them.

> **Warning**
> **Our definition of "Work in Progress"**
> Because issues that are actively being worked on must have somebody assigned to them, we use "the issues that have somebody assigned to them" as our definition of Work in Progress.

### Backlog item limits

Our goal is to have backlog items that roughly cover the next 3 sprint cycles.
We **should not have more backlog items than this amount**.

You can estimate the number of items on the board at any one time by assuming that **each team member (at 100% FTE) can accomplish about 2 items per sprint**.
You can then calculate the rough number of items on this board with the equation:

```mathjax
$$ n_team_members * 2 (items per sprint) * 3 (sprints on the board) $$
```

So if we have `5.5` team members available (if one of them is at 50% FTE), then the team backlog should have around `$ 5.5 * 2 * 3 = 33 deliverables $` on it.

### Adding backlog items

We should add items to our team backlog when we have capacity to do the work in the next 3 sprints, and when those items are ready to be prioritized over all the other work that we *could* do (e.g., all issues in our repositories and encoded in project backlogs).

> **Note**
> It can be difficult to keep track of issues across all of our repositories, so our [Sprint board][sprint-board] and [Backlog board][backlog-board] are the single source of truth for all the work.
> There are larger projects such as [documentation][documentation-board] and [community growth][community-board] that have their own boards. But the issues must also be added to the team backlog and sprint boards.

To add an item to the backlog, take the following steps:

1. Look at the team backlog to make sure that it has capacity to absorb a new item.
1. If it does not have capacity
   1. Consider adding it to a Project Backlog(i.e. documentation or community growth) or leave it in the issues of a repository.
    We can always get to it later.
   2. Choose whether you wish to **remove** an item from the backlog in order to make space.
    Use your best judgment about whether this is the right thing to do, depending on the priority of the backlog items that are already on there.
1. Place the new backlog item in the appropriate location, according to its perceived importance and urgency. To add the issue to the [Backlog board][backlog-board] click on the `Projects` tab in the GitHub UI and select the [🗃 - Nebari backlog board][backlog-board].

![Adding items to Nebari backlog organization board](../assets/Nebari_add_item_project.png)

### How to prioritize backlog items

It can be difficult to prioritize backlog items, and is ultimately a subjective decision.
These criteria can be used to help guide your actions:

1. **Impact**: How impactful will it be to resolve this item?
  Will it affect many users or be particularly useful?
1. **Urgency**: How important is it that we resolve this item quickly?
  If it is lower impact, but urgent to accomplish, we may nonetheless wish to prioritize it.
1. **Effort**: How many moving pieces does this item have and how much deep thinking will it take to resolve?

All else being equal, we should prioritize backlog items that are easier or faster to accomplish since this will be more bang for our buck.
This is very subjective, so is probably best-estimated when there's a candidate person to work on an item.

### Working on backlog items

Backlog items are ready to work when they have enough context and tasks so that a team member can begin making progress towards closing them.
This doesn't mean that we know **all** the tasks needed to complete the item, but that there's enough information to begin work. [^invest]

[^invest]: A good resource for considering what kinds of information makes a deliverable "ready" is [the INVEST methodology](https://agileforall.com/new-to-agile-invest-in-good-user-stories).

The team picks up work associated with a backlog item via our Sprint Planning meeting.
In this case, there are two options:

1. **Add the item to the Sprint Board**. If an item is scoped tightly enough that it can be completed within one sprint, then add it to the [Sprint Board][sprint-board] and complete it in a sprint.
2. **Generate issues from tasks and add them to the Sprint Board**. For items that are more complex and require tasks that would take more than one sprint, use the **Task List** in the issue to generate new issues for use on the Sprint Board.

> **Note**
> You can [use GitHub's task issue tracking features](https://docs.github.com/en/issues/tracking-your-work-with-issues/about-task-lists) to keep track of tasks associated with an issue.

As work is done towards a backlog item, **update the top comment of the issue** with new information and tasks.

### Tracking upstream issues

In some cases we want to do work in an upstream repository or project.
To do this, add upstream issues to our Team Backlog as we would add any other issue.

## :eyes: Merging and Reviewing policy

The sections below describe major policies around merging and reviewing depending on the kind of change being made.
There are some extra policies for changes that **affect actively-running infrastructure**.
See the section below for details.

> **Note**
> Not all of them are followed strictly, though some are more important than others, and are marked with **REQUIRED :pushpin:**.

- **Always make a Pull Request**. (REQUIRED :pushpin:).
  All changes to Nebari repositories should be made via a Pull Request.
  This should be enforced by setting the `main` branch of each repository to be "protected".
- **PRs should reference (and close) issues**.
  A pull request should almost always be related to an issue.
  Ideally, the issue should be tightly-scoped enough that the PR will close it when merged.
  If you have an idea that *doesn't* yet have an issue, open an issue first and then make the PR to close it.
  This ensures that the team has context around Pull Requests, and a chance to discuss before we implement.
- **Use GitHub's `Request Review` feature**.
  Add specific team members so that it is clear who is needed to review the PR.
- **Be explicit about what feedback you want**.
  When you open a PR, include some language about specific things you'd like feedback with, if applicable.
  This helps others focus their attention.
- **Use the review column on sprint boards**.
  When a PR needs review, move any relevant issues to the `Review` column of the active [Sprint Board][sprint-board] so others notice it.
- **Merge after one approval**.
  If there is at least one approval on a PR, then anybody, including the PR author, may merge the PR.
  PR authors should not hesitate to merge their own PR after an approval if they think it is ready to go!
- **Merging without review is discouraged, but not forbidden**.
  For changes that are minor, very straightforward, and do not affect actively-running infrastructure, it is acceptable to self-merge a PR without getting an approval.
  If you don't believe that your PR requires an approval before merging, make it clear in your PR or in a comment that you plan to merge it in 24 hours.
- **Leave PRs open for at least 24 working hours**.
  This helps ensure that others on the team have a chance to look at the PR and give their thoughts (by working hours we mean hours during a weekday).

### Policy for changes to running infrastructure

Changing active infrastructure is a bit different from developing technology that is not immediately in production.
As such, we follow some more specific guidelines for these kinds of changes.

:link: See [Changing active infrastructure](active-infra.md) for more details.

### Policy for team compass changes

If a change affects the Nebari team policies, or makes significant changes to our documentation or public-facing material, then you should also follow these extra policies:

- **Ensure that the team has consented**.
  For any major change, you should make sure that you have followed best-practices in consent-based decision making.

## :pencil2: How to keep track of projects

Longer-term projects are generally more complex and may be made up of many actions and deliverables to accomplish.
There is no official way to track long-term projects within Nebari, but there are a few patterns that may be useful to do so, described in this section.

<!--TODO: We should define a more reliable process for tracking long-term projects -->

### Meta issues

The simplest way to track longer-term efforts is with a **Meta Issue**.
This is a GitHub Issue whose job is to keep track of many actions and deliverables over time that are needed to close the issue.
They are generally encoded as **Task Lists** in the issue's top comment.
Each item in the list tends to be a deliverable, and can be converted into its own GitHub Issue (e.g., to put on the [Sprint Board][sprint-board]) as-needed.

Each Meta issue is the `Source of Truth` for all work associated with it (instead of, for example, an issue created as a sub-task for that item).

### Project Backlogs

For more complex efforts, it can be useful to create a Project Backlog.
These are GitHub Projects boards that contain all the deliverables that will complete a given project.
These are often organized into a few columns, representing the **status** of each deliverable.
Here is a common column structure:

- `Needs Discussion/Refinement 🪨`: Deliverables that are high-priority but un-refined. Our goal should be having discussion and doing research in order to get these deliverables ready for work.
- `Todo -ready to work 📬`: Deliverables that are well-scoped and have a clear path forward, and are thus ready to implement. As deliverables in `In progress` are completed, we should replace them with deliverables from this column. Generally speaking, deliverables near the top have higher priority than those at the bottom.
- `In progress 🏗`: Deliverables that we are currently working towards. This means that they should be added to the [Sprint Board]([sprint-board]) to track its completion.
- `In review 👀`:
- `PR opened 📥`:
- `Blocked ⛔️`: Deliverables that require another action or delivearable from the Nebari team to complete before they can move forward.
- `Waiting ⏳`: Deliverables that require another action from a **non-Nebari team member** before they can move forward.
- `Done 💪🏾`: Deliverables that have been completed. We should close these issues and celebrate the improvements that we have made!

## :mega: How we make decisions

The Nebari Team follows [consent based decision-making](https://thedecider.app/consent-decision-making) in making all of its team decisions.
This roughly means the following for **any decision that impacts all team members**:

- The proposed decision and relevant context must be available to all team members.
  This is generally done via opening GitHub issues.
- Ensure that team members have time to understand the proposal, and ask questions about it to understand its ramifications.
- Ensure that team members have time to object and make suggested changes.
- Ensure that the result of the decision is recorded somewhere that is available to all team members.

Generally speaking, this process is carried out via GitHub Issues and Pull Requests.
See [Merging and reviewing policies](#eyes-merging-and-reviewing-policy) for how this works in practice.

### Resources to learn about consent-based decision making

Here are some helpful resources for more information about consent-based decision-making.

- A short primer: <https://thedecider.app/consent-decision-making>
- A more in-depth discussion: <https://sociocracyforall.org/consent-decision-making/>
- A well-known technical proposal on "Consent via humming": <https://tools.ietf.org/html/rfc7282>

<!-- links -->
[sprint-board]: https://github.com/orgs/nebari-dev/projects/4
[backlog-board]: https://github.com/orgs/nebari-dev/projects/2
[documentation-board]: https://github.com/orgs/nebari-dev/projects/3
[community-board]: https://github.com/orgs/nebari-dev/projects/1
