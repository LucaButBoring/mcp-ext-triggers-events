# Triggers & Events Working Group

> ⚠️ **Experimental** — This repository is an incubation space for the Triggers & Events Working Group. Contents are exploratory and do not represent official MCP specifications or recommendations.

## Mission

The Triggers & Events Working Group exists to define how MCP servers proactively notify clients of state changes. Today, clients learn about server-side updates by polling or holding an SSE connection open. This WG will specify a standardized callback mechanism — webhooks or similar — that lets servers push notifications when new data is available, with defined ordering guarantees that hold across all transports.

See the full [Working Group Charter](https://modelcontextprotocol.io/community/triggers-events/charter) for scope, authority, and operations.

## Scope

### In Scope

- **Specification work:** SEPs defining the trigger/callback mechanism, subscription lifecycle, delivery semantics, and event ordering guarantees
- **Reference implementations:** SDK components demonstrating server-initiated notifications and client-side callback handling
- **Cross-cutting concerns:** Coordination with the Transports WG on transport-specific delivery behavior, and with the Agents WG where task completion notifications intersect with event triggers
- **Documentation:** Specification sections covering event-driven patterns and migration guidance from polling-based approaches

### Out of Scope

- Changes to the transport wire format or session model (owned by the Transports WG)
- General-purpose pub/sub infrastructure beyond what the MCP protocol requires
- Modifications to existing notification primitives (`notifications/resources/updated`, `notifications/tools/list_changed`, etc.) that do not relate to proactive server-initiated delivery

## Related Groups

| Group | Overlap |
| :--- | :--- |
| Transports WG | Delivery and ordering guarantees depend on transport capabilities; callback semantics must be coherent across stdio, Streamable HTTP, and future transports |
| Agents WG | [SEP-1686 (Tasks)](https://github.com/modelcontextprotocol/modelcontextprotocol/issues/1686) identifies webhook-style task completion notifications as a future consideration; this WG owns that mechanism |

## Leadership

| Role | Name | Organization | GitHub |
| :--- | :--- | :--- | :--- |
| Lead | Clare Liguori | Amazon Web Services | [@clareliguori](https://github.com/clareliguori) |
| Lead | Peter Alexander | Anthropic | [@pja-ant](https://github.com/pja-ant) |

## Repository Contents

This repository will hold proposals, reference implementations, and experimental findings as the WG's work progresses. See [CONTRIBUTING.md](CONTRIBUTING.md) for how to participate.
