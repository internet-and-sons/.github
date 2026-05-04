# Project context — internet-and-sons/.github

This file is auto-loaded as project context whenever Claude Code is opened in this repo. Read it first, then read the companion files below as the task requires.

## What this repo is

The org-level `.github` repo for [internet-and-sons](https://github.com/internet-and-sons). It holds the small set of files GitHub auto-applies across every repo in the org — the org landing page, the org-wide `CONTRIBUTING.md`, the auto-applied PR template — plus a `repo-skeleton/` folder of starter docs that get hand-copied into new repos.

The repo is **public**. Anything committed here is visible at github.com/internet-and-sons/.github. It does not contain project source code; each project lives in its own repo.

## Companion files (read as the task warrants)

- **`CONTRIBUTING.md`** — note: in this repo the root `CONTRIBUTING.md` is the **org-wide** document that GitHub serves as the fallback to every other repo in the org. There is no separate per-repo `CONTRIBUTING.md`; the org-wide one covers what applies here too.
- **`TODO.md`** — pending work, deferred decisions, done log. **Gitignored — local-only by design.** Won't exist in a fresh clone; create from `repo-skeleton/TODO.md` if you need it.
- **`LEARNINGS.md`** — non-obvious gotchas. **Gitignored — local-only by design.** Same as `TODO.md`: not present in a fresh clone. The intent is to avoid overexposing internal scheduling and gotchas on a public repo.

Org-wide rules live in this repo's own [`CONTRIBUTING.md`](./CONTRIBUTING.md). Read it once; it covers branching, PRs, and the merge policy that applies to every repo here.

## Hard rules (always apply, never override)

1. **Every change goes through a PR.** No direct pushes to `main`. The bootstrap commit was the one-time exception (empty repo, no `main` to protect). See [`CONTRIBUTING.md`](./CONTRIBUTING.md) for the full policy.

2. **Changes here ripple to every repo in the org.** `CONTRIBUTING.md`, `PULL_REQUEST_TEMPLATE.md`, and the `repo-skeleton/` files are inherited (or copied) by every internet-and-sons repo. Default to extra caution: a wording change here can subtly change the rules dozens of repos operate under. When the change is structural — renaming a file GitHub specifically looks for, removing a section other repos may link to — loop in a collaborator before merging.

3. **Don't commit `TODO.md` or `LEARNINGS.md`.** They're gitignored on purpose for this public repo. If you need to track something visible to the org, put it in an issue, not these files.

## Quick orientation

| Path | What it is |
| --- | --- |
| `profile/README.md` | Public landing page rendered at github.com/internet-and-sons. |
| `CONTRIBUTING.md` | Org-wide rules; auto-served as the fallback `CONTRIBUTING.md` to every repo in the org. |
| `PULL_REQUEST_TEMPLATE.md` | Auto-applied to every PR opened in any internet-and-sons repo. |
| `repo-skeleton/` | Starter docs (`README`, `CLAUDE`, `CONTRIBUTING`, `TODO`, `LEARNINGS`) plus `LICENSE-MIT`, hand-copied into new repos. |
| `LICENSE` | MIT, required because this repo is public. |

## Need help?

If you're unsure whether a change is safe — especially anything that's inherited org-wide — stop and ask. The cost of pausing is near-zero; the cost of a wrong assumption ripples across every repo in the org.
