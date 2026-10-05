# The Agentic Enterprise Blueprint

## A reference architecture for operating and governing agents at enterprise scale

Enterprise AI is moving from assistants that produce an answer to agents that retrieve sensitive information, choose tools and change business systems. A customer-service agent may update a case, an embedded SaaS agent may change a workflow, and a custom agent may coordinate several models and APIs. Once an agent can act, architecture has to govern the complete path from a person's intent to the destination outcome.

Large enterprises already have several of these paths. Productivity copilots, SaaS agents, data-platform assistants and custom agents arrive with different identity models, policy controls, tool interfaces, logs and administration consoles. If each team solves those concerns inside its own product, the enterprise cannot consistently answer who authorized an action, which policy was enforced, whether the destination accepted it, or how the authority will be withdrawn.

The leadership decision is larger than selecting a model or agent framework. Financial-services, healthcare and other regulated enterprises need a shared architecture that identifies what must be common, what may remain federated, where controls execute and what evidence survives across vendor and business-unit boundaries.

**This blueprint defines eleven logical ownership planes and connects them through three operational paths: serve, decide and protect, and observe and prove.** It lets domains build useful agents without rebuilding identity, policy, evidence and recovery for every implementation.

> Build enterprise AI as a platform of owned capabilities: buy useful substrate, own the seams and evidence, and build the agents and workflows that differentiate the business.

Read the figure as three operational contracts. **Serve** handles live work. **Decide and protect** supplies current policy and revocation to the boundaries in that live path. **Observe and prove** joins runtime signals with destination-confirmed outcomes so evaluation, recovery and accountability use the same action identity.

![Three runtime paths connect live agent work, distributed control and durable evidence](diagrams/02-three-runtime-paths.svg)

The separation is operational. Live work, policy distribution and evidence have different latency, integrity and failure requirements. Approved low-risk work may continue from valid signed state during a control-plane outage, while revocation uses a faster restriction path. A successful trace cannot substitute for proof that a consequential action reached its destination.

## The decisions this architecture makes visible

Before choosing products, an executive team should settle five decisions:

1. **Topology:** start centrally, or use hub-and-spoke delivery when domain scale and release demand justify federation?
2. **Mediation:** which model, context, tool and agent-to-agent boundaries must be enterprise-controlled, and how will embedded SaaS agents be registered and observed?
3. **Control separation:** which decisions are authored centrally, and which signed state must be evaluated locally so serving survives a control-plane outage?
4. **Sourcing:** what should be bought, configured, reused or built in each plane, and which interfaces remain enterprise-owned?
5. **Evidence and accountability:** who owns each agent, policy, data product, tool and recovery decision, and what evidence must exist before authority expands?

Selecting an agent framework answers only part of these questions.

## Eleven logical ownership planes

![The eleven logical ownership planes of the Agentic Enterprise Blueprint](diagrams/01-eleven-planes.svg)

The planes are responsibilities, not eleven required products or a build sequence. One platform may implement several planes; one plane may run in several clouds or business units. Keep the boundaries explicit so ownership, interfaces and failure behavior remain visible.

| Plane | Owns | Accountable leadership |
|---|---|---|
| **Experience** | Channels, user identity, approvals and handoff | Product and channel leaders |
| **Agent** | Runtime, harness, orchestration, sessions and durable work | Agent platform engineering |
| **Intelligence** | Model access, routing, catalog, inference and lifecycle | AI platform and model engineering |
| **Knowledge & Context** | Permission-aware retrieval and task-specific context assembly | Knowledge-serving platform and domain owners |
| **Data** | Contracted knowledge graphs, semantic metrics, retrieval indexes, lineage and source data | Data-product owners |
| **Tool & Integration** | MCP services, APIs, events, legacy bridges and agent federation | Integration platform and domain API owners |
| **Control** | Registries, policy decisions, budgets, configuration and revocation | Enterprise AI platform owner |
| **Trust & Security** | Agent identity, delegated credentials, guardrails, sandboxing, egress and DLP | CISO and platform security |
| **Governance & Assurance** | AI inventory, risk tiering, impact assessment and protected evidence | AI governance, risk and audit |
| **AgentOps** | Traces, evaluation, feedback, release gates and incident response | AI reliability and evaluation owners |
| **Infrastructure & Deployment** | Cloud, hybrid and sovereign footprints, cells, landing zones and compute | Cloud and infrastructure engineering |

Domain leaders remain accountable for the actions their agents take. Centralizing a platform capability does not centralize every business decision.

## Four operating rules

1. **Treat the platform as a product.** Builders, operators, risk teams and domain owners need supported capabilities, owners and service objectives. A slower managed path will be bypassed.
2. **Author centrally and enforce locally.** Distribute signed, versioned state to model, context and action boundaries. Define freshness, revocation and fail-safe behavior by risk tier.
3. **Offer paved roads, then federate on evidence.** Begin with supported templates that include identity, gateways, evaluation and recovery. Move to hub-and-spoke delivery when demand, domain obligations or release cadence justify it.
4. **Own open, versioned seams.** Products and model providers remain replaceable only when contracts, conformance tests, evidence export and exit behavior belong to the enterprise.

Buying implementation does not transfer accountability. For each required capability, compare products and custom work against the same interface, service, control, operating-cost and exit criteria. The enterprise still owns business meaning, identity mapping, policy, acceptance, recovery and the decision to expand or stop.

## Prove one complete path before building a platform program

Choose one bounded workflow with an accountable business owner and a measurable baseline. Connect the minimum complete path: identity, one runtime, one model route, one published knowledge source, one mediated action, tracing, evaluation and recovery.

The first increment should demonstrate:

- the destination can attribute the person, agent and authorized action;
- context, model and action boundaries enforce current signed state;
- a timed-out write can be reconciled without blind repetition;
- revocation reaches every applicable boundary and work in flight has an owner;
- evidence identifies the policy, model, context, tool, approval and outcome versions;
- workflow benefit remains after platform consumption, review, exception and recovery effort.

Turn the successful path into a reusable template and onboard a second agent from another team. Federate when central demand becomes a constraint, while retaining one inventory, common identity, an enterprise policy floor, portable traces and attributable cost.

Useful platform measures include time to first controlled release, adoption of supported paths, enforcement-point coverage, platform-added latency and cost, evaluation escape rate, time to restrict, unresolved reconciliation work and duplicate connectors or credentials retired. Connect them to the funded workflow outcome; a technically successful agent that does not improve that outcome should be narrowed or stopped.

## Architecture detail and review

[Architecture detail](architecture.md) contains plane contracts, the 13-step runtime sequence, control-plane failure behavior, the reference deployment, decision rights, build-versus-buy criteria and failure scenarios.

Use its review questions before approving an implementation: Can any agent bypass a managed model, context or tool boundary? What continues during a control-plane outage? How does revocation reach every enforcement point? Which identity reaches the destination? Who reconciles uncertain writes? Can the enterprise reconstruct a consequential action? What changes when a provider is replaced?

## How this connects to the portfolio

This blueprint is the enterprise map. Three companion papers turn specific decisions into operating guidance:

- [**Earned Autonomy**](https://github.com/appliedgenai/earned-autonomy) defines permission per business action and shows how evidence, evaluation, restriction and recovery support an owner's decision to expand or reduce authority.
- [**From Intent to Production**](https://github.com/appliedgenai/intent-to-production) connects intent, specifications, enterprise knowledge, task context, execution, control and evidence for employee-led coding agents, delegated tasks, multi-agent delivery cells and AI software factories.
- [**Data Products for the Agent Economy**](https://github.com/appliedgenai/agent-data-products) treats knowledge graphs, semantic metrics and retrieval/vector indexes as governed products for many agents.

The models answer different questions. The blueprint defines enterprise capability and ownership boundaries. Earned Autonomy decides what an action may do. Intent to Production governs how software work moves. Data Products governs how reusable enterprise meaning reaches agents.

## About the book and author

This guide is adapted from Chapter 2 of the working manuscript for Mohit Mittal's upcoming book, *The Agentic Enterprise: Patterns and Reference Architectures for Enterprise AI Adoption*. See [BOOK.md](BOOK.md) for its structure and intended reading paths.

Mohit Mittal is a Chief Architect with 22+ years of experience in enterprise architecture, distributed systems and AI-enabled platforms. At Chegg, he led product, data and AI architecture for a platform serving millions of paying subscribers; his work included production LLM/RAG capabilities and agentic workflows. In healthcare, he has defined target-state architecture for a multi-tenant, AI-native EMR platform incorporating governed agent workflows, policy enforcement and auditability.

This is an independent reference architecture. Organizations should validate its boundaries, service objectives and sourcing decisions against their workloads, risk obligations and existing platforms. Primary references and claim boundaries are in [SOURCES.md](SOURCES.md). Content is available under [CC BY 4.0](LICENSE.md).
