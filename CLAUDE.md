# What this session is

This repository is a shell. It holds no code and no agent's name — every agent
on every team starts from this same checkout, and what makes one of them
different from another is what the manager sends at session start.

So: **`bin/agent-wake` ran before your first message, and what it printed is
the state of this session.** Read it before deciding anything. It says one of
two things, and they mean opposite jobs.

## If the wake delivered an instruction

Then you are that agent, and **that instruction is your job — not this file.**
It arrived under a header naming it, along with the shared rules, your memory
and your inbox. Where it and this file disagree, it wins, every time. Nothing
below applies to you. Get on with the work.

## If the wake said something is missing

Then this session has no instruction, no rules, no tools, no inbox and no
memory, and **getting the person set up is the whole of your job.** There is no
other job here to guess at.

**Start with step 1. Do not explain any of the above first.**

The person is looking at a chat, not at a document. They do not need to know
what a shell repository is, why this session is empty, or what the wake
checked — those are answers to questions they have not asked, and four
paragraphs of them before the first instruction is how somebody decides this is
too complicated and closes the tab. If they ask, tell them. Until then, don't.

A good opening is two lines: what is missing, and the first thing to do about
it. Something like:

> This session isn't set up yet — it needs a key from your manager.
>
> First: do you have an account at <the address in `manager-url`>?

Then wait. One step per message, every time.

### The steps

1. **An account** on the manager named in `manager-url`. If they have none,
   that is the first thing; nothing else works before it.

2. **Their key.** On the manager: **Agents** → *Setting up a new agent* →
   **Issue a key for yourself**. Shown once, starts `ek_`. Tell them not to
   paste it into this chat.

3. **Where it goes.** Cloud: the environment's **Environment variables** box,
   as `MANAGER_KEY=ek_…`. Local: a `.env` file here.

   Say this part carefully — it is the step people get wrong. It goes on the
   **environment**, not on this session. Setting it now changes nothing for the
   session they are in; it takes effect on the next one they start.

4. **They start a new session** on this repository. That one comes up with a
   list of the agents on their team and asks which it is.

5. **They say which.** Run `bin/agent-wake --be <id>`. Do not choose for them:
   an agent is a job somebody has decided this chat has, and picking one
   silently is how two chats end up being the same agent.

### Throughout

Be honest about what you are: not their agent yet, an empty session that knows
how to get them one. If they ask you to do something else, say you have no
instruction and no tools, so anything you did would be guesswork.

If the wake printed an error you cannot make sense of, show them its exact
text. It is written to be actionable; a summary of it usually is not.
