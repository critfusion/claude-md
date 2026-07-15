# Claude UI Design and Implementation Standard

Use the following as the default design and implementation standard for UI work. Treat it as a judgment framework, not a list of absolute bans. Explicit project requirements and existing brand/design-system conventions override it.

## Design direction

1. Start from the product, audience, real content, and primary user task. Before coding, write a one-sentence design thesis and name one project-specific signature idea: a focal artifact, composition, interaction, illustration, or authentic product representation that would not make sense pasted unchanged into an unrelated product.
2. Build one coherent visual world. Typography, palette, geometry, spacing, imagery, iconography, controls, and motion must reinforce the same idea. Prefer a few strong authored choices over many decorative effects.
3. Use real copy, real data, real product states, and authentic brand assets wherever available. Never invent customers, testimonials, logos, metrics, integrations, or capabilities.
4. Use accessible, tested primitives for behavior, but do not ship generic component-library styling unchanged. Art-direct the primitives for this specific project.
5. Familiar patterns are allowed only when they are the clearest solution. Do not mechanically ban fonts, colors, cards, gradients, glass, pills, grids, shadows, or motion. Instead, avoid reflexive use and execute chosen techniques precisely.
6. Cut filler. Every line, label, chip, divider, card, animation, and decoration must earn its place.

## Template-warning signs

Before implementation, identify the two or three defaults this project is most likely to fall into and replace or explicitly justify them. Watch especially for stacked combinations such as:

- eyebrow + oversized headline + generic subtext + two CTAs + decorative right-side panel;
- blue/purple glow gradients, floating cards, icon-in-tinted-tile feature grids, faux app windows, generic code panels, and decorative metadata pills;
- filled-primary plus outlined-secondary buttons used automatically;
- repeated cards, three-tier pricing, testimonial blocks, FAQ, pre-footer CTA slab, and standard multi-column footer assembled in the usual SaaS sequence;
- fashionable default font pairings selected without reference to the product;
- global hover lifts, entrance fades, glows, shadows, grids, or motion applied indiscriminately;
- empty placeholder product UI, fake social proof, or controls that look interactive but do nothing.

A familiar pattern may remain when it genuinely improves comprehension or conversion, but it must be deliberate, branded, accessible, and integrated into the whole composition.

## Non-negotiable visual quality

- Important content is visible and usable by default. JavaScript failure, hydration issues, background tabs, screenshots, or reduced-motion mode must not leave content hidden.
- Text and controls have strong contrast, responsive gutters, and adequate breathing room.
- Nothing is accidentally clipped by fixed heights, overflow, masks, notches, or overlaps.
- Repeated/comparison columns align corresponding headings, descriptions, lists, prices, and actions.
- Intended centering is mathematically and optically correct.
- Shadows and lighting have a restrained, consistent direction; avoid generic halos and visible seams.
- Background texture stays behind readable content.
- Every apparent control works with pointer, keyboard, and touch where applicable, with visible focus states.
- Motion is purposeful, respects `prefers-reduced-motion`, never gates content, pauses expensive offscreen CSS/RAF/WebGL work, and cleans up timers, listeners, observers, and render loops.
- Responsive layouts are composed intentionally, not merely compressed desktop designs.

## UI engineering quality gates

### Components and interaction

- Use the project's existing accessible component primitives first. Do not mix primitive systems inside one interaction surface.
- Prefer native HTML semantics over ARIA repairs or hand-built keyboard behavior.
- Every interactive control needs an accessible name and visible focus state.
- Icon-only controls need an accessible label; decorative icons stay hidden from assistive technology.
- Dialogs trap focus, close with Escape when appropriate, and restore focus to their trigger.
- Associate form labels, helper text, required state, and errors with the correct fields. Put errors beside the failed action rather than relying only on toasts.
- Never block paste in text inputs.
- Destructive or irreversible actions require an explicit confirmation pattern appropriate to the product.

### Responsive layout

- Use dynamic viewport units such as `dvh` when browser chrome can change available height; do not assume `100vh` is stable on mobile.
- Respect safe-area insets for fixed or edge-aligned controls.
- Maintain a deliberate z-index scale instead of arbitrary escalation.
- Test touch targets, text wrapping, overflow, sticky/fixed elements, and virtual-keyboard behavior at representative phone widths.
- Empty states present one clear next action.

### Motion and rendering performance

- Default motion to `transform` and `opacity`; use layout or paint animation only for small, isolated surfaces where it is justified.
- Batch DOM reads before writes. Measure once, then animate with transforms; use FLIP-style transitions for layout-like movement.
- Do not continuously drive animation from raw scroll events or repeated layout reads.
- Prefer `IntersectionObserver` or supported scroll/view timelines for visibility and scroll-linked behavior.
- Every `requestAnimationFrame` loop needs pause/stop and unmount cleanup paths.
- Pause looping CSS, canvas, WebGL, and physics work when offscreen; resume without a large frame-delta jump.
- Apply `will-change` only during an active animation and remove it afterward.
- Avoid continuously animated blur/filter effects and large blurred surfaces. Prefer opacity and translation.
- Respect `prefers-reduced-motion`; essential state changes remain understandable without decorative motion.
- Do not mix animation systems inside one component without a concrete reason and verified cleanup behavior.

### Tooling boundaries

React Doctor, Vitest, pnpm, Playwright, shadcn/ui, and similar tools are useful only when they match the repository's stack and conventions. Do not introduce or migrate package managers, test frameworks, component systems, or animation libraries solely because an external standard recommends them. Use the existing project toolchain unless the user explicitly approves a migration.

## Required workflow and proof

1. Inspect the existing product, content, brand rules, implementation conventions, and available assets before changing anything.
2. State the design thesis, signature idea, and likely template traps.
3. Implement with real content and accessible primitives.
4. Render and inspect representative desktop and mobile sizes.
5. Exercise every visible control with real input.
6. Check keyboard behavior, focus states, focus restoration, Escape behavior, form errors, contrast, reduced motion, responsive behavior, and the browser console.
7. Profile motion at the top, middle, and bottom of long pages. Confirm offscreen CSS and JavaScript animation work stops.
8. Verify timers, listeners, observers, animation frames, media streams, and WebGL resources are cleaned up across navigation/unmount.
9. Review for cohesion, generic-template stacking, contrast, clipping, alignment, centering, dead controls, and unnecessary offscreen animation work.
10. Fix the defects you find and rerun the relevant checks.
11. Run the project's existing lint, type, unit, component, build, and end-to-end gates before reporting completion.
12. Deliver the working artifact with concise evidence: what was built, routes/files changed, viewport and control checks performed, test/build results, and any genuine remaining limitation.

## References and iteration

Use references for their design language, interaction principles, or technical patterns. Do not reproduce another product's branding, copy, proprietary assets, or complete composition.

When generating alternatives, begin with two or three genuinely different design directions. Name them by concept rather than color. After a direction is selected, change only one meaningful variable at a time so feedback remains attributable.

## Final standard

Clean is only the floor. The result should be specific, coherent, usable, performant, and memorable without becoming noisy. If the page could be rebranded for an unrelated product by swapping only copy and colors, strengthen the project-specific idea before calling it complete.
