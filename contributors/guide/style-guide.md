# Style guide for repositories

We use [pre-commit](https://pre-commit.com/) to automatically enforce certain styles across our [`nebari` repository][nebari-repo].
You can view the full configuration in the [`.pre-commit-config.yaml` file](https://github.com/nebari-dev/nebari/blob/main/.pre-commit-config.yaml).
These tools have been agreed upon by the engineering team and can be applied to a new repository under the [`nebari-dev organisation`][nebari-dev-organisation] as a team member sees fit.

A short summary of the tools and the file types they affect are given in the table below.

| File type | Tools                                                                                                                                 |
| :-------- | :------------------------------------------------------------------------------------------------------------------------------------ |
| Markdown  | [`prettier`](https://prettier.io/)                                                                                                    |
| YAML      | [`prettier`](https://prettier.io/)                                                                                                    |
| Python    | [`black`](https://black.readthedocs.io/), [`flake8`](https://flake8.pycqa.org/), [`pyupgrade`](https://github.com/asottile/pyupgrade) |

## Applying to repos

When creating a new repo, please use any pre-commit hooks and tools that are useful.

When working with an existing repo, please balance the benefits of adding a tool or pre-commit hook with considerations such as

- the amount of code churn
- how it will improve code maintainability
- the time it may add to CI runs

<!-- links -->

[pre-commit-nebari]: ***
[nebari-dev-organisation]: https://github.com/nebari-dev
[nebari-repo]: https://github.com/nebari-dev/nebari
