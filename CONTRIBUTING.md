# Contributing to internet-and-sons repos

A few rules that apply to every repo in this org. Each repo has its own `CONTRIBUTING.md` that adds repo-specific stuff (setup, version-bumping, etc.) — read that next.

If you're brand new, skim this whole page first. Five minutes. Then click into whichever repo you'll work in and read its own `CLAUDE.md` — that's where the hard rules and architectural picture for that repo live.

## How changes land

**Every change reaches `main` via a squash-merged PR.** Branch off `main`, commit as many times as you want, push, decide when it's time, open a PR, someone merges. Same rule for public open-source repos and private ones — the PR is the unit of review.

## Branch names

Pick a prefix that matches what you're doing, then a short slug:

| Prefix | For | Example |
| --- | --- | --- |
| `feat/` | A new feature or new content | `feat/inline-image-generation` |
| `fix/` | A bug fix | `fix/typo-in-readme` |
| `chore/` | Maintenance, refactors, dependency bumps | `chore/bump-deps` |
| `docs/` | Documentation only | `docs/clarify-bumping-flow` |
| `edit/` | Content edits in content repos | `edit/rewrite-intro-section` |

If your change doesn't fit one cleanly, pick the closest. Don't overthink it.

## PR descriptions

Every PR auto-fills with the org-level template — you'll see it the moment you click "Create pull request." Fill in the sections; don't replace it with free-form prose. The template covers what reviewers actually need (Summary / Why / What changed / Docs touched / Test plan).

If you've got something the template doesn't fit, expand a section, don't delete it. And if a section genuinely doesn't apply, say so in one short line — empty sections are fine, vanished sections aren't.

## Merging

- **Squash-and-merge** is the default merge style. Keeps `main`'s history readable.
- **Repo owners can self-merge their own PRs** once the PR template is filled in, the pre-commit hook has passed locally, and any required CI checks are green. No "stamp from a colleague" required for routine work on your own repo — but use judgment: structural changes still benefit from a second pair of eyes.
- **Non-owners need an owner's review** before merging.
- **AI agents don't self-merge.** If you're using Claude Code or another AI agent to make changes on your behalf, the agent **opens the PR and stops there** — it shares the PR URL and waits for you to merge yourself. The self-merge rule above is for humans on their own routine work; an AI doesn't get to decide a change is "routine enough" to ship without your eyes on the GitHub diff. Tell the agent "merge it" explicitly when you're ready, and only for the specific PR you mean.

If you're not sure whether you're an "owner" of a repo, ask. Usually it's whoever maintains it day to day.

## Public vs private repos

This org runs a mix of public open-source repos and private ones. The rules above apply to both. Public repos additionally need:

- A **`LICENSE`** file at the repo root. Drop in [`repo-skeleton/LICENSE-MIT`](https://github.com/internet-and-sons/.github/blob/main/repo-skeleton/LICENSE-MIT) (or pick another OSI-approved license if there's a reason) and fill in the year and copyright holder.
- A **`README.md` written for strangers**, not just collaborators. Assume the reader has never met you and arrived from a search engine. The `repo-skeleton/README.md` placeholder works for both — just lean public-friendly when filling it in.
- Awareness that **issues and PRs from strangers are possible**. That's the whole point of open-sourcing it. Be ready to triage — or set expectations clearly in the README if you can't.

Private repos can stay terser; the audience is just you and collaborators you invited.

## Pre-commit hooks

Some repos use git pre-commit hooks for things like version-drift checks. If a repo has a `.githooks/` folder, run this once after cloning:

```
git config core.hooksPath .githooks
```

Then commits run the checks automatically. The repo's own `CONTRIBUTING.md` will tell you what the hook is checking for and what to do if it fails.

## Where the rest of the rules live

- **Each repo's `CLAUDE.md`** carries safety rules, what the repo does, and the architectural picture. **Read this first** when you open a repo. Claude Code auto-loads it; if you're not using Claude Code, just open the file.
- **Each repo's `CONTRIBUTING.md`** carries the workflow specifics — how to set the repo up, how to bump a version, what NOT to change without coordination.
- **Each repo's `LEARNINGS.md`** carries the non-obvious gotchas — things that cost real debugging time, documented so the next person doesn't relearn them.

## Stuck?

Ask. Way better than re-reading these docs in circles or guessing. Five "obvious" questions answered beats one wrong assumption landing on `main`.
