# Roadmap - 2023

## Table of contents

- [Roadmap - 2023](#roadmap---2023)
  - [Table of contents](#table-of-contents)
  - [Themes for 2023](#themes-for-2022)
    - [Engineering](#engineering)
    - [User experience](#user-experience)
    - [Performance and stability](#performance-and-stability)
    - [Reliability and security](#reliability-and-security)
    - [Community support and governance](#community-support-and-governance)
    - [Design](#design)
    - [Explorations](#explorations)

## Themes for 2023

For 2023, we'll continue to focus on the [same themes as last year](./roadmap_2022.md#themes-for-2022).
We carried the unfinished tasks and added some new ones.

### Engineering

- 🗃 - Adopt overall development and structure standards
  - 🗃 - All repos must have an [architecture.md](http://architecture.md) or source code organisation guide
  - 🏗 - Adopt and document coding guidelines
- 📬 - Allow custom docker images
    - 🗃 - Create templates (e.g. cookie-cutter) with minimum requirements
    - 🗃 - Create tutorials for how to use the templates and add customization
    - 🗃 - Add tests for validating custom images
    - 🗃 - Update charts/config to allow pulls from other container registries
- ✅ - Integrate new conda-store UI
- 🏗 - Add an extension mechanism to Nebari
  - 🏗 - Design and implement extension architecture
  - 📬 - Move relevant integrations to the extension framework
  - 🗃 - Write tutorials for creating new extensions
- 🗃 - Replace CDS Dashboards, with new tooling

### User experience

- 🏗️ - Improve our overall users’ experience
  - 🗃 - Standardize feedback and user research processes
  - 🗃 - Improve the Nebari CLI for better experience and accessibility
- 🏗 - Updates to the documentation
  - 🗃 - Evaluate [terraform-docs](https://terraform-docs.io/) to document Terraform modules
  - 🏗️ - Add API documentation
  - 🗃 - Create new Tutorials for integrations
  - ✅ - Migrate all documentation from `qhub.dev`
  - ✅ - Sunset `qhub.dev` and archive corresponding documents

### Performance and stability

- 🏗️ - Ensure all the current integrations are workings, they have corresponding documentation and are tested accordingly
- 🗃 - More robust testing
  - 🗃 - Run scheduled tests on top of those from PRs and releases
  - 🏗️ - Add tests to the docker images
- 📬 - Upgrade to JupyterHub 4.0
- 📬 - Upgrade to latest Kubernetes version

### Reliability and security

- 🗃 - Secure our supply chain
  - 🗃 - Ensure we are not using long-lived credentials
  - 🗃 - Introduce DevSecOps practices
- 🗃 - Refactor our CI/CD pipelines
  - 🗃 - Identify bottlenecks and opportunities for improvements
  - 🗃 - Critical deployments and other releases require `code owner` approval
  - 🏗️ - Reduce re-creation of artifacts and unnecessary runs (for example, add `[ci skip]` for Kubernetes tests)
- 🗃 - Decentralize development and deployment
  - 🗃 - All deployments should have a `staging` → `production` pattern
- 🗃 - Adopt a policy for secrets management
  - 🏗️ - Investigate, scope, and implement the use of [SOPS](https://github.com/mozilla/sops)
  - 🗃 - Document the secrets management process for maintainers

### Community support and governance

- 🏗 - Improve our maintenance practices and OSS citizenship
  - 📬 - Adopt a promise framework such as [https://about.gitlab.com/company/stewardship/](https://about.gitlab.com/company/stewardship/) (complementary to the governance work)
  - 🗃 - Adopt public and transparent guidelines on how we interact with the broader OSS ecosystem
  - 📬 - Measure, track, and grow the Nebari community using the Orbit model

- 🏗️ - Formalize our governance
  - 🏗️ - Adopt a decision-making process: RFD, Nebari enhancement proposals
  - 🏗️ - Define roles and expectations for: maintainers, contributors, emeritus maintainers, etc. and how to attain membership to said groups
    - 🗃 - Adopt and onboarding and off boarding checklist for new and retiring maintainers

### Design

- 🗃 - Improve the accessibility of products we own or release
- ✅ - Improve the website and documentation design
  - ✅ - Complete the website design
  - ✅ - Make the website theme consistent

### Explorations

- ✅ - Open source MLOps story
  - ✅ - Workflow automation - orchestration (Argo) maybe others
    - ✅ - Argo has been added as a backend integration in Nebari
    - ✅ - Add Jupyter-scheduler to complement Argo
    - 📬 - Remove kbatch integration
  - 🔮 - Integrations with CML, DVC
- 🔮 - Jupyter experience improvements
  - ✅ - Evaluate which extensions we should add by default
  - 🔮 - Accessible theming
- 🔮 - Improve monitoring and logging
  - 🔮 - Grafana dashboards improvements
- 🔮 - Security explorations
  - 🔮 - Adopt [Kubescape](https://github.com/armosec/kubescape)
- 🔮 - Evaluate the use of (dagger)[https://dagger.io/blog/public-launch-announcement](https://dagger.io/blog/public-launch-announcement)
- 🔮 - Expand test suite
  - 📬 - Verify stability of (Jupyter) extensions
  - 🔮 - Explore testing Nebari integrations
