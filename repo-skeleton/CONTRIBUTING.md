# Contributing — {{repo-name}}

> **Org-wide rules:** [`internet-and-sons/.github/CONTRIBUTING.md`](https://github.com/internet-and-sons/.github/blob/main/CONTRIBUTING.md). PR template: [`PULL_REQUEST_TEMPLATE.md`](https://github.com/internet-and-sons/.github/blob/main/PULL_REQUEST_TEMPLATE.md). This file covers what's specific to {{repo-name}}.

Read `CLAUDE.md` first for the architectural picture and the safety rules. This file is the operational reference for actually making changes.

## Setup (per clone)

<!-- What does someone need to do once after cloning this repo to be able
     to work in it? Examples: install deps via uv sync, set OPENAI_API_KEY
     in .env, run `git config core.hooksPath .githooks`, run a one-off
     migration. Be concrete and step-by-step. -->

1. {{step}}
2. {{step}}

<!-- If your repo has a pre-commit hook, mention it here so contributors
     remember to enable it: -->
<!--
3. Enable the pre-commit hook (once per clone):
   ```
   git config core.hooksPath .githooks
   ```
   The hook checks {{what it checks}}; if it fails, {{what to do}}.
-->

## Workflow

<!-- The day-to-day flow of working in this repo. Whatever the most common
     contributor activity is, document it here as a numbered walkthrough.
     If your repo only has one common workflow, just describe that one. -->

{{Step-by-step description of the most common contributor workflow.}}

## Bumping a version

<!-- Delete this whole section if your repo doesn't ship versioned
     releases. Otherwise: which files carry the version, what bump levels
     mean (patch / minor / major), how the release flow works (tag, npm
     publish, update a registry pin, etc.). -->

{{If applicable: walk through the version-bump flow. Include: which
files agree on the version, what semver rules apply, how to tag and
push.}}

## What NOT to change without coordination

<!-- The "I'm about to do something with downstream effects — should I
     ask first?" list. Examples: renaming the package, changing a public
     API surface, moving a file something else references, changing a
     plugin pin URL. Things that are technically possible but would break
     downstream users or cross-repo contracts. -->

{{Bullet list of stable contracts other systems (or other people) depend
on. If you'd want to give someone a heads-up before changing something,
list it here.}}

## Help

{{Open an issue, or ask {{channel or person}}.}} Stuck > guessing.
