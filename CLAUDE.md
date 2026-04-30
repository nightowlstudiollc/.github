# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Purpose

This is the **`.github` organization-level repository** for the `nightowlstudiollc` GitHub organization. It provides defaults inherited by all repos in the org:

- **`profile/README.md`** — Org landing page rendered at <https://github.com/nightowlstudiollc>
- **`workflow-templates/`** — Reusable workflow templates available in the Actions tab of any org repo
- **`.github/dependabot.yml`** — Dependabot config for this repo's own actions
- **`.github/workflows/claude.yml`** — `@claude` mention handler for issues/PRs in this repo

## Architecture

There is no build system, test suite, or application code. This repo contains only GitHub configuration files:

- `workflow-templates/claude-blocking-review.yml` — Caller stub for `smartwatermelon/github-workflows/.github/workflows/claude-blocking-review.yml@v3.0.0`. When a NightOwl repo selects this template via Actions → New workflow, GitHub copies the file into that repo.
- `workflow-templates/claude-blocking-review.properties.json` — Picker metadata (name, description, icon).
- `workflow-templates/dependabot-auto-merge.yml` — Auto-merges patch + minor Dependabot bumps after CI passes. Narrow scope (see header comment).

## Key details

- The Claude Blocking Review workflow requires a `CLAUDE_CODE_OAUTH_TOKEN` secret on the **consuming repo**. The token is provisioned per-repo by Claude Code CLI's `/install-github-app` slash command — there is no org-level installation scope. The expectation is that every repo Andrew owns already has the GitHub App installed; missing-secret cases are remediation gaps surfaced by `claude-review-audit.sh` in `smartwatermelon/github-workflows`.
- The actual reusable-workflow logic lives in `smartwatermelon/github-workflows`, not here. This repo only holds the picker stub.
- Workflow templates are a **one-time scaffold** — selecting one copies the file into the consumer repo. Future edits here do not propagate. Live propagation happens via the `uses: ...@v3.0.0` line in the consumer's copy plus Dependabot bumps.
- Profile rendering requires this repo to be **public**. Workflow templates work in either public or private `.github` repos.

## Related

- [smartwatermelon/.github](https://github.com/smartwatermelon/.github) — sister repo for the smartwatermelon user account. Contains the same workflow templates (decoratively, since user accounts don't get the picker UI).
- [smartwatermelon/github-workflows](https://github.com/smartwatermelon/github-workflows) — the reusable-workflow source repo this scaffolds against.
- Plans: see `docs/plans/2026-04-30-create-nightowlstudiollc-github-defaults.md` and `2026-04-30-required-workflows-nightowlstudiollc.md` in `smartwatermelon/github-workflows`.
