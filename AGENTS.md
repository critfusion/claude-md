# claude-md: rules for every agent working in this repo

A UI design and implementation standard for coding agents, kept as one Markdown file. Read first: `README.md` (how projects install the standard) and `ui-framework.md` (the standard itself, canonical).

## Setup and gate
- No build, no dependencies, no tests, no CI workflow. The repo holds `ui-framework.md`, `README.md` and `LICENSE` (MIT).
- Before every push, re-read the edited file and check that each link and the `curl` install line in `README.md` still point at real files.

## Layout
- `ui-framework.md`: the standard. Sections: Design direction, Template-warning signs, Visual quality requirements, UI engineering quality gates, Required workflow and proof, References and iteration, Final standard.
- `README.md`: how to install and use the standard in another repo.
- `LICENSE`: MIT.

## Deploy
No deploy in this repo. Projects fetch `ui-framework.md` from the `main` branch with the `curl` line in `README.md`, so a merge to `main` changes what they download.

## Rules
- Keep the file named `ui-framework.md`, not `CLAUDE.md`. The README says this lets a workplace repo add the standard without replacing its own agent instructions. (This repo's own `CLAUDE.md` only points at this file.)
- The standard is a judgment framework, not a ban list. Do not turn guidance into absolute prohibitions.
- Explicit project requirements and existing design-system conventions override the standard. Keep that sentence.
- Never push to `main`. Open a PR. Stage files by name. No force-push, no amend of pushed commits.
