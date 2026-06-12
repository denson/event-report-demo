# Cyber Event Reports — demo

A small, self-contained demo of a cyber event-reporting service (stood up 2026-06-12, in active build).

- **`index.html`** — the feed: published reports on top (sortable, paginated), plus a tier of additional
  threats detected but not yet written up.
- **`<slug>.html`** — each event report: a multi-source knowledge-graph view with source-reliability
  tiering, reconciled conflicting claims, adjudicated **false alarms** (what is NOT part of the event),
  **dual severity** (AI-assessed + named-expert point-of-view), and a human-review banner.
- **`<slug>.json`** + **`events/index.json`** — the machine twins: each event as a structured card an
  agent can fetch, and the index the feed reads.
- **`.well-known/agent-card.json`** — an A2A AgentCard describing the service and its methodology.
- Report pages also expose **WebMCP** tools (`getEventReportCard`, `explainThisEvent`, `getFalseAlarms`)
  to in-browser agents, feature-detected so they no-op where unsupported.

Methodology (as it stands): watch RSS feeds to detect candidate events → supplement with Google Vertex AI
and other grounded searches to corroborate and fact-check (including the over-relating check) → auto-generate
the report → human expert review → publish. Diagrams by [ConceptViz](https://conceptviz.app/).

*Author: Denson Smith.*
