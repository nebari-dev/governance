# GitHub Admin

This doc provides information about how we administer the Nebari GitHub Org.

- [GitHub Admin](#github-admin)
  - [:lock: GitHub Permissions](#lock-github-permissions)
    - [Least Privilege](#least-privilege)
    - [GitOps](#gitops)

## :lock: GitHub Permissions

In administering GitHub we follow the principles of

1. Least Privilege
1. Use GitOps for scalability and transparency

### Least Privilege

When requesting permission please

1. Use the least privileged role necessary

   - Please refer to the [GitHub Docs](https://help.github.com/en/github/setting-up-and-managing-organizations-and-teams/repository-permission-levels-for-an-organization) to understand the different levels of permission that GitHub offers.

1. Request access to only the resources you need access to

<!-- TODO implement peribolos -->

### GitOps

We use [Peribolos](https://github.com/kubernetes/test-infra/tree/master/prow/cmd/peribolos) from Kubernetes
to manage GitHub with GitOps.

1. The GitHub config is stored in [org.yaml](****)
2. To request access please open a PR modifying [org.yaml](******)

- For more info please refer to the [README](***)
- Access to repos is granted through GitHub teams
  - Teams are granted permissions on repositories
  - Individuals should be added to one or more teams to gain privileges for a particular repository
