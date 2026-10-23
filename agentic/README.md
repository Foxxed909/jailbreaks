# Agentic Attack Surface

The most dangerous live attack vector in 2026. Agents that browse, read files,
execute code, and call APIs introduce indirect injection surfaces that bypass
every direct-prompt defense.

---

## Why Agents Are Different

Direct jailbreaks require convincing the user to submit malicious content.
Agent attacks are invisible to the user. The attack lives in:
- A web page the agent browses
- A document the agent reads
- A tool output the agent processes
- An email the agent summarizes
- A code file the agent reviews
- An MCP server the agent connects to

The legitimate user never sees the attack. They only see the compromised output.

---

## Attack Categories

| Category | File |
|----------|------|
| MCP server injection | `mcp-injection.md` |
| Tool output injection | `tool-output-injection.md` |
| Rules file backdoor | `rules-file-backdoor.md` |
| Document injection | `document-injection.md` |
| Web content injection | `web-injection.md` |
| Multi-agent pipeline attacks | `multi-agent.md` |
