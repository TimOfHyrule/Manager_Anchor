# An agent's shell

This is the whole repository an agent needs. It has no code, no agent's name in
it, and nothing to edit — it is the same checkout for every agent on every team,
which is the point.

## Setting one up

1. Start a Claude Code session on this repository.
2. Put two things in that environment:

   ```
   MANAGER_URL=https://your-manager
   MANAGER_KEY=ek_…      your own key, from the manager's Agents page
   ```

3. The session starts and prints the agents on your team. Say which one this
   chat is. It runs `bin/agent-wake --be <id>` and that is the setup finished.

The same key does every agent on your team. It is yours rather than the team's
— a teammate issues their own, so losing a laptop or leaving costs one key
rather than everybody's. Which chat is which agent is remembered by the
manager, not by anything here.

## Why there is nothing in here

Everything an agent works from is fetched at session start, from the manager:
its instruction, the shared rules, the picture, its memory, its inbox, and the
tools. A copy in a repository is a copy that goes stale in one place while
looking maintained in every other — which happened, to a `bin/tama` that grew a
command in one agent's repository and never in the rest.

`bin/agent-wake` is the exception and has to be: the thing that fetches the
tools cannot itself arrive in them. It is small, it changes rarely, and the
manager's own copy is the original.

## What this is not for

An agent that owns a codebase. A chat that works on your repository has to be
started on your repository, and that one wants its own credential rather than a
yours — see **the long way** in the manager's `docs/AGENT-SETUP.md`.

## What your key can do

Claim to be any agent on your own team, and nothing on anybody else's. That is
what makes one key enough for all of them, and it is why revoking it stops
every chat of yours that has not been given an agent's own credential.
