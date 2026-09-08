# Feature Flag Management System for Elisa Oyj

> A scalable feature flag management platform developed to enable safe release control, granular rollouts, and role-based access management without requiring full production deployment cycles.
> The implementation strictly complies with the **OpenFeature standard** for vendor-neutral, interoperable flag evaluation.
> **Note:** The source code is private under a client Non-Disclosure Agreement (NDA).

## Reference / Product Owner

> "Great job! I'm looking forward to getting the Feature Flag system integrated into our services soon."  
> — **[Santeri Auvinen](https://www.linkedin.com/in/santeri-auvinen-7234552/)**, Product Owner at Elisa Oyj

## Project Overview

In enterprise environments, managing application state across distributed services requires a centralized, secure control plane. This system was designed to solve three critical operational challenges:
- Decoupling software deployment from feature activation.
- Implementing fine-grained, role-based authorization for flag lifecycle changes.
- Providing visibility and lifecycle management for active, stale, and deprecated flag keys.

The solution comprises:
- **Core Engine & Backend (Go):** High-throughput evaluation API, relational data model, authentication, and scanner integrations.
- **Admin UI & Client (React + TypeScript):** Intuitive management interface for projects, flags, targeted rollouts, and tagging.

## Key Capabilities

- **Project-Scoped Flag Isolation:** Multi-project structure isolating configurations and permissions.
- **Role-Based Access Control (RBAC):** Hierarchical permissions defining full project administration (ADMIN), flag modification and toggling (EDITOR), and strictly read-only flag inspection (VIEWER).
- **Targeting & Progressive Rollouts:** Rule-based evaluations, context targeting, and percentage-based progressive delivery.
- **Automated Flag Hygiene:** Scanner integration to detect code usage, surface abandoned flags, and prompt deprecation.
- **Client Relay/Proxy:** Lightweight HTTP evaluation endpoints serving flag states directly to client applications via OpenFeature providers.
## Architecture & Tech Stack

| Layer | Technologies | Role |
|---|---|---|
| **Frontend** | React, TypeScript, Vite | Administration interface, modular UI components, responsive dashboards |
| **Backend** | Go, REST API (OpenAPI) | High-performance API, data validation, OpenFeature evaluation backend |
| **Database** | PostgreSQL | Relational persistence for flag definitions, audit logs, and projects |
| **Identity & Security** | Microsoft Entra ID | Enterprise identity management and SSO |
| **Infrastructure** | Docker, OpenShift (Kubernetes) | Containerized local development and scalable cloud orchestration |
| **Quality & CI/CD** | GitHub Actions, Vitest, React Testing Library, ESLint, Prettier | Automated CI/CD pipelines, component and unit test suites, static analysis, and code formatting |

## My Role & Key Contributions

### Initial Architecture & Prototype (Sprint 0)
- Designed and built the first functional end-to-end prototype: React Admin UI, React Demo Client, backend service, PostgreSQL database, and a `go-feature-flag` relay proxy.
- Established the integration flow connecting the management UI, database storage, and external evaluation services.

### Backend & Integrations (Go & PostgreSQL)
- Implemented core backend services in Go, managing multi-directional communication between the Admin API, the flag evaluation proxy, and client endpoints.
- Designed relational schemas and persistence queries in PostgreSQL.

### Frontend Engineering (React & TypeScript)
- Implemented the modal-based feature flag editor, managing dialog states, event propagation, and background scroll locking.
- Integrated UI workflows and indicators for obsolete/stale flags to surface deprecated flag keys for removal.
### Technical Quality & Delivery
- Conducted architectural code reviews focusing on structural consistency, API patterns, and maintainability.
- Managed branch integration and resolved multi-contributor Git merge conflicts across complex UI and backend updates.
- Refined technical backlog items into small, well-defined tasks and presented working increments in client sprint reviews.

## Teamwork & Scrum Delivery

The development was executed in an agile cross-functional team utilizing Scrum:
- **Sprint Cadence:** Bi-weekly sprints encompassing planning, daily standups, sprint reviews, and retrospectives.
- **Iterative Refinement:** Translating stakeholder epics into technical user stories, prioritizing backlog items according to client risk profiles.
- **Code Reviews:** Peer reviews covering architectural alignment, OpenFeature spec compliance, and test coverage before merging.

## Outcome

The project established a unified feature flag management baseline for Elisa Oyj, substantially mitigating deployment risk and streamlining continuous delivery pipelines across dependent teams.