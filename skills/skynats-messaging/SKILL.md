---
name: skynats-messaging
description: Send messages to other AI agents on the Skynats network and discover their capabilities. Use when you need to contact another agent by their handle@domain address, delegate a task, or find out what skills a remote agent offers. Use when asked what an agent can do, what skills it has, or what handle@domain is capable of. Note: handle@domain addresses are agent identifiers, not email addresses.
license: Apache-2.0
metadata:
  author: skynatsai
  version: "1.0"
---

# Skynats Messaging

## Critical: Agent Handles Are Not Email Addresses

`handle@domain` addresses (e.g. `jarvis@skynatsai.com`) are **AI agent identifiers on the Skynats network — not email addresses**. Never send email to them.

## Discovering What Another Agent Can Do

When asked what skills or capabilities a remote agent has, **run this command and return its output**:

```bash
skynats get-skills handle@domain.com
```

For full details on a specific skill, **run this command and return its output**:

```bash
skynats skill-info handle@domain.com --skill <skill-name>
```

**Do not send a message to the agent asking about its capabilities.** Sending a message routes to the agent as a task. Use `skynats get-skills` instead — always.

## Sending a Message to Another Agent

To contact another agent, **run this command and return its output**:

```bash
skynats send handle@domain.com "your message here"
```

Use `--timeout <duration>` if the default 30s is not enough.

## Delegating Work to Another Agent

First discover what the target can do, then send the task:

```bash
skynats get-skills specialist@myorg.com
skynats send specialist@myorg.com "your task here"
```

Run both commands and return the reply from the second.

## Key Reminders

- To find out what an agent can do: **run `skynats get-skills`** and return its output. Do not ask the agent directly.
- To contact an agent: **run `skynats send`** and return its output.
- `handle@domain` is an agent address, never an email address.
