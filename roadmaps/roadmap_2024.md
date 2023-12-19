# Roadmap - 2024

## Table of contents

- [Roadmap - 2024](#roadmap---2024)
  - [Table of contents](#table-of-contents)
  - [Themes for 2024](#themes-for-2024)
  - [Engineering: Core](#engineering-core)
  - [Engineering: integrations and extensions](#engineering-integrations-and-extensions)
  - [User experience](#user-experience)
  - [Performance and stability](#performance-and-stability)
  - [Reliability and security](#reliability-and-security)
  - [Community support and governance](#community-support-and-governance)
  - [Design](#design)
  - [General explorations](#general-explorations)

## Themes for 2024

For 2024, we'll continue to focus on the [similar themes as last year](./roadmap_2022.md#themes-for-2022), with stronger focus on engineering tasks.
We have added several new tasks that are planned for 2024 (marked as 🏗 or 📬) and carried over a few unfinished items from last year.

## Engineering: Core

- 📬 - Improve backup, restore, and upgrade process
- 🏗 - Enhance account-registration and sign-up mechanism
- 📬 - Scope and implement a desktop version of Nebari
- 🗃 - Allow custom docker images
    - 🗃 - Create templates (e.g. cookie-cutter) with minimum requirements
    - 🗃 - Create tutorials for how to use the templates and add customization
    - 🗃 - Add tests for validating custom images
    - 🗃 - Update charts/config to allow pulls from other container registries
- 🏗 - Improved robust role-based-access system
  - 🏗 - Fixes for conda-store permissions
  - 📬 - Better default namespaces
  - 📬 - Robust and clear permissions for users, admins, and super-admins

## Engineering: integrations and extensions

- 🏗 - Replace CDS Dashboards, with new tooling
- 🏗 - Integrate Grafana Loki for improved logging
- 📬 - Improve JupyterLab launcher (for handing multiple conda environments)
- 📬 - Move relevant integrations to the new extension framework
- 📬 - Refactor Jupyter scheduler to use k8s cron instead of Argo workflows
- 📬 - Improve conda-store integration
    - 📬 - Fix `pip install` issues in notebooks
    - 🔮 - Fix conda-store pods' storage management
- 🗃 - Create Ray extension
- 🗃 - Create PyTorch Distributes extension
- 🗃 - Integrate OpenTelemetry for improved monitoring
- 🔮 - Integrate cost monitoring and management system

## User experience

- 🏗 - Scope and document "what is Nebari"?
- 📬 - Evaluate and smoothen to end-to-end Nebari setup to management to destroy workflow
  - 📬 - Improve instance configuration
  - 📬 - Improve credential creation and setting
  - 📬 - Document minimum set of permissions required for Nebari setup
- 🗃 - Improve user management (addition, removal, permission-change, etc.)
- 🔮 - Provide super-admins insights about cluster (without k9s)
- 📬 - Update documentation to match current state of Nebari
  - 🔮 - Evaluate moving documentation back into core, to keep docs up-to-date
  - 📬 - Remove documentation about deprecated features and integrations
- 📬 - Create and add default examples on first-time Nebari installations

## Performance and stability

- 🏗️ - Upgrade to JupyterHub 4.0
- 🏗️ - Upgrade to JupyterLab 4.0
- 🏗️ - Upgrade to latest Kubernetes version
- 📬 - Implement and document standard testing procedures in the release process
- 🗃 - More robust testing
  - 🗃 - Run scheduled tests on top of those from PRs and releases
  - 🗃 - Add tests to the docker images
- 🔮 - Explore per-user-storage instead of shared NFS
  - 🔮 - Explore setting per-user resource limits

## Reliability and security

- 📬 - Refactor our CI/CD pipelines
  - 📬 - Identify bottlenecks and opportunities for improvements
  - 📬 - Critical deployments and other releases require `code owner` approval
  - 📬 - Reduce re-creation of artifacts and unnecessary runs (for example, add `[ci skip]` for Kubernetes tests)
-  📬 - Document `staging` → `production` workflows
- 🗃 - Secure our supply chain
  - 🗃 - Ensure we are not using long-lived credentials
  - 🗃 - Introduce DevSecOps practices
- 🔮 - Adopt a policy for secrets management
  - 🔮 - Investigate, scope, and implement the use of [SOPS](https://github.com/mozilla/sops)
  - 🔮 - Document the secrets management process for maintainers

## Community support and governance

- 🗃 - Adopt overall development and structure standards
  - 🗃 - All repos must have an [architecture.md](http://architecture.md) or source code organization guide
  - 🗃 - Adopt and document coding guidelines

- 🗃 - Improve our maintenance practices and OSS citizenship
  - 🗃 - Adopt a promise framework such as [https://about.gitlab.com/company/stewardship/](https://about.gitlab.com/company/stewardship/) (complementary to the governance work)
  - 🗃 - Adopt public and transparent guidelines on how we interact with the broader OSS ecosystem
  - 🗃 - Measure, track, and grow the Nebari community using the Orbit model

## Design

- 🏗 - User-friendly JupyterHub launcher
- 🗃 - Improve the accessibility of products we own or release

## General explorations

- 🔮 - Scope using [Pulumi](https://www.pulumi.com) for better abstraction of resources
- 🔮 - Scope alternatives for Argo (for default Nebari workflow manager)
- 🔮 - Evaluate Kubernetes operator for Nebari infrastructure
- 🔮 - Security explorations
  - 🔮 - Adopt [Kubescape](https://github.com/armosec/kubescape)
- 🔮 - Evaluate the use of (dagger)[https://dagger.io/blog/public-launch-announcement](https://dagger.io/blog/public-launch-announcement)
- 📬 - Expand test suite
  - 📬 - Verify stability of (Jupyter) extensions
  - 🔮 - Explore testing Nebari integrations
