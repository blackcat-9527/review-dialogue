# Shared Review Dialogue

A Codex skill for an author and reviewer to exchange evidence-based feedback through a shared Markdown log.

## Start a review

Choose the artifact you want reviewed, such as a report, slide deck, or code project. Both chats need to read and append to the same Markdown log and read the artifact. The author needs to save revisions where the reviewer can open them.

In the reviewer chat, identify the artifact and use this prompt:

```text
Use $review-dialogue as the reviewer.
```

The reviewer automatically creates a log in its current workspace when no path is supplied. It reuses a matching existing log and provides its absolute path for the author.

In the author chat:

```text
Use $review-dialogue with [log path] as the author.
```

If the chats run in different workspaces or environments, give each chat a path it can use to open the same log. Artifact paths can be relative to the log directory when both chats see the same folder layout. You can also supply an explicit path mapping. Separate clones or copies need reliable synchronization for each chat to see the other's changes.

Continue either chat with `Continue review` or `繼續審閱`. Chats are resumed by the user; the skill does not automatically send messages or launch another agent.

## Keep review logs private

Save actual review logs in a folder outside Git checkouts that both chats can access. If you need to keep a log in a clone of this repository, put it under the ignored `review-logs/` directory at the repository root. For any custom path inside a checkout, confirm Git ignores it with `git check-ignore -v -- <log-path>` before staging files.

## Install

Copy `SKILL.md`, `agents/`, and `assets/` into `~/.codex/skills/review-dialogue/`. These are the skill files; this repository contains no project reports or review history.

The skill preserves versions, records source and validation limits, and closes resolved reviews without generating unnecessary revisions. Instructions are in English; replies and artifacts follow the user's language preferences.
