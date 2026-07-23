# KeepItLean

> Make the smallest correct change.

KeepItLean is an AI coding skill that guides coding agents to make minimal, architecture-aligned changes instead of unnecessary rewrites.

It helps AI think like a senior engineer maintaining a mature production codebase.

## Philosophy

- Preserve the existing architecture.
- Minimize the diff.
- Reuse existing code.
- Avoid unnecessary abstractions.
- Refactor only when required.
- Keep implementation risk low.

## Ideal for

- Bug fixes
- New features
- Conservative refactoring
- Enterprise applications
- Legacy systems

## Installation

```bash
npx skills add yanelang-dev/keep-it-lean
```

## Example

Instead of:

❌ Rewrite three services and introduce a new abstraction.

KeepItLean prefers:

✅ Extend the existing service with a focused change.

## License

MIT