# Active infrastructure review and merge guidelines

We follow team policies for review/merge that are more specific than our general development merge policies.

- [Active infrastructure review and merge guidelines](#active-infrastructure-review-and-merge-guidelines)
  - [Changing active infrastructure in general](#changing-active-infrastructure-in-general)
  - [Terraform changes](#terraform-changes)
    - [Changes to running infrastructure](#changes-to-running-infrastructure)

## Changing active infrastructure in general

The following general policies apply to any change that will affect active infrastructure. Policies specific to Terraform changes are described below.

Here are some guidelines for merging and reviewing in this case:

- The PR author must also merge the PR. (**REQUIRED** :pushpin:) Because a PR is a reflection of a deployment, the author of the PR should also be the one that merges it, since only they know what infrastructure has actually been deployed.

- Explicitly list a back-up if you must step away. (**REQUIRED** :pushpin:) PR authors are responsible for the infrastructure changes that they make. You should generally only make a change to live infrastructure if you’ll have the bandwidth to ensure it is fixed if something goes wrong. If for some reason you must step away, make it clear who else is responsible for shepherding the PR.

- Be careful when self-merging without review. Because changing active infrastructure is potentially confusing or disruptive to users, be extra careful if you self-merge without a review approval. Consider whether your commit will cause a change that might be destructive and ask if you really need to merge now or can wait for review. That said, sometimes the only way to understand the impact of a change is to merge and see how things go, so use your best judgment!

## Terraform changes

Terraform is used for directly provisioning and modifying cloud infrastructure (as opposed to only deploying applications on pre-existing cloud infrastructure). This lets us treat our infrastructure as code, so we can use regular code quality practices (code review, linters, extensive documentation, etc.) to keep the quality of our infrastructure high. However, it comes with a few caveats:

1. Locally and iteratively testing terraform is impossible - as we develop it, the infrastructure is deployed / modified / destroyed as we go.
1. Behavior of terraform code differs based on the current state of the infrastructure (as represented in the state file).
1. While `terraform plan` can tell us what Terraform thinks it is going to do, it might not always succeed. Permission errors or organizational restrictions can cause it to fail. Timeouts can happen. Runtime errors show up.

Thanks to all these, it is impossible to either:

1. Accurately gauge the impact of a Terraform code change only from looking at the text
1. Automatically deploy it via continuous deployment

As a result, we have some workflows that are specific to using Terraform, described below.

### Changes to running infrastructure

In this scenario, there is already-running infrastructure, and you are deploying changes to it.

To deploy changes, follow these steps:

1. **Propose changes.** Change the codebase and open a PR. Do not deploy changes yet. Use `terraform plan` rather than `terraform apply` to understand the change before deploying it.
1. **Post the output of `terraform plan`** in your PR’s top comment, post the output of `terraform plan` whenever you update the PR. This helps others review the likely impact on our infrastructure.
1. **Wait for review and approval.** Leave the PR open for other team members to review and approve.

   > **Warning**
   > When reviewing changes to running infrastructure: focus is on both making sure the change is minimally disruptive, and on the quality of the infrastructure design.

1. **Deploy the change.** Once approved, leave a comment in the PR that you will start deploying the changes. Then `terraform apply` your change and verify it works ok.
1. **Iterate as needed.** If things break, or if you need to iterate on the deployment, follow this cycle until the infrastructure is in the state you wish:

   1. Amend your PR with changes
   1. Deploy with terraform apply
   1. Comment that you’ve made a deployment

1. **Communicate that you’ve finished deploying.** Leave a comment in the PR that the changes have been deployed. You should always communicate when a deployment has been made!
1. **Self-merge or request another review.** If you didn’t need to make a change to the PR, merge the PR. If you made changes to the PR, use your judgment to decide if you should request another review or if you should self-merge it directly. If you merge, leave a comment about changes made since the initial approval.
