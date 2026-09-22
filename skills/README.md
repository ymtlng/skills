
Skills for understanding and implementing code changes safely.

## ScopeIt

### What it is

[ScopeIt](scope-it/SKILL.md) converts approved product requirements or technical proposals into a codebase-aware implementation scope. It identifies affected components, boundaries, dependencies, risks, tests, assumptions, and open decisions without writing implementation code.

### Why we need it

Requirements describe intent, while the repository reflects the current implementation. ScopeIt connects the two before coding begins so teams can expose conflicts, avoid invented work, and agree on the smallest coherent change.

### Install

```bash
npx skills add ymtlng/skills --skill scope-it
```

## KeepItLean

### What it is

[KeepItLean](skills/SKILL.md) guides coding agents to make minimal, production-safe changes that preserve existing architecture and patterns.

### Why we need it

AI coding agents can over-engineer focused requests by introducing unnecessary abstractions, rewrites, and unrelated cleanup. KeepItLean constrains implementation to the smallest correct change, reducing maintenance cost and deployment risk.

### Install

```bash
npx skills add ymtlng/skills --skill keep-it-lean
```

## Install both

```bash
npx skills add ymtlng/skills
```

Select both skills when prompted.

## Recommended workflow

1. Use `$scope-it` to produce and review an implementation-ready scope.
2. Resolve any blocking decisions or accept the documented assumptions.
3. Use `$keep-it-lean` to implement the approved scope with the smallest safe change.
