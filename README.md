# Everyone Votes

Nonpartisan voter education, resources, and guidance for overwhelmed and busy voters.

## Project status

Everyone Votes is at the starting line. This repository currently contains the collaboration setup; the application framework, dependencies, and hosting are still to be chosen. There is no app to install or run yet.

Design, content, research, accessibility, and engineering contributions are welcome. Start with an [issue](https://github.com/jyeung9/everyone-votes/issues) to discuss an idea or find work to join.

## Get the starting files

You need Git, a GitHub account to contribute, and an editor of your choice.

```sh
git clone --branch staging https://github.com/jyeung9/everyone-votes.git
cd everyone-votes
git switch -c your-name/short-description
```

This starts your work from `staging`, where upcoming changes come together. If you do not have repository write access, [fork the repository](https://github.com/jyeung9/everyone-votes/fork), clone your fork, and follow the [fork setup instructions](CONTRIBUTING.md#contributing-from-a-fork).

For a files-only copy, [download staging as a ZIP](https://github.com/jyeung9/everyone-votes/archive/refs/heads/staging.zip). Use a clone or fork if you plan to submit changes.

## How changes move

```text
your feature branch → staging → main
```

- **Feature branches:** focused work on a change.
- **`staging`:** the shared integration branch. Open ordinary pull requests here.
- **`main`:** the reviewed, stable version. Maintainers promote ready changes from `staging` through a pull request.

`staging` is a Git branch; a hosted staging preview has not been configured yet. See [CONTRIBUTING.md](CONTRIBUTING.md) for the full workflow and review checklist.

## What is in this repository

| File | Purpose |
| --- | --- |
| [CONTRIBUTING.md](CONTRIBUTING.md) | Branching, pull requests, and contribution expectations |
| [.github/](.github/) | Issue and pull request templates |
| [.editorconfig](.editorconfig) | Shared whitespace and file-format conventions |
| [.gitignore](.gitignore) | Keeps local environment files and common generated files out of Git |

## Before the first runnable app

The initial application setup should include these together:

- The chosen framework, a pinned runtime version, and a committed dependency lockfile.
- Exact commands here for installing dependencies, running locally, and checking a change.
- A safe `.env.example` if configuration is needed, with instructions for obtaining required values. Never commit real credentials.
- Automated checks for pull requests, once there is application code to check.
- A staging preview and a documented production release process.

A project license also remains to be selected by the maintainer.
