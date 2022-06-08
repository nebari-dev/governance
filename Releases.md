# Releases

*We are currently undergoing a project rename and repo transfer. Please bare with use as we work to improve the release process.*

## nebari

The release process for `nebari` is managed by a checklist which maintainers can create from a new issue template. When the time comes, that issue is used to track all related tasks and as a place to discuss the release. 

> [Click here to create this release checklist issue.](https://github.com/Quansight/qhub/issues/new?assignees=&labels=type%3A+release+%F0%9F%8F%B7&template=release-checklist.md&title=%5BRELEASE%5D+-+%3Cversion%3E)


### Current release details

|                                    PyPI version                                     |                                               Conda-Forge version                                               |     Versioning system scheme      |  Cadence   |
| :---------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------: | :-------------------------------: | :--------: |
| [![PyPI version](https://badge.fury.io/py/qhub.svg)](https://badge.fury.io/py/qhub) | [![Conda Version](https://img.shields.io/conda/vn/conda-forge/qhub.svg)](https://anaconda.org/conda-forge/qhub) | [SemVer](https://semver.org/) `*` | AdHoc `**` |

> `*` a switch to CalVer has been [proposed](https://github.com/Quansight/qhub/issues/1242).

> `**` coupled with the switch to CalVer versioning, we aim to adopt a more regular cadence. Something on the order of once a month or once every six weeks. 


### nebari-dask

[`nebari-dask`](https://github.com/conda-forge/qhub-dask-feedstock) is a meta package which contains specific versions of `dask`, `dask-gateway` and `distributed`. 

> Released at the same time as `nebari` with matching version numbers. Included in the release checklist linked above.


### nebari-docker-images 

The [nebari-docker-images](https://github.com/nebari-dev/nebari-docker-images) repo contains the Dockerfiles for the JupyterHub, JupyterLab and Dask-Gateway Kubernetes deployments. This repo also contains the workflow needed to build and push them the images to [github.com/orgs/nebari-dev/packages](https://github.com/orgs/nebari-dev/packages) and [quay.io/organization/nebari](https://quay.io/organization/nebari).

> These images are built and tagged with the same version number of the corresponding `nebari` release. Included in the release checklist linked above.