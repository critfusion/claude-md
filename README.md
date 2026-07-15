# UI Framework

A portable UI design and implementation standard for producing distinctive, accessible, responsive, and verifiably working interfaces with Claude or another coding agent.

The canonical standard is [`ui-framework.md`](./ui-framework.md). It is intentionally **not** named `CLAUDE.md`, so it can be added to a workplace repository without replacing that project's existing agent instructions.

## Use it in a project

Download the framework into the repository:

```bash
curl -fsSL https://raw.githubusercontent.com/critfusion/claude-md/main/ui-framework.md -o ui-framework.md
```

Then instruct the coding agent to read `ui-framework.md` before UI design, implementation, or review work. If the repository already has a `CLAUDE.md`, `AGENTS.md`, or equivalent instruction file, reference this framework from it or merge only the relevant sections deliberately.

## What it covers

- Project-specific design direction and anti-template checks
- Authentic content and coherent visual systems
- Accessibility and interaction foundations
- Responsive layout and mobile behavior
- Motion and rendering performance
- Toolchain boundaries
- Desktop/mobile rendering and real-control verification
- Evidence required before completion

## Guiding principle

This is a judgment framework, not an absolute prohibition list. Explicit project requirements and established brand/design-system conventions take precedence.

## License

MIT. See [`LICENSE`](./LICENSE).
