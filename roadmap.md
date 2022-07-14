# Roadmap - 2022

Our roadmap typically looks out 12-18 months, and we establish topics we want to work on.

We develop our roadmap based on the findings we made over the course of the last year, and what we heard from the users and collaborators in issues, in face-to-face discussions, and other media.

When we execute on our roadmap, we keep learning and our assessment of some topics listed changes. As a result, we may add or drop topics as we go. After around 12 months we come together to develop the next roadmap.

We describe some initiatives as "investigations" or "explorations" which means our goal in the next few months is to better understand the problem and potential solutions before scheduling actual feature work. Once an investigation is done, we will update our plans, either deferring the initiative or committing to it.

## Table of contents

- [Roadmap - 2022](#roadmap---2022)
  - [Legend of annotations](#legend-of-annotations)
  - [Values](#values)
  - [Themes for 2022](#themes-for-2022)
    - [Engineering](#engineering)
    - [User experience](#user-experience)
    - [Performance and stability](#performance-and-stability)
    - [Reliability and security](#reliability-and-security)
    - [Community support and governance](#community-support-and-governance)
    - [Design](#design)
    - [Explorations](#explorations)

## Legend of annotations

| Mark | Description                                  |
| ---- | -------------------------------------------- |
| 🗃    | work not started -usually within the backlog |
| 📬   | scoped and due to work on                    |
| 🏗    | ongoing work                                 |
| ✅   | work completed                               |
| ⛔️  | blocked item                                 |
| 🔮   | stretch goal                                 |

We use the same legends across our project boards to keep planning and messages consistent

## Values

Before we go into the details, let's start with our values that guide the development of Nebari.

- We strive for a “just works” experience for end-users - this places user experience at the core of everything we build.
- Performance trumps functionality.
- The documentation must be as transparent & accessible as possible.
- We build on open source software. In addition, any changes we make to open source software will be made in public and/or contributed upstream, so customers continue to have access to them regardless of where their infrastructure is.
- We must not directly depend on proprietary cloud vendor specific products or APIs. Instead, we use cloud-managed open source software, or hide the dependency behind a layer of abstraction. This ensures that customers can port their infrastructure to any cloud provider of their choice, or run it on their own hardware with purely open source software.

(Definitions of `MUST`, `MUST NOT`, `SHOULD`, `MAY`, etc are defined in [RFC 2119](https://tools.ietf.org/html/rfc2119))

## Themes for 2022

For 2022, we'll particularly focus on the following themes.

### Engineering

- 🏗️ - Improve team’s overall software development practices
- 📬 - Improve our GitHub practices and efficiency
  - 📬 - Unify issues, PRs and RFCs into issue boards
  - 🗃 - Reevaluate the use of bots, pre-commits, and other automations → they should help make the development process more efficient (i.e. instead of blocking contributions or adding unnecessary noise)
  - 🗃 - Adopt the use of `gitlab-flow` moving forward
  - 🗃 - Create triaging guidelines
- 🗃 - Document and streamline our release process
  - 🗃 - Automate the creation of release checklists and document all the to-release steps
  - 🗃 - Migrate from `SemVer` to `CalVer` (Nebari migration)
- 🗃 - adopt overall development and structure standards
  - 🗃 - All repos must have an [architecture.md](http://architecture.md) or source code organisation guide
  - 🗃 - Adopt and document coding guidelines
  - 🏗️ - Standardise the use of labels, milestones, and templates

### User experience

- 🗃 - Improve our overall users’ experience
  - 🗃 - Standardise feedback and user research processes
  - 🗃 - Adopt a user design first approach
- 🏗 - Major update to the documentation
  - ✅ - Audit current documentation and identify gaps and outdated content
  - ✅ - Adopt the Diataxis framework
  - ✅ - Create personas for Nebari
  - 🏗 - Create Tutorials
  - 🏗 - Create References
  - 🏗 - Create Conceptual guides
  - 🏗 - Create how-tos
  - 🏗 - Create supporting material such as schematics and other diagrams

### Performance and stability

- 🗃 - Ensure all the current integrations are workings, they have corresponding documentation and are tested accordingly
- 🗃 - More robust testing
  - 🗃 - Run scheduled tests on top of those from PRs and releases
  - 🗃 - Add tests to the docker images

### Reliability and security

- 🗃 - Secure our supply chain
  - 🗃 - Ensure we are not using long-lived credentials
  - 🗃 - Introduce DevSecOps practices
- 🗃 - Refactor our CI/CD pipelines
  - 🗃 - Identify bottlenecks and opportunities for improvements
  - 🗃 - Critical deployments and other releases require `code owner` approval
  - 🗃 - Reduce re-creation of artefacts and unnecessary runs
- 🗃 - Decentralise development and deployment
  - 🗃 - One repository == one single product/scope (i.e. docker-images) should be outside of the main repository
  - 🗃 - All deployments should have a `staging` → `production` pattern

### Community support and governance

- 🏗 - Improve our maintenance practices and OSS citizenship

  - 🏗 - Create teams with defined scopes and responsibilities (GitHub)
  - 📬 - Have a public roadmap in GitHub
  - 📬 - Adopt a promise framework such as [https://about.gitlab.com/company/stewardship/](https://about.gitlab.com/company/stewardship/) (complementary to the governance work)
  - 🗃 - Adopt public and transparent guidelines on how we interact with the broader OSS ecosystem
  - 🗃 - Either host or join community calls

- 🏗️ - Formalise our governance
  - 🗃 - Adopt a decision making process: RFD, Nebari enhancement proposals
  - 🗃 - Define roles and expectations for: maintainers, contributors, emeritus maintainers, etc. and how to attain membership to said groups
    - 🗃 - Adopt and onboarding and offboarding checklist

### Design

- 📬 - Create and launch Nebari OSS website
- 📬 - Unify documentation theme and main site
- 🗃 - Improve the accessibility of products we own or release
- 📬 - Rebranding - Nebari
  - 🗃 - Develop brand guidelines, assets (including logos, illustrations…)
  - 🗃 - Refresh any outdated assets or schematics
  - 🗃 - Launch and announcement

### Explorations

- 🏗 - Open source MLOps story
  - 🏗 - Workflow automation - orchestration (Argo) maybe others
  - 🔮 - Integrations with CML, DVC
- 🔮 - Jupyter experience improvements
  - 🗃 - Evaluate which extensions we should add by default
  - 🔮 - Accessible theming
- 🔮 - Improve monitoring and logging
  - 🔮 - Grafana dashboards see ‣
- 🔮 - Security explorations
  - 🔮 - Adopt [Kubescape](https://github.com/armosec/kubescape)
- 🔮 - Evaluate the use of (dagger)[https://dagger.io/blog/public-launch-announcement](https://dagger.io/blog/public-launch-announcement)
