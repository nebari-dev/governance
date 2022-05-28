# Style guide for repositories

We use [pre-commit](https://pre-commit.com/) to automatically enforce certain styles across our [`nebari` repository](https://github.com/nebari-dev/mebari).
You can view the full configuration in the [`.pre-commit-config.yaml` file](https://github.com/nebari-dev/nebari/blob/main/.pre-commit-config.yaml).
These tools have been agreed upon by the engineering team and can be applied to a new repository under the [`nebaro-dev organisation`](https://github.com/nebari-dev) as a team member sees fit.

A short summary of the tools and the file types they affect are given in the table below.

| File type | Tools |
| :--- | :--- |
| Markdown | [`prettier`](https://prettier.io/) |
| YAML | [`prettier`](https://prettier.io/) |
| Python | [`black`](https://black.readthedocs.io/), [`flake8`](https://flake8.pycqa.org/), [`pyupgrade`](https://github.com/asottile/pyupgrade) |
