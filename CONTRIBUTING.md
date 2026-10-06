# Contributing to Everyone Votes

Start small: describe the problem in an [issue](https://github.com/jyeung9/everyone-votes/issues), check for related work, and agree on the scope before taking on a large change. Content and design work can start in an issue without a development environment.

## Branch workflow

Use `staging` as the starting point and pull request destination for everyday work. Keep `main` for reviewed changes that are ready to release.

With a clean working tree in an existing clone:

```sh
git switch staging
git pull --ff-only origin staging
git switch -c your-name/short-description
```

Make the change, inspect it, and commit only the files you intend to include:

```sh
git status
git diff
git add <changed-files>
git commit -m "Describe the change"
git push -u origin HEAD
```

Replace `<changed-files>` with the paths you reviewed. Open a pull request with **base: `staging`**, explain what changed and why, and describe how you checked it. GitHub may suggest `main` by default, so check the base branch before submitting. Draft pull requests are welcome for early feedback.

Branch names should describe the work, such as `julie/improve-welcome-copy`. Codex-created branches use `codex/short-description`.

## Contributing from a fork

Fork the repository on GitHub, then substitute your GitHub username below:

```sh
git clone https://github.com/YOUR-USERNAME/everyone-votes.git
cd everyone-votes
git remote add upstream https://github.com/jyeung9/everyone-votes.git
git fetch upstream
git switch -c your-name/short-description upstream/staging
```

Commit your changes and run `git push -u origin HEAD`. Open a pull request from your fork to **`jyeung9/everyone-votes`, base: `staging`**.

To bring newer shared changes into your feature branch, first commit or otherwise save your current work, then run `git fetch upstream` and `git merge upstream/staging`. In a direct clone, use `origin` in place of `upstream`.

## Review expectations

- Keep each pull request focused and explain the user-facing effect.
- Include screenshots for visual changes and describe keyboard and small-screen checks when relevant.
- Write in clear, accessible, nonpartisan language. Support factual voting information with links to the relevant official election authority, and identify the jurisdiction and date checked.
- Keep credentials, local `.env` files, and personal voter information out of commits and issues.
- Update setup instructions when a change adds a dependency, configuration value, or new command.
- State what you verified and what remains unverified. There is no application test suite yet; for documentation changes, read the rendered Markdown and check links and commands.

## Promoting staging to main

Maintainers open a pull request with **base: `main`** and **compare: `staging`**, summarize the included changes, and verify that they are ready for the stable branch.

Use **Create a merge commit** for promotions so `staging` and `main` retain shared history. After promotion, bring `main` back into `staging` before the next batch:

```sh
git fetch origin
git switch staging
git merge --ff-only origin/staging
git merge --ff-only origin/main
git push origin staging
```

These commands assume a clean working tree and that `staging` has not advanced since promotion. If fast-forwarding fails, preserve the work and reconcile the branches through a pull request; do not force-push. Keep the long-lived `staging` branch after merging a promotion.

Promotion updates Git history only. Deployment instructions will be added when hosting is configured.
