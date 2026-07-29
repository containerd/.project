# containerd project repository

This `project` repository contains the canonical metadata, governance definitions, and specified project roles (such as maintainers and security advisors) for [containerd](https://containerd.io/).

It also implements the CNCF `.project` (dot-project) initiative to centralize and automate metadata management for all CNCF projects.

## What's in this repo

| File | Purpose |
|------|---------|
| `project.yaml` | Canonical project metadata (name, maturity, repositories, governance links, …) |
| `maintainers.yaml` | Maintainer and reviewer roster used for drift detection and mailing-list sync |
| `CODEOWNERS` | Ensures PRs to this repo require maintainer approval |
| `GOVERNANCE.md` | Core governance definitions for containerd projects |
| `MAINTAINERS` | Maintainers and reviewers list |
| `CONTRIBUTING.md` | Contributing guidelines for containerd projects |
| `.github/workflows/validate.yaml` | CI — validates `project.yaml` and `maintainers.yaml` on every PR |
| `.github/workflows/update-landscape.yml` | Automatically proposes landscape updates when `project.yaml` changes |

## Project core documents

Project governance, maintainer list, and contributing guidelines are all
maintained as single copies within this repository and linked to from
all containerd projects to reduce duplication and maintenance across all
repos.

You can see each of these core documents here:
 * [Governance for containerd projects](./GOVERNANCE.md)
 * [Maintainers and reviewers list](./MAINTAINERS)
 * [Contributing guidelines](./CONTRIBUTING.md)

For an example of how to include these in a project's `README.md` file see
the following markdown:
```
## Project details

{Some-project} is a containerd sub-project, licensed under the [Apache 2.0 license](./LICENSE).
As a containerd sub-project, you will find the:
 * [Project governance](https://github.com/containerd/.project/blob/main/GOVERNANCE.md),
 * [Maintainers](https://github.com/containerd/.project/blob/main/MAINTAINERS),
 * and [Contributing guidelines](https://github.com/containerd/.project/blob/main/CONTRIBUTING.md)

information in our [`containerd/.project`](https://github.com/containerd/.project) repository.
```

If the project has its own `MAINTAINERS` file, that file should contain a comment with a link to
the core `MAINTAINERS` file in `containerd/.project` and mention it as additional maintainers.

### Non-core project documents

If your project is a non-core addition to the containerd GitHub organization, please
make the following changes to your project once approved and added:

 * Clearly state in an opening sentence within your project `README.md` that "_Project X is
 a **non-core** subproject of containerd_"
 * Add the project details boilerplate provided above with the following two changes:
   1. The first line should be modified to state: _{Some-project} is a **non-core** containerd subproject_
   2. Do not link to the core `MAINTAINERS` file in `containerd/.project`. That link should be modified to point to your existing non-core project `MAINTAINERS` file.

## Scripts and utilities

Originally, this repository held common CI scripts/checks as well as the
`release-tool`. Neither of those items are maintained in this repository.
See the below paragraphs for their new locations:

### The release-tool utility

The `release-tool` now has its own repository. It is located in
the [`release-tool`](https://github.com/containerd/release-tool) subproject.

### Common CI checks/scripts

After migrating the entire project and all sub-projects to GitHub
Actions for CI, we made a subproject repo that contains a common `project-checks`
action with our file header, DCO, and vendor checks. That repository is
located in [`project-checks`](https://github.com/containerd/project-checks)

## Keeping metadata up to date

Open a pull request against this repository to update any metadata field.
The validate workflow will check schema correctness and block merge if validation fails.

## Resources

- [`.project` documentation](https://github.com/cncf/automation/tree/main/utilities/dot-project)
- [Schema reference](https://github.com/cncf/automation/blob/main/utilities/dot-project/SCHEMA.md)
- [CNCF Automation repository](https://github.com/cncf/automation)
