# Jira → cloud agent → findings in the ticket (teaser)

## Current synthesis

The chain is doable with documented building blocks: Jira Automation (“Work item transitioned” → “Send web request”) starts the same QA workflow via GitHub `repository_dispatch`. Claude reads the ticket (Rovo MCP or REST) and writes a comment plus screenshots as attachments back. Not built, not tested.

## Claims and evidence

- A status change can trigger an automation, filterable to one status. [raw](../raw/2026-11-07-jira-cloud-agent-bausteine.md)
- An automation can send a web request with its own body and smart values. [raw](../raw/2026-11-07-jira-cloud-agent-bausteine.md)
- GitHub accepts `repository_dispatch` with a `client_payload` (204). [raw](../raw/2026-11-07-jira-cloud-agent-bausteine.md)
- Screenshots can be attached to the ticket via REST. [raw](../raw/2026-11-07-jira-cloud-agent-bausteine.md)

## Tensions and open questions

- The Rovo MCP server uses OAuth with an interactive login. Whether that works headless in CI is open. The REST API with an API token is the safe route.
- Header configuration of the web request action is not described on the docs page, only in community examples.
- A Jira token in the agent job contradicts the split “agent reads, report job writes”. Better: the report job writes to Jira.

## Sources

- [Building blocks Jira → cloud agent](../raw/2026-11-07-jira-cloud-agent-bausteine.md)
