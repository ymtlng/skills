---
name: scope-it
description: Convert product requirements or technical proposals into a codebase-aware implementation scope. Use before coding a feature, bug fix, integration, migration, or refactor to identify affected components, boundaries, dependencies, risks, tests, and the smallest viable implementation. Do not use to implement code.
---

# ScopeIt

Understand the change before changing the code.

## Mission

Turn approved requirements and technical proposals into an implementation-ready scope grounded in the existing codebase. Do not write implementation code.

## Evidence order

Use the strongest available sources in this order:

1. Product requirements
2. Technical proposal or architecture decision
3. Acceptance criteria
4. Existing code and tests
5. Repository documentation
6. User clarification

Treat documents as intent and the codebase as the current implementation truth. Record conflicts between them; do not silently choose one.

## Workflow

### 1. Read the source material

Locate and read the full referenced requirements, proposals, acceptance criteria, diagrams, and related decisions. Establish:

- business goal
- users and workflows
- required behavior
- constraints
- acceptance criteria
- explicit exclusions
- proposed technical direction

Do not scope from a filename, summary, or isolated excerpt when the full source is available.

### 2. Establish the current architecture

Inspect relevant code paths before proposing scope. Trace applicable:

- entry points and owning modules or projects
- domain and business logic
- persistence
- APIs and contracts
- UI or client behavior
- integrations and asynchronous processing
- configuration and secrets
- observability
- existing tests

Prefer repository evidence over assumptions.

### 3. Trace every requirement

Map every material requirement to affected system areas. Classify each as:

- **Covered** - existing behavior already satisfies it
- **Modify** - existing behavior must change
- **New** - new behavior is required
- **Unclear or conflicting** - evidence is ambiguous or contradictory
- **Out of scope** - explicitly excluded

Do not omit a requirement because its implementation is uncertain.

### 4. Define the smallest coherent change

Recommend the minimum set of changes that fully satisfies the approved requirements and fits the current architecture.

Prefer extending existing components, reusing existing patterns, preserving contracts, localizing changes, keeping work reversible, and adding focused tests.

Do not introduce speculative abstractions, unrelated cleanup, architecture redesign, framework replacement, or broad refactoring.

### 5. Assess affected surfaces

Assess only applicable areas:

- applications, projects, modules, and services
- likely files or directories
- domain models and business rules
- API endpoints and contracts
- database schema and data migration
- events, queues, webhooks, and scheduled jobs
- UI states and user flows
- authentication and authorization
- configuration, secrets, and feature flags
- telemetry, logging, and alerting
- automated and manual tests
- deployment and operational changes

Use `Not affected` when evidence shows an area does not require work. Do not invent work or list the whole repository as potentially affected. Do not claim exact file changes before inspecting them.

### 6. Label certainty

Label each material finding:

- **Confirmed** - directly supported by requirements or code
- **Inferred** - strongly suggested by architecture or conventions
- **Open decision** - requires an explicit product or technical choice
- **Unknown** - evidence is missing

Ask only questions whose answers materially change scope, architecture, risk, or acceptance.

### 7. Sequence implementation

Order the proposed work by dependency and risk. Adapt this sequence to the repository:

1. Contracts and decisions
2. Data or configuration foundations
3. Domain and service behavior
4. Integration and API changes
5. UI or consumer changes
6. Tests and verification
7. Rollout and monitoring

### 8. Produce the scope

Return the scope in the response unless the user explicitly asks to save it. Do not modify repository files while scoping.

Use these sections:

1. **Outcome** - approved goal, users, and observable result
2. **Sources and conflicts** - evidence used, missing sources, and contradictions
3. **Current architecture** - relevant flow and owning components, supported by repository paths
4. **Requirement traceability** - each requirement, classification, affected area, evidence, and certainty
5. **Implementation boundary** - in-scope and out-of-scope work
6. **Affected surfaces** - impact, likely locations, and certainty; use `Not affected` where appropriate
7. **Dependencies and sequence** - ordered implementation units and blocking relationships
8. **Test and verification scope** - automated, integration, manual, and regression coverage
9. **Risks and mitigations** - evidence-based risks and proportionate mitigations
10. **Assumptions and open decisions** - only items material to implementation or acceptance
11. **Acceptance mapping** - each acceptance criterion mapped to planned behavior and verification
12. **Completion status** - exactly one status from the completion gate

Keep the scope actionable for an implementation agent without including production code.

## Guardrails

- Do not implement code.
- Do not modify files unless explicitly asked to save the scope.
- Do not invent missing requirements.
- Do not treat a technical proposal as automatically correct.
- Do not redesign architecture without evidence.
- Do not turn optional improvements into required scope.
- Do not hide contradictions or unresolved decisions.
- Do not continue past a decision that materially prevents reliable scoping.

## Completion gate

Conclude with exactly one:

- **Ready for implementation** - the scope is bounded and no blocking decisions remain.
- **Ready with assumptions** - implementation can proceed if the listed assumptions are accepted.
- **Blocked** - a missing fact or unresolved decision materially prevents reliable scoping.

## Success criteria

- Every material requirement is traced.
- Findings are grounded in supplied documents and repository evidence.
- Boundaries and exclusions are explicit.
- Affected files and surfaces are stated conservatively.
- Risks, assumptions, conflicts, and unknowns are visible.
- Verification covers the acceptance criteria.
- The result is ready to hand to an implementation agent.
