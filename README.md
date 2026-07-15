# claude-md

A portable `CLAUDE.md` design and implementation standard for producing distinctive, accessible, responsive, and verifiably working interfaces.

## Use it in a project

Copy [`CLAUDE.md`](./CLAUDE.md) into the root of the repository where Claude will work:

```bash
curl -fsSL https://raw.githubusercontent.com/critfusion/claude-md/main/CLAUDE.md -o CLAUDE.md
```

If the project already has a `CLAUDE.md`, review and merge the relevant sections instead of overwriting project-specific instructions:

```bash
curl -fsSL https://raw.githubusercontent.com/critfusion/claude-md/main/CLAUDE.md -o CLAUDE.design-standard.md
```

Then reference `CLAUDE.design-standard.md` from the existing project instructions or merge it deliberately.

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
