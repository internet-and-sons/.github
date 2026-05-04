# Internet & Sons

Welcome. This is the GitHub home of [Internet & Sons](https://www.internetandsons.com) — Tal Oron's independent studio out of London. We build a mix of open-source tools, AI/agent skills, and private client work. Some lives here in public; some stays behind the curtain. The repo grid below this README is the source of truth for what's open right now — no curated list to rot.

If you arrived here from one of the open-source projects, the project's own `README.md` is where to start. This page is the org-level orientation: what the conventions are, and how to contribute back if you'd like to.

## If you're new here

1. **Start with [`CONTRIBUTING.md`](https://github.com/internet-and-sons/.github/blob/main/CONTRIBUTING.md)** in this repo. It's the few rules every internet-and-sons repo follows — branching, PR template, merge policy. Five minutes of reading.
2. **Then click into whichever repo you'll be working in** and open its `CLAUDE.md`. Each repo has its own quirks, hard rules, and gotchas — they're all in there. If you use Claude Code, it auto-loads CLAUDE.md when you open the repo, so you don't have to remember to read it.
3. **Stuck?** Open an issue or ask. Better than reading docs in circles.

## Cloning a repo onto your computer

Easiest path — open Claude Code and ask it in plain English:

> *"Clone geo-reporter."*

Claude handles auth, drops the repo in `~/projects/<repo-name>/`, and opens it for you. No git commands to remember. Swap `geo-reporter` for whichever repo you want.

If you'd rather run it yourself in the terminal:

```bash
gh repo clone internet-and-sons/<repo-name> ~/projects/<repo-name>
```

Needs the [GitHub CLI](https://cli.github.com) — `brew install gh && gh auth login` if you don't have it yet. Then open the folder in your editor and you're set; each repo's `CLAUDE.md` auto-loads when Claude Code opens it.

## When to make a new repo

**Default to one repo per stack piece.** Each tool, each agent skill, each distinct surface area gets its own repo. A skill that's substantial enough to evolve on its own (its own SKILL.md, its own scripts, its own learnings) belongs in its own repo, not bundled inside another. Small repos are easier to read, easier to grant access to selectively, and let each piece carry its own `CLAUDE.md` / `TODO.md` / `LEARNINGS.md` without competing.

If you're unsure, err toward a new repo. Splitting later is harder than starting clean.

## Starting a new repo here

When you spin up a new repo in this org, follow this walkthrough. It keeps things consistent across the org so the next person to land in your repo recognises the layout.

### 1. Pick visibility deliberately

This org runs both public open-source repos and private repos. There's no automatic default — choose with intent:

- **Public** if it's a reusable tool, a skill, or anything you'd be happy to point a stranger at. Public repos additionally need a `LICENSE` file (see [step 4](#4-copy-the-scaffold) — `repo-skeleton/LICENSE-MIT` is a drop-in) and a README written for someone who's never met you.
- **Private** if it's client work, contains credentials/keys, isn't ready to be seen, or is just useful only to you.

If in doubt, start private. Flipping a repo to public later is one click; the reverse is messier.

### 2. Name it clearly

Short, descriptive, kebab-case (lowercase, hyphens). No mandatory prefix — pick a name that reads well in a sentence: *"the geo-reporter repo"*, *"the apple-music-extract repo"*. If the name needs a glossary entry to make sense, it's the wrong name.

Avoid generic names (`utils`, `tools`, `scripts`) — those age badly when you have ten of them. Be specific about what the repo *does* or what domain it's in.

### 3. Write a clear "About"

GitHub asks for a description right under the repo name on the New Repository page. **Fill it in.** One short sentence that says what the repo *is* — that's the line people see when scrolling the org repo grid trying to find the right one, and it's the snippet search engines show for public repos.

If you forgot during creation, you can fix it from the repo's main page: click the ⚙ icon next to **About** in the right sidebar, type the description, save. Takes ten seconds.

### 4. Copy the scaffold

This `.github` repo ships a starter folder at [`repo-skeleton/`](https://github.com/internet-and-sons/.github/tree/main/repo-skeleton). Copy its contents into your new repo's root and replace the `{{placeholders}}` (repo name, one-line description). The five docs:

- `README.md` — what the repo is, in two or three lines.
- `CLAUDE.md` — the project context Claude Code auto-loads. Hard rules, dispatcher to the other docs.
- `CONTRIBUTING.md` — the repo-specific layer. Top-line points at the org-wide rules; the rest is yours.
- `TODO.md` — pending work, deferred decisions, done log.
- `LEARNINGS.md` — non-obvious gotchas you've discovered.

Plus, **for public repos only**, copy `LICENSE-MIT` to the repo root as `LICENSE` and update the year and copyright holder. Or pick a different OSI-approved license if the project calls for it.

The placeholders walk you through what each section is for. None of these need to be perfect on day one — they grow with the repo.

### 5. First commit, first PR

Push the scaffold to `main`. Then branch off, fill in your repo-specific content, open a PR against `main`, merge. From here on every change goes through a PR — see [`CONTRIBUTING.md`](https://github.com/internet-and-sons/.github/blob/main/CONTRIBUTING.md).

### 6. Pre-commit hook (optional but recommended)

If your repo will ship plugin manifests, schema files, version-locked tooling, or anything else where two files have to agree on the same value, drop a `.githooks/pre-commit` plus a small Python or shell script that checks the invariant. Cheap to set up; saves drift bugs that are otherwise easy to merge by accident.

## Help

Open an issue on the relevant repo, or reach out via [internetandsons.com](https://www.internetandsons.com). For anything sensitive (security, client work), email is better than a public issue.
