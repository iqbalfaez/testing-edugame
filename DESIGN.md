# DESIGN.md

Design direction for **CYBER SKY RBT: Misi Komponen Elektronik & Mikropengawal**.

## Design Read
Reading this as: interactive AR educational cockpit game for Malaysian secondary school RBT students (Bahasa Melayu), in a sharp dark-slate aviation HUD language with targeted cyan lock accents, dial `ENERGY 2 / RHYTHM 2 / MOTION 2`.

Dial: ENERGY 2 / RHYTHM 2 / MOTION 2

## Product Identity & Visual Hierarchy
1. **RBT component / function text** on drones is the #1 visual priority: crisp white text on dark matte holographic panels with automatic font fitting and zero clipping.
2. **Cyber RBT Drones** are the active focal targets in the playfield.
3. **Cyber Gauntlet & Arc Core** give clear spatial aiming feedback for hand tracking and pointer fallback.
4. **Cockpit HUD** frames the top and bottom edges compactly without competing with the playfield.
5. **Atmospheric sky & effects** stay calm and secondary so reading Bahasa Melayu terminology is never disrupted.

## Palette (R-01, R-25, R-29)
- **Core dark base:** `#070d1f` (deep cockpit slate) and `#0b142c` (elevated solid HUD plate). Reason: high legibility against live webcam AR underlay and bright holographic drone text.
- **Core neutral text:** `#ffffff` (primary, `19.33:1` on `#070d1f`), `#cbd5e1` (secondary, `13.02:1`), `#94a3b8` (muted labels, `7.54:1`). Zero colors below WCAG AA `4.5:1`.
- **Core structural accent:** `#06f6ff` (Cyber Cyan, `14.39:1` on `#070d1f`) reserved for active target lock, Arc Core, and primary mission action.
- **Deliberate secondary accent:** `#f59e0b` (Amber, `9.00:1` on `#070d1f`) reserved for combo multiplier, star rewards, and mission objective headers.
- **Semantic status colors:** `#34d399` (Emerald, correct confirmation), `#fb7185` (Rose, wrong-target shield deflection and error state), `#a78bfa` (Violet, standby gauntlet/city horizon accent).

## Typography (R-06)
- **Display & HUD counters (`Orbitron`):** angular cockpit instrumentation feel for score, combo, progress `00 / 16`, and modal headings.
- **Readable Bahasa Melayu body & drone text (`Kanit`, fallback `Rajdhani`):** wide open letterforms that remain clear on floating canvas drones across phone, tablet, and desktop screens.
- Fluid heading sizes using `clamp()` so text scales across breakpoints without overflow.

## Technique Purpose & Dose Caps (R-07 to R-19, R-31)
- **Glassmorphism (R-10):** applied to at most 2 floating surfaces at a time (the central mission prompt banner and the active modal dialog). Secondary HUD modules use solid matte dark-slate plates for clear foreground hierarchy.
- **Glow (R-13):** reserved strictly for active focus moments (primary `MULA MISI` CTA, active `TARGET LOCK` reticle, and open-palm Arc Core).
- **Motion (R-19, R-39):** gentle sky drift, drone patrol, and 0.75s charge feedback match `MOTION 2`; non-essential animations stop under `prefers-reduced-motion: reduce`, and gameplay includes a visible Pause (`Jeda`) control.
- **Icons (R-04):** custom canvas vector circuit symbols directly depicting each of the 16 RBT electronic components.
- **Single-file constraint:** all runtime HTML, CSS, and JS remain inside `index.html` with zero external local files or audio files.
