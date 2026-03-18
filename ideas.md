# NIROGEN — Design Brainstorm

## Chosen Design Philosophy

**Precision Engineering Dark UI — Cyberpunk-Technical Aesthetic**

### Design Movement
Inspired by **Brutalist Digital / Technical Precision** — the visual language of high-performance engineering tools, terminal interfaces, and aerospace dashboards. Think: dark cockpit displays, oscilloscope readouts, and military-grade software UIs.

### Core Principles
1. **Monochromatic depth** — Deep navy-black backgrounds with a single electric cyan accent that functions as the entire brand color system
2. **Typography as structure** — Display font (Michroma) for headlines acts as architectural scaffolding; mono font (DM Mono) for labels/data; Syne for body text
3. **Grid as philosophy** — Subtle grid overlay reinforces the "engineered" quality; layout uses asymmetric grids, not centered columns
4. **Motion with purpose** — Every animation communicates meaning: line reveals = precision, count-ups = performance, marquee = velocity

### Color Philosophy
- `#050e1a` — Deep space black (background): creates infinite depth, makes cyan "glow"
- `#64FFDA` — Electric cyan (accent): the single brand color; used sparingly for maximum impact
- `#8892B0` — Slate (secondary text): recedes, creates hierarchy without competing
- `#CCD6F6` — Light lavender-white (body text): readable but not harsh against dark bg

### Layout Paradigm
- **Left-anchored asymmetric layout** for hero (text left, stats right)
- **12-column mosaic grid** for project cards (not uniform rows)
- **Timeline with vertical spine** for process section
- **3-column equal grid** for why/testimonials (structural, not decorative)

### Signature Elements
1. **Corner brackets** — L-shaped cyan corner accents on cards (top-left gradient line + bottom-right corner bracket)
2. **Monospace data labels** — All metrics, tags, and labels use DM Mono with wide letter-spacing
3. **Animated line reveals** — Headlines animate in from below with overflow:hidden clip

### Interaction Philosophy
- Custom cursor (dot + ring) that scales on hover — signals the site is "alive"
- Hover states reveal grid patterns inside cards — rewards exploration
- Scroll-triggered reveals with staggered delays — content feels curated, not dumped

### Animation Guidelines
- Hero text: line-by-line reveal from translateY(100%) with staggered delays (0.5s, 0.65s, 0.8s)
- Section elements: fade + translateY(32px) → 0 on intersection
- Marquee: continuous 28s linear scroll
- Count-up: 1800ms duration for stats
- Cursor ring: lagged follow (0.12 lerp factor) for organic feel

### Typography System
- **Display**: Michroma — geometric, technical, zero-personality warmth (intentional)
- **Body**: Syne — humanist grotesque, readable, slightly quirky
- **Mono**: DM Mono — data, labels, tags, code — reinforces engineering identity

---

<response>
<text>
**Approach A — Precision Engineering Dark UI** (chosen)
Dark navy/cyan technical aesthetic with custom cursor, grid overlay, asymmetric layouts, and monospace data labels. Michroma + Syne + DM Mono typography system.
</text>
<probability>0.08</probability>
</response>

<response>
<text>
**Approach B — Brutalist Editorial**
High-contrast black/white with aggressive typography, oversized numbers, raw borders, and zero decorative elements. Helvetica Neue + Courier New. Stark, confrontational, memorable.
</text>
<probability>0.06</probability>
</response>

<response>
<text>
**Approach C — Glassmorphism Luxury**
Deep purple-black with frosted glass cards, aurora gradient accents, and soft bloom lighting effects. Clash Display + Cabinet Grotesk. Premium, aspirational, agency-forward.
</text>
<probability>0.07</probability>
</response>
