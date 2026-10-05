# Sources and claim boundaries

This repository presents an independent architecture proposal adapted from the working manuscript for Mohit Mittal's upcoming book, *The Agentic Enterprise*. The sources below support the standards and risk-management concepts used at the seams. They do not validate the complete reference architecture or imply that different vendor implementations are interchangeable.

| Source | Use in this guide |
|---|---|
| [C4 model](https://c4model.com/) | Vocabulary for system-context, container, component and dynamic architecture views. |
| [Model Context Protocol — 2026-07-28 release](https://blog.modelcontextprotocol.io/posts/2026-07-28/) and [specification](https://modelcontextprotocol.io/specification/) | Open protocol used as one candidate seam between agents and tools/data. Pin a protocol revision and test conformance. |
| [Agent2Agent protocol](https://github.com/a2aproject/A2A) | Open protocol for communication between independent, potentially opaque agent systems. It complements rather than replaces tool protocols. |
| [OpenTelemetry GenAI semantic conventions](https://github.com/open-telemetry/semantic-conventions-genai) | Shared vocabulary for traces and signals spanning inference, agents, tools, evaluation and MCP. Check stability and implementation support before standardizing attributes. |
| [OAuth 2.0 Token Exchange — RFC 8693](https://www.rfc-editor.org/rfc/rfc8693) | Standards basis for exchanging an initiating identity for a short-lived delegated token. A token exchange alone does not define business authorization. |
| [CloudEvents specification](https://cloudevents.io/) | Common event-envelope option for event-triggered agents and cross-platform event transport. |
| [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework) and [Generative AI Profile](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf) | Risk-management vocabulary and voluntary practices. AI RMF 1.0 is being revised; use the current framework and applicable legal obligations for each deployment. |
| [Claude Code setup](https://docs.anthropic.com/en/docs/claude-code/getting-started) and [CLI reference](https://docs.anthropic.com/en/docs/claude-code/cli-usage) | Primary-source examples of an interactive local coding-agent surface and a programmatic invocation mode. Enterprise controls still depend on the configured identity, environment, tools and review path. |
| [GitHub third-party coding agents](https://docs.github.com/en/copilot/concepts/agents/about-third-party-coding-agents) | Primary-source example of asynchronous task delegation that produces a pull request for human review. Preview status and enterprise policy must be checked at adoption time. |
| [Kiro Web](https://kiro.dev/docs/web/) and [Kiro autonomous mode](https://kiro.dev/docs/web/autonomous-mode/) | Primary-source examples of collaborative, specification-led and autonomous work in isolated cloud sessions that can produce pull requests. Product behavior is an implementation candidate, not the architecture itself. |

## Proposal versus evidence

- The eleven-plane structure, three paths, ownership model, sourcing defaults and deployment shape are architectural proposals.
- Service objectives, freshness windows and cell boundaries must be set from an organization's risk tier and workload evidence.
- The guide contains no claim that this complete platform has been deployed by the author or that it produces a particular financial return.
- Product capabilities, protocol versions and regulations change. Recheck them at selection and deployment time.
