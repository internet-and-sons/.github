# Learnings — {{repo-name}}

Non-obvious things you've discovered. Read before editing the parts of the repo where past gotchas have lived; future-you will thank past-you.

A "learning" worth writing down is something that:

- Cost real debugging time to figure out the first time.
- Isn't obvious from reading the code.
- Will bite the next person if they don't know it.

If a thing has those three traits, write it up. If it's just trivia, skip it.

## Format

For each learning, capture:

- **What you observed** (the symptom).
- **Why it happens** (the cause, once you understood it).
- **What to do** (the fix, or the rule for next time).

Keep entries short — a paragraph or two each. Long-form explanations belong in CLAUDE.md or in code comments. This file is the index to "stuff I wish I'd known."

## Example entry (delete this once you have real ones)

### Example: third-party API silently truncates payloads above 4KB

<!-- Replace this whole example with your first real learning. Keeping it
     here as a template until then. -->

**Observed:** Long messages sent to the API came back with the response built from a partial input — middle of the message simply gone. No error, no warning.

**Why:** The provider's gateway truncates request bodies at 4KB and processes whatever's left. Documented in a footnote on a status page, nowhere in the API docs.

**What to do:** Chunk anything over 3.5KB into multiple calls and stitch the responses. There's a helper in `lib/chunk.ts` — use it instead of writing it again.
