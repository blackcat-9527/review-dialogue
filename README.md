# Shared Review Dialogue

A Codex skill for an author and reviewer to exchange evidence-based feedback through a shared Markdown log.

## Start a review

With the artifact and workspace established:

```text
Use $review-dialogue as the reviewer.
```

The reviewer automatically creates a log in its current workspace when no path is supplied. It reuses a matching existing log and provides its absolute path for the author.

In the author chat:

```text
Use $review-dialogue with [log path] as the author.
```

Continue either chat with `Continue review` or `繼續審閱`. Chats are resumed by the user; the skill does not automatically send messages or launch another agent.

## Install

Copy `SKILL.md`, `agents/`, and `assets/` into `~/.codex/skills/review-dialogue/`. These are the skill files; this repository contains no project reports or review history.

The skill preserves versions, records source and validation limits, and closes resolved reviews without generating unnecessary revisions. Instructions are in English; replies and artifacts follow the user's language preferences.
