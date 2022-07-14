# Nebari repository guidelines

This document attempts to outline a structure for creating and associating GitHub repositories with the Nebari project.

Requests for creating, transferring, modifying, or archiving repositories can be made by opening a request against the nebari-dev/governance repo.

## 📦 Core Repositories

Core repositories are considered core components of Nebari. They are
utilities, tools, applications, or libraries that are expected to be present in
every or nearly every Nebari cluster, such as components and tools included
in official Nebari releases. Additionally, the Nebari website, and other project-wide infrastructure will remain in the Nebari
GitHub organization.

### 🎯 Goals

Create a broader base of repositories than the existing
gh/nebari-dev/nebari so that the project can scale. Present expectations
about the centrality and importance of the repository in the Nebari
ecosystem. Carries the endorsement of the Nebari community.

### ⚡️ Rules

- Must live under `github.com/nebari-dev/<project-name>`
- Must adopt the Nebari Code of Conduct statement in their repo.
<!-- * TODO: double check and link -->
- All code projects use the BSD-3License. Documentation
  repositories must use the Creative Commons License version 4.0.
