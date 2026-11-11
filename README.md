# ThinClaw

**A multi-user, agentic AI assistant you talk to over chat.**

ThinClaw plans, uses tools and gets things done for you: everyday tasks across your connected services, code it writes and runs for you, and work it keeps doing on a schedule while you're away. Each user has their own isolated workspace, their own encrypted credentials and their own choice of model.

- **Status:** in active development, private beta. **Closed source.**
- **Built by:** Fortune Max-Eguakun, solo, March 2026 to now.

> This repository is a public overview for people evaluating my work. It contains no source code.

---

## What it does (at a glance)

- **Agentic tool use.** Multi-step tasks from a single message, with live progress and instant cancellation.
- **Integrations.** Connects to everyday services through a plugin system that users switch on or off.
- **Code execution.** A personal, persistent workspace where the assistant can write and run code for you.
- **Scheduling.** Recurring and one-off tasks that start a full agent run, not just a reminder.
- **Multi-model.** Works across several major LLM providers.
- **Human in the loop.** Sensitive or irreversible actions wait for the user's explicit approval.
- **Payments and a web dashboard** for managing the account.

## Engineering principles

- **Isolation by default.** Every user's code runs in its own sandbox with per-user resource limits. A runaway job only ever affects its owner.
- **Fail closed.** If isolation isn't available, code doesn't run. Malformed or truncated tool calls are refused, never half-executed.
- **Untrusted code is treated as untrusted.** Third-party extensions get least-privilege permissions and are checked before their first run.
- **Secrets stay secret.** Credentials are encrypted at rest with authenticated encryption, kept out of the conversation, and redacted from stored logs.
- **Reliable automation.** Scheduled runs execute exactly once, survive restarts and never overlap.
- **Provider-agnostic.** One agent loop across model providers, with automatic fallback on errors and rate limits.
- **Multi-tenant access control.** Role-based permissions, quotas and per-role capabilities.

## By the numbers (November 2026)

| | |
|---|---|
| TypeScript | ~38,000 lines |
| Tests | 136 test files, ~840 test cases |
| Commits | 500+ since March 2026 |
| Plugins | 19 first-party |

## Tech stack (high level)

TypeScript · Node.js · SQLite · React · Docker. Linux sandboxing. LLM APIs from multiple providers.

## Source code

ThinClaw is closed source while it is in active development. I'm happy to walk through the architecture, code and trade-offs in an interview. You can reach me via [fme.dev](https://fme.dev) or [LinkedIn](https://www.linkedin.com/in/fortune-max-eguakun/).

## License

© 2026 Fortune Max-Eguakun. All rights reserved. This repository is documentation only. No license is granted to use, copy, modify or distribute ThinClaw or any part of it.
