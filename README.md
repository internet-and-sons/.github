# internet-and-sons/.github

This repo holds the **org-level conventions, the auto-applied PR template, and a starter scaffold** for new internet-and-sons repos. Most of its files are special — GitHub treats them differently from a normal repo.

If you landed here looking for the welcome page that shows on [github.com/internet-and-sons](https://github.com/internet-and-sons), that's [`profile/README.md`](./profile/README.md) — read on for what's in here and how to change it.

## Who this is for

Anyone with org-write access who needs to:

- Update the rules every internet-and-sons repo follows.
- Adjust the PR template that auto-applies to every repo's pull requests.
- Tweak the starter scaffold copied into a new repo when spinning one up.
- Update the welcome README that shows on the org's GitHub landing page.

## What's in here

| Path | What it is | How GitHub uses it |
| --- | --- | --- |
| [`profile/README.md`](./profile/README.md) | The org landing page. Welcomes visitors, explains what this org is, walks through how to start a new repo. | Auto-rendered at [github.com/internet-and-sons](https://github.com/internet-and-sons). Public-visible. The repo grid GitHub renders below it does the discovery work — no need to hand-curate a list. |
| [`CONTRIBUTING.md`](./CONTRIBUTING.md) | The org-wide rules every repo follows: PR-required, branch naming, merge policy, AI-agent rule, hooks. | Auto-used as the default `CONTRIBUTING.md` for any repo in the org that doesn't have its own. |
| [`PULL_REQUEST_TEMPLATE.md`](./PULL_REQUEST_TEMPLATE.md) | The PR description template (Summary / Why / What changed / Docs touched / Test plan). | Auto-applied to every PR opened in any internet-and-sons repo, unless that repo overrides with its own template. |
| [`repo-skeleton/`](./repo-skeleton) | Five starter docs (`README`, `CLAUDE`, `CONTRIBUTING`, `TODO`, `LEARNINGS`) plus a drop-in `LICENSE-MIT` for public repos. All carry `{{placeholders}}` and inline comments. | Not magic — copy these into a new repo by hand when spinning one up. The "Starting a new repo here" section in `profile/README.md` walks through it. |

GitHub also looks for `CODE_OF_CONDUCT.md`, `SECURITY.md`, `SUPPORT.md`, and `ISSUE_TEMPLATE/` here. Not shipping those yet — they get added when there's an actual reason to (a public repo with external contributors complaining, a security-disclosure flow worth formalising). No need for ceremony.

## When to update what

| You want to… | Edit |
| --- | --- |
| Change the welcome page on github.com/internet-and-sons | `profile/README.md` |
| Add or change a rule that applies to every repo | `CONTRIBUTING.md` |
| Adjust the PR template (sections, wording) | `PULL_REQUEST_TEMPLATE.md` |
| Update the scaffold for new repos (placeholder phrasing, structure) | `repo-skeleton/*.md` |
| Add a new file type GitHub auto-uses across the org (CoC, security, etc.) | Add the file at the repo root |

## Workflow for changes

This repo follows the same rules as every other internet-and-sons repo: every change goes through a PR. See [`CONTRIBUTING.md`](./CONTRIBUTING.md) for the full picture.

The exception was the bootstrapping commit (when the repo was empty) — that pushed directly to `main` because there was no `main` to protect yet. From here on, branch + PR + merge.

Quick flow:

```
git checkout main
git pull
git checkout -b <prefix>/<short-name>
# edit files
git add -A && git commit -m "..."
git push -u origin <branch>
gh pr create
```

Self-merge is fine for routine doc edits once any CI / pre-commit checks pass. Loop in a collaborator on structural changes (renaming a file GitHub specifically looks for, removing a section other repos link to, etc.).

## What this repo is NOT

- **Not a place for project source code.** Each project — open-source or private — lives in its own repo. This one is just the org-level scaffolding.
- **Not a documentation hub.** This repo is for the small set of files GitHub auto-uses across the org. Long-form docs about a specific project live in that project's repo (`docs/`, `CLAUDE.md`, `LEARNINGS.md`).
- **Not a template repo (in GitHub's "Use this template" sense).** The `repo-skeleton/` folder is a copy-source, not a GitHub repo template. New repos are created normally; the skeleton files are copied in by hand.

## Help

If something here doesn't make sense, open an issue or ask. Better than guessing — these files affect every repo in the org, so a wrong assumption ripples wider than usual.
