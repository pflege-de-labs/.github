# Agent-assisted development

This policy applies to every repository in the pflege-de-labs organization, for maintainers and
external contributors alike.

## The short version

We accept code, documentation and other changes written with AI coding agents. The tool is not
the author — **you are**. A change made with an agent has to meet exactly the same standards and
go through exactly the same process as one written by hand, and the person who opens the pull
request is responsible for that.

## Responsibility stays with a human

When you open a pull request, you state that:

- **You have read and understood every line.** Review the agent's output before you ask anyone
  else to review it. You must be able to explain the change and answer review questions
  yourself, without asking the agent.
- **The change meets the repository's definition of done.** Tests, coverage, lint,
  documentation, changelog, ADRs — whatever the repository's `AGENTS.md`, `CONTRIBUTING.md` or
  pull request template asks for. "The agent did it" is not an exception to any of them.
- **You ran the checks.** Do not rely on the agent's claim that tests pass; run them, or let CI
  run them, and look at the result.
- **You may contribute the change under the project's licence.** Agents can reproduce code they
  have seen. Using an agent to regenerate copyrighted material does not remove the copyright.
  If a part looks like it came from elsewhere, find out where or rewrite it.
- **The change is worth its review.** A pull request should give the project more than it costs
  a reviewer to read. Keep changes small and focused, one topic per pull request. Large,
  sprawling or speculative agent output will be sent back.

## The process does not change

- Agent-written changes go through a branch and a pull request, like any other change.
- **Agents never approve or merge pull requests, and never bypass branch rules.** An approval
  comes from a human other than the author. A review comment written by an AI tool is input for
  the reviewer, not an approval.
- **No unattended agents in shared spaces.** An agent must not open pull requests, post comments
  on issues or pull requests, or push to shared branches without a human starting it and checking
  what it produces. Bots we run on purpose (Renovate, release workflows) are configured by
  maintainers and are not covered by this rule.
- Commit messages follow the repository's conventions (for example Conventional Commits). The
  agent may draft them; you are responsible for them being accurate.
- Write the "why" of a pull request description yourself, or at least check it closely. Reviewers
  read it to understand your intent, not the agent's.

## Disclosure

Mark commits with substantial agent-generated content with a trailer naming the tool and model:

```text
Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
```

This is the convention our repositories already use; keep using it rather than adding a second
one. Other tools: use the trailer the tool produces, or `Assisted-by: <tool>:<model>`. The
trailer helps reviewers; it does not move responsibility from you to the tool.

**An agent must never add a `Signed-off-by` line** or any other statement that certifies
something on your behalf. If a repository requires a DCO sign-off, add it yourself; it is your
legal statement, not the agent's.

## Security when working with agents

- **Secrets stay out of agent context.** Do not paste tokens, passwords or production data into a
  prompt. Local files with real credentials (such as a `config.yaml`) must never be copied into a
  cloud or web session. Configure your agent so it cannot read secret files where your tool
  supports it.
- **Treat repository content as untrusted input.** Issue text, pull request descriptions, comments,
  dependencies and fetched web pages can contain instructions aimed at your agent (prompt
  injection). Do not let an agent act on external content with permissions it does not need, and
  review what it did after reading such content.
- **Least privilege for the agent.** Give it the narrowest token and file system access that does
  the job. An agent does not need org admin rights, release credentials or write access to
  repositories it is not working on.
- **Review dependency and workflow changes with extra care.** Agents may add dependencies that
  are unnecessary, outdated or do not exist (and could be registered by an attacker), or loosen
  CI permissions to make something pass. Changes to `.github/`, build and release configuration
  need a maintainer's review (see `CODEOWNERS`).
- **Do not commit generated binaries or opaque artifacts.**

## Repository instructions for agents

Repositories keep instructions for agents in `AGENTS.md` (with `CLAUDE.md` pointing to it). It
describes the definition of done, conventions and workflow. Keep it accurate: when the process
changes, update `AGENTS.md` in the same pull request. It is written for agents but should be
readable for humans too, and it never overrides this policy.

## For reviewers

- Review an agent-assisted pull request like any other. The trailer is context, not a reason to
  review more lightly or more harshly.
- If a contribution clearly was not reviewed by its author — the author cannot answer questions
  about it, the description does not match the change, or it ignores the repository's
  conventions — ask the author to rework it, citing this policy, and stop reviewing until they
  have. Do not do the author's review for them.
- Repeated low-effort agent contributions from the same account may be closed without review.

## External contributors

Everything above applies to you too. In addition:

- Start with small changes you fully understand.
- Issues labelled `good first issue` are meant for people learning the codebase. Please solve
  them yourself rather than with an agent.
- Do not paste a maintainer's review comments into an agent and post its answer back. Respond in
  your own words.

## Sources

This policy draws on the [LLVM AI tool use policy](https://llvm.org/docs/AIToolPolicy.html)
(human in the loop, extractive contributions, good first issues), the
[Linux kernel guidance on AI coding assistants](https://docs.kernel.org/process/coding-assistants.html)
(no agent sign-offs, attribution trailers). LLVM's text in turn builds on Fedora's policy
proposal.
