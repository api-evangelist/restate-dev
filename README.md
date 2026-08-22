# Restate (restate-dev)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Restate is a durable execution platform for building resilient distributed applications, microservice orchestration, durable workflows, stateful services, and AI agents. Founded by Apache Flink and Apache Kafka veterans (Stephan Ewen, Igal Shilman, Till Rohrmann), Restate ships a single-binary Rust runtime that journals every step of handler execution so code survives crashes, restarts, and infrastructure failures. The platform exposes an Ingress API on port 8080 for HTTP invocation of services, virtual objects, and workflows (with idempotency keys, async /send semantics, and delayed invocations) and an Admin API on port 9070 for deployment registration, service introspection, invocation control, subscriptions, and cluster health. Official SDKs target TypeScript, Java/Kotlin, Python, Go, Rust, and Ruby, with first-class integrations for AWS Lambda, Cloudflare Workers, Deno Deploy, Vercel, and Kubernetes via the restate-operator. Restate Cloud is the managed offering with SOC 2 Type I compliance, enterprise SSO (Okta, Google Workspace, Azure AD), HIPAA BAAs, and an in-preview client-side journal encryption feature.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/restate-dev/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags

 - AI Agents, Durable Execution, Durable Workflows, Event-Driven, Kafka, Microservice Orchestration, Orchestration, ProCode_API_Composition, Resilience, Sagas, Self-Hosting, Service Protocol, State Machines, Stateful Services, Step Functions, Virtual Objects, Workflows, XState

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## APIs

### Restate Admin API
The Restate Admin API is the HTTP control plane for a running Restate Server, exposed by default on port 9070. It manages service deployment registration, lists and introspects services and handlers, controls invocations (cancel, kill, pause, resume, restart, purge), manages Kafka and event subscriptions, queries system state via embedded SQL, and reports cluster health and version.

**Human URL:** [https://docs.restate.dev/operate/clients](https://docs.restate.dev/operate/clients)

- [Documentation](https://docs.restate.dev/operate/clients)
- [API Reference](https://docs.restate.dev/references/admin-api)
- [GitHub Repository](https://github.com/restatedev/restate)

### Restate Ingress API
The Restate Ingress API is the HTTP data-plane for invoking services, virtual objects, and workflows running on Restate Server, exposed by default on port 8080. Requests follow the path conventions `/{ServiceName}/{handler}`, `/{VirtualObject}/{key}/{handler}`, and `/{Workflow}/{workflowId}/run` with JSON bodies. Append `/send` for fire-and-forget invocations, pass `?delay=` for scheduled invocations, and use the `Idempotency-Key` header for at-most-once semantics (responses cached 24 hours).

**Human URL:** [https://docs.restate.dev/invoke/http](https://docs.restate.dev/invoke/http)

- [Documentation](https://docs.restate.dev/invoke/http)
- [GitHub Repository](https://github.com/restatedev/restate)

### Restate Service Protocol
The Restate Service Protocol is the wire protocol Restate Server uses to communicate with handler endpoints implemented in any official SDK. It journals every side-effect (durable steps, RPCs, state reads/writes, sleeps, awakeables) so handlers can be replayed deterministically and resume from the exact step they were on when an infrastructure failure occurred.

**Human URL:** [https://docs.restate.dev/develop/sdks](https://docs.restate.dev/develop/sdks)

- [Documentation](https://docs.restate.dev/develop/sdks)
- [GitHub Repository](https://github.com/restatedev/sdk-shared-core)

## Common Properties

- [Portal](https://restate.dev)
- [Documentation](https://docs.restate.dev)
- [Getting Started](https://docs.restate.dev/get_started/quickstart)
- [Quickstart](https://docs.restate.dev/get_started/quickstart)
- [Tutorial](https://docs.restate.dev/get_started/tour)
- [SDK](https://docs.restate.dev/develop/sdks)
- [CLI](https://docs.restate.dev/operate/clients)
- [Pricing](https://restate.dev/pricing)
- [Cloud](https://restate.dev/cloud)
- [Blog](https://restate.dev/blog)
- [Use Cases](https://restate.dev/use-cases)
- [Careers](https://restate.dev/careers)
- [Team](https://restate.dev/team)
- [Contact](https://restate.dev/contact)
- [Terms of Service](https://restate.dev/terms-and-conditions)
- [Privacy Policy](https://restate.dev/privacy)
- [Imprint](https://restate.dev/imprint)
- [Login](https://cloud.restate.dev)
- [Sign Up](https://cloud.restate.dev)
- [GitHub Organization](https://github.com/restatedev)
- [llms.txt](https://docs.restate.dev/llms.txt)
- [Agent Skills](https://github.com/restatedev/skills)

## Features

- **Durable Execution** — Restate journals every handler step so code survives crashes, restarts, and infrastructure failures and resumes exactly where it left off.
- **Virtual Objects** — Stateful, single-writer addressable entities with built-in key-value state and exclusive concurrency for safe stateful services.
- **Workflows** — Long-running, durable workflow handlers with deterministic replay, sleeps that can span months, and external signal awakeables.
- **Sagas and Compensations** — First-class patterns for compensating side-effects across distributed transactions with guaranteed cleanup paths.
- **Durable Promises and Awakeables** — External-event integration where workflows pause for human input, webhooks, or asynchronous callbacks without losing state.
- **Kafka Event Subscriptions** — Subscribe Restate handlers to Kafka topics so events are turned into durable, exactly-once handler invocations.
- **Idempotent HTTP Invocations** — `Idempotency-Key` header makes any Ingress invocation safe to retry, with responses cached for 24 hours.
- **Delayed and Scheduled Invocations** — Schedule invocations into the future with `?delay=` or use Restate as a cron substitute for durable timers.
- **Embedded SQL Introspection** — Query journal, invocation, service, and state metadata over an embedded Apache DataFusion SQL engine for live introspection.
- **Single-Binary Distributed Server** — A single Rust binary that runs single-node for development and scales to a multi-node cluster with embedded RocksDB and Raft.
- **Restate Cloud** — Managed Restate clusters with SOC 2 Type I, enterprise SSO (Okta, Google Workspace, Azure AD), HIPAA BAAs, and tunneling.
- **Client-Side Journal Encryption** — Developer-preview feature that encrypts journal entries with customer-owned keys before they reach Restate Cloud.
- **Web UI and CLI** — First-party Web UI and `restate` CLI for inspecting invocations, registering deployments, and managing services.

## Use Cases

- **Microservice Orchestration** — Coordinate multi-service business transactions with automatic retries, compensation, and timeout handling using durable handlers.
- **Durable AI Agents** — Build agents that survive process crashes and replay tool calls deterministically, with integrations for OpenAI, LangChain, Pydantic AI, Vercel AI, Google ADK, and LiteLLM.
- **Step Functions and Workflow Engines** — Replace AWS Step Functions / Azure Durable Functions / hand-rolled state machines with code-first workflows in your language of choice.
- **Background Jobs and Async Tasks** — Run reliable background jobs with retries, idempotency, and scheduling without a separate queue and worker infrastructure.
- **Saga-Based Distributed Transactions** — Implement compensating-action sagas for cross-service operations like order fulfillment, payments, and inventory reservation.
- **Stateful Serverless APIs** — Combine virtual-object state with FaaS deployment on AWS Lambda, Cloudflare Workers, Deno Deploy, or Vercel for stateful serverless apps.
- **Event-Driven Workflows** — Subscribe handlers to Kafka topics so each event triggers a durable, exactly-once workflow invocation.
- **Human-in-the-Loop Approvals** — Pause workflows on awakeables that wait for webhook callbacks, signed URLs, or human approvals for arbitrary durations.

## Integrations

TypeScript SDK, Java/Kotlin SDK, Python SDK, Go SDK, Rust SDK, Ruby SDK, restate-operator (Kubernetes), AWS Lambda, Cloudflare Workers, Deno Deploy, Vercel, Kafka, XState, OpenAI Agents SDK, LangChain, Pydantic AI, Google ADK, Vercel AI SDK, LiteLLM, Langfuse, OpenTelemetry, PostgreSQL, Apache DataFusion, Knative.

## Solutions

- **Restate Server (Open Source)** — BSL-licensed single-binary Rust server, free for self-hosted use and the canonical runtime for the Restate Service Protocol.
- **Restate Cloud** — Fully-managed Restate clusters with SOC 2, enterprise SSO, HIPAA BAA support, and Cloud Tunnel client for hybrid deployments.
- **Restate On-Prem / BYOC** — Bring-your-own-cloud option for running Restate in customer-controlled AWS, GCP, or Azure accounts with Restate-managed operations.
- **Restate for AI Agents** — Targeted positioning for durable agent orchestration with integrations across major LLM and agent frameworks.

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
