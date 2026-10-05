# .github

Organization-level defaults for `nightowlstudiollc` repositories.

## What's included

- **`profile/README.md`** — Org landing page rendered at <https://github.com/nightowlstudiollc>
- **`workflow-templates/dependabot-auto-merge.yml`** — Workflow template that auto-merges patch + minor Dependabot bumps
- **`.github/dependabot.yml`** — Dependabot config for this repo's own GitHub Actions pins
- **`.github/workflows/claude.yml`** — `@claude` mention handler for issues/PRs in this repo

## Usage

### Dependabot Auto-Merge

Optional. Add via the Actions tab → New workflow. Auto-merges only `patch` and `minor` Dependabot bumps; majors stay open for manual review.

## Related

- [smartwatermelon/github-workflows](https://github.com/smartwatermelon/github-workflows) — the source of the reusable workflow this scaffolds against.
- [smartwatermelon/.github](https://github.com/smartwatermelon/.github) — sister repo for the smartwatermelon user account.
