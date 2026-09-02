# An agent's shell

The whole repository an agent needs. No code, no agent's name, nothing to edit —
the same checkout for every agent on every team, which is the point.

## Setting one up

1. **Start a Claude Code session on this repository.** You do not need to fork
   it; it is public and it is never written to.

2. **Put one variable in that environment.** On the web that is the cloud
   environment's **Environment variables** box; locally it is a `.env` file
   beside this README.

   ```
   MANAGER_KEY=ek_…
   ```

   The key is yours, from the manager's **Agents** page → *Setting up a new
   agent* → **Issue a key for yourself**. It is shown once.

   Set it on the ENVIRONMENT, not on one session: every session started
   afterwards copies it at startup, so you do this once and never again.

3. **Say which agent this chat is.** The session starts, asks the manager which
   agents are on your team, and prints the list. Answer, and it runs
   `bin/agent-wake --be <id>` for you. That is the setup finished.

The same key does every agent you set up. Which chat is which agent is
remembered by the manager, not by anything here — so a chat is wakeable from
the moment you choose.

`manager-url` holds the address of the manager this repository belongs to. Set
`MANAGER_URL` in the environment to point somewhere else; it wins.

## Why there is nothing in here

Everything an agent works from is fetched at session start, from the manager:
its instruction, the shared rules, the picture, its memory, its inbox, and the
tools. A copy in a repository is a copy that goes stale in one place while
looking maintained in every other — which happened, to a `bin/tama` that grew a
command in one agent's repository and never in the rest.

`bin/agent-wake` is the exception and has to be: the thing that fetches the
tools cannot itself arrive in them. It is small, it changes rarely, and the
manager's own copy is the original.

## When something is wrong

The wake never fails silently. If it cannot reach the manager, cannot prove who
it is, or gets no instruction, it says so in the session's first message and
keeps going — so a chat that has nothing is a chat that knows it has nothing,
and tells you. If a session starts and says none of that, it got what it needed.

## What this is not for

An agent that owns a codebase. A chat that works on your repository has to be
started on your repository, and that one wants the agent's own credential
rather than yours — see **the long way** in the manager's
`docs/AGENT-SETUP.md`.

## What your key can do

Claim to be any agent on your own team, and nothing on anybody else's. That is
what makes one key enough for all of them, and it is why revoking it stops
every chat of yours that has not been given an agent's own credential.
