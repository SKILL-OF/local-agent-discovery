---
name: local-agent-discovery
description: Understand and apply local coding-agent session discovery from an office directory; use when identifying resumable Claude, Codex, or Copilot sessions without contacting them.
---

# Local agent discovery

An office is a working directory. Discovery answers which agent sessions were
started from that office; it is not contact, control, or permission to act as a
discovered agent.

## Procedure

1. Start from the named office directory, not a storage or tape-closet path.
2. Query a discovery tool for sessions whose recorded working directory belongs
   to that office.
3. Treat each result as metadata: tool type, canonical session identifier,
   normalized office path, and recency. A historical record does not prove the
   session is currently live.
4. Resolve any intended contact through that agent's native transport. For a
   remote agent, include a return address and require an explicit return-path
   acknowledgement.
5. Keep discovery, contact, and work mutation separate. Discovery alone never
   authorizes attachment, resume, stopping, credential access, or a task change.

## Tooling

Install or invoke a tool only when tool access is available. The current
implementation is
[TOOLS-OF/local-agent-discovery/AS/sesh-hound](https://github.com/TOOLS-OF/local-agent-discovery/tree/main/AS/sesh-hound).
It should support an office query such as `sesh-hound <office> --json`.

If the tool misses a known session, retain the smallest reproducible office
query and expected canonical id, then open a bounded discovery issue. Do not
work around the defect by treating storage paths as the public interface.
