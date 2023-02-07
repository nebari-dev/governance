# Roadmap - 2022

## Table of contents

- [Roadmap - 2022](#roadmap---2022)
  - [Table of contents](#table-of-contents)
  - [Themes for 2022](#themes-for-2022)
    - [Engineering](#engineering)
    - [User experience](#user-experience)
    - [Performance and stability](#performance-and-stability)
    - [Reliability and security](#reliability-and-security)
    - [Community support and governance](#community-support-and-governance)
    - [Design](#design)
    - [Explorations](#explorations)

## Themes for 2022

For 2022, we'll particularly focus on the following themes.

### Engineering

- ✅ - Improve team’s overall software development practices
- ✅ - Improve our GitHub practices and efficiency
  - ✅ - Unify issues, PRs and RFCs into issue boards
  - ✅ - Reevaluate the use of bots, pre-commits, and other automations → they should help make the development process more efficient (i.e. instead of blocking contributions or adding unnecessary noise)
  - ✅ - Adopt the use of `gitlab-flow` moving forward
  - ✅ - Create triaging guidelines
- ✅ - Document and streamline our release process
  - ✅ - Automate the creation of release checklists and document all the to-release steps
  - ✅ - Migrate from `SemVer` to `CalVer` (Done with the Nebari rename in October 2022)
- 🗃 - adopt overall development and structure standards
  - 🗃 - All repos must have an [architecture.md](http://architecture.md) or source code organisation guide
  - 🏗 - Adopt and document coding guidelines
  - ✅ - Standardize the use of labels, milestones, and templates

### User experience

- 🏗️ - Improve our overall users’ experience
  - 🗃 - Standardize feedback and user research processes
  - ✅ - Adopt a user design first approach
  - ✅ - Refactor the Nebari CLI
  - ✅ - Simplify the first deployment experience for new users
- 🏗 - Major updates to the documentation
  - ✅ - Audit current documentation and identify gaps and outdated content
  - ✅ - Adopt the Diataxis framework
  - ✅ - Create personas for Nebari
  - 🏗️ - Add API documentation
  - ✅ - Create Tutorials
  - ✅ - Create References
  - ✅ - Create Conceptual guides
  - ✅ - Create how-tos
  - ✅ - Create supporting material such as schematics and other diagrams

> **Note**
> While many items in the documentation section are marked as **complete** there is still a lot of work to be done to improve the overall documentation experience. We will continue to work on this in 2022-2023.

### Performance and stability

- 🏗️ - Ensure all the current integrations are workings, they have corresponding documentation and are tested accordingly
- 🗃 - More robust testing
  - 🗃 - Run scheduled tests on top of those from PRs and releases
  - 🏗️ - Add tests to the docker images

### Reliability and security

- 🗃 - Secure our supply chain
  - 🗃 - Ensure we are not using long-lived credentials
  - 🗃 - Introduce DevSecOps practices
- 🗃 - Refactor our CI/CD pipelines
  - 🗃 - Identify bottlenecks and opportunities for improvements
  - 🗃 - Critical deployments and other releases require `code owner` approval
  - 🏗️ - Reduce re-creation of artifacts and unnecessary runs
- 🗃 - Decentralize development and deployment
  - ✅  - One repository == one single product/scope (i.e. docker-images) should be outside the main repository
  - 🗃 - All deployments should have a `staging` → `production` pattern

### Community support and governance

- 🏗 - Improve our maintenance practices and OSS citizenship
  - ✅ - Create teams with defined scopes and responsibilities (GitHub)
  - ✅ - Have a public roadmap in GitHub
  - 📬 - Adopt a promise framework such as [https://about.gitlab.com/company/stewardship/](https://about.gitlab.com/company/stewardship/) (complementary to the governance work)
  - 🗃 - Adopt public and transparent guidelines on how we interact with the broader OSS ecosystem
  - ✅ - Either host or join community calls

- 🏗️ - Formalize our governance
  - 🏗️ - Adopt a decision-making process: RFD, Nebari enhancement proposals
  - 🏗️ - Define roles and expectations for: maintainers, contributors, emeritus maintainers, etc. and how to attain membership to said groups
    - 🗃 - Adopt and onboarding and off boarding checklist for new and retiring maintainers

### Design

- ✅ - Create and launch Nebari OSS website
- ✅ - Unify documentation theme and main site
- 🗃 - Improve the accessibility of products we own or release
- ✅ - Rebranding - Nebari
  - ✅ - Develop brand guidelines, assets (including logos, illustrations…)
  - ✅ - Refresh any outdated assets or schematics
  - ✅ - Launch and announcement

### Explorations

- 🏗 - Open source MLOps story
  - 🏗 - Workflow automation - orchestration (Argo) maybe others
    - ✅ - Argo has been added as a backend integration in Nebari
  - 🔮 - Integrations with CML, DVC
- 🔮 - Jupyter experience improvements
  - 🗃 - Evaluate which extensions we should add by default
  - 🔮 - Accessible theming
- 🔮 - Improve monitoring and logging
  - 🔮 - Grafana dashboards improvements
- 🔮 - Security explorations
  - 🔮 - Adopt [Kubescape](https://github.com/armosec/kubescape)
- 🔮 - Evaluate the use of (dagger)[https://dagger.io/blog/public-launch-announcement](https://dagger.io/blog/public-launch-announcement)
