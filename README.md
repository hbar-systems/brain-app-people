---
created: 2026-10-22
---

# People

A brain-app for BrainFoundry brains. Part of the base shelf.

Type a name.
It tells you who they are, what you last discussed and what is still open between you.
Everything comes from your brain's memory; nothing is invented.

## What it does

- Look up: two memory searches in parallel (the name, and the name with "conversation discussed last time"), de-duplicated, then one model call over the excerpts.
- The card shows who, how they relate to you, up to five things last discussed with date and source, up to five open threads, and a confidence tag.
- "What memory had" lists the raw excerpts (document, similarity, first 300 characters) so you can see the grounding.
- Add a note writes "About <name>: <note>" to semantic memory; the next look up includes it.
- Ask about them answers a question using the card as context.
- If memory has nothing on a name, it says so, and a note is how to start.
- The last card per name is kept on this device and shown at once, with a Refresh.
- The last 12 names looked up appear as chips.

## Permissions, and why

- `memory.read` (semantic and episodic, read): to search for the person.
- `memory.write` (semantic, append): to save a note you add.
- `llm.invoke`: to turn excerpts into the card and answer questions, over the layers above.

No network access, no tasks, no mail.
Excerpts go into the prompt fenced as untrusted reference data.

## Try it

1. Push this repo to `https://github.com/hbar-systems/brain-app-people`.
2. On your brain, open Apps and install People from that repo.
3. Open People, type a name, press Enter.
4. Add a note and look the name up again.

Power-user path: clone into `brain-apps/people/` on the brain and `POST /apps/install {"path": "brain-apps/people"}`.

AGPL-3.0.
