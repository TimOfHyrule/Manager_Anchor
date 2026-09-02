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
memory, and **helping the person finish setting it up is the whole of your job
for this session.** Do not start any other work, and do not guess at what an
agent here is supposed to do — you have not been told.

The person on the other end has just selected this repository and may never
have done any of this. Walk them through it, one step at a time, waiting after
each. Do not paste all of it at once.

### The steps

1. **Do they have a manager account?** `manager-url` in this repository says
   which manager this is. If they have no account there, that is the first
   step: open it, sign up, and come back. Nothing else works until then.

2. **Get their key.** On the manager: **Agents** page → *Setting up a new
   agent* → **Issue a key for yourself**. It is shown once and starts `ek_`.
   Tell them not to paste it into this chat — it goes in one place only.

3. **Where it goes.** In a cloud session (claude.ai/code): the environment's
   **Environment variables** box, as `MANAGER_KEY=ek_…`. Locally: a `.env`
   file beside this README.

   Say this part plainly, because it is the step people get wrong: it goes on
   the **environment**, not on this one session. A session copies those values
   once at startup, so setting it now does nothing for the session they are
   already in — they set it, then start a new session, and it is done for
   every session after that.

4. **They start a new session on this repository.** That one will come up with
   a list of the agents on their team, and ask which one it is.

5. **They say which.** Run `bin/agent-wake --be <id>` with the id they chose.
   Do not choose for them: an agent is a job somebody has decided this chat
   has, and picking one silently is how two chats end up being the same agent.

### While you are doing that

Be honest about what you are. You are not their agent yet — you are an empty
session that knows how to get them one. If they ask you to do something else,
say that you have no instruction and no tools, and that whatever you did would
be from guesswork rather than from anything they have set up.

If the wake printed an error you cannot make sense of, show them the exact
text rather than paraphrasing it. It is written to be actionable, and a
summary of it usually is not.
