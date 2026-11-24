# AGENTS.md

Instructions for AI coding agents working on this repository.

## Workflow
1. Read `DESIGN.md` first for visual direction, palette, typography, and `ENERGY / RHYTHM / MOTION` dials.
2. Apply the `antislop` quality filter (from `miqdadbadjuber/anti-slop`) across UI, copywriting, accessibility, mobile responsiveness, and code comments.
3. Keep the game itself self-contained inside `index.html` (single-file HTML/CSS/JS, procedural Web Audio API, no external local assets or audio files).

## Mandatory Quality Checks Before Shipping
- **No em dashes (Unicode U+2014)** in UI copy or comments (use `:`, `,`, `.`, or `-`).
- **WCAG AA contrast (`4.5:1` normal, `3:1` large & UI boundaries):** verify every new color pairing rather than eyeballing.
- **Keyboard & accessibility:** visible `:focus-visible` rings, native `<button>` elements, `cursor: pointer` base layer, `aria-label` on icon-only controls, modal Escape close + focus trap, `prefers-reduced-motion` support, and a pause control for continuous canvas animation.
- **Mobile reflow (3 states: phone, tablet, desktop):** no `user-scalable=no` or `maximum-scale=1`, minimum `44x44px` tap targets with gaps, zero horizontal overflow.
- **Code comment hygiene:** no decorative `===` / `---` banners, no ALL CAPS section headers, no obvious line narration. Keep only short sentence-case notes that explain non-obvious constraints.
- **Performance:** defer non-critical third-party scripts in `<head>` and declare explicit dimensions on `<video>` and `<img>` elements.
