# .github

Organization-level defaults for `nightowlstudiollc` repositories.

## What's included

- **`profile/README.md`** — Org landing page rendered at <https://github.com/nightowlstudiollc>
- **`workflow-templates/claude-blocking-review.yml`** — Available as a workflow template in the Actions tab when creating new workflows in any NightOwl repo
- **`workflow-templates/dependabot-auto-merge.yml`** — Workflow template that auto-merges patch + minor Dependabot bumps
- **`.github/dependabot.yml`** — Dependabot config for this repo's own GitHub Actions pins
- **`.github/workflows/claude.yml`** — `@claude` mention handler for issues/PRs in this repo

## Usage

### Claude Blocking Review

When creating a new repo (or adding the workflow to an existing one):

1. Go to the repo's **Actions** tab.
2. Click **New workflow**.
3. Find **Claude Blocking Review** under the **By Night Owl Studio** templates section.
4. Click **Configure**.
5. Commit the workflow file.
6. Ensure `CLAUDE_CODE_OAUTH_TOKEN` is set (org-level secret recommended).

### Dependabot Auto-Merge

Optional. Add via the same Actions → New workflow flow. Auto-merges only `patch` and `minor` Dependabot bumps; majors stay open for manual review.

## Related

- [smartwatermelon/github-workflows](https://github.com/smartwatermelon/github-workflows) — the source of the reusable workflow this scaffolds against.
- [smartwatermelon/.github](https://github.com/smartwatermelon/.github) — sister repo for the smartwatermelon user account.
