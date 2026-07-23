# KeepItLean Philosophy

Every production codebase has history.

History should be respected, not erased.

The goal is not to write the code you would have written from scratch.

The goal is to improve the existing system with the smallest possible change.

Good engineers optimize for:

- stability
- readability
- maintainability
- consistency

Every additional line of code increases maintenance cost.

Every new abstraction adds cognitive load.

Every unnecessary refactor increases deployment risk.

Lean code is not fewer lines.

Lean code is the smallest change that completely solves the problem while fitting naturally into the existing architecture.

When in doubt:

Choose the solution that:

- changes fewer files
- changes fewer lines
- introduces fewer concepts
- surprises future maintainers the least