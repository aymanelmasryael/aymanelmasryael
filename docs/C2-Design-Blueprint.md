# C2 Design Blueprint — www.aymanelmasry.com (Corporate Website)

**Phase:** C1.5 — Design Blueprint (PLAN only. No file modified.)
**Date:** 2026-08-06
**Status:** Approved for implementation (Open Decisions resolved 2026-08-06)
**Prepared by:** AEL Engineering (OpenCode) + Ayman Elmasry
**Governance:** AGENTS.md — Product Architecture / Verification Policy / Decision Policy

---

## 1. Vision

Transform the current **personal-brand page** into a **product-first corporate website** that
convinces a client in under a minute: *"AEL builds systems."*

The page must answer, in order of attention:
1. **What does AEL build?** (Selected Systems — proof by flagship)
2. **What can AEL do for me?** (Core Capabilities)
3. **Show me real work.** (Projects)
4. **Can I trust you?** (Verified Credentials)
5. **Let's talk.** (Contact — via Wix, added later)

The redesign is a *translation of a blueprint to code*, not a design-by-programming session.
Every visual decision below is pre-decided.

---

## 2. Current State Analysis (Evidence)

### 2.1 Existing Information Architecture

```
Nav:  Identity · Systems · Services · About(→me) · Deployed Systems[CTA]
01 Hero            H1 "Ayman Elmasry" + terminal animation      [person-first]
02 Identity        Photo, bio, AEL Digital Studio, expertise, metrics
   Sovereign       Legal/IP verification cards (3 glass cards)
03 Services        "Architectural Services" — 3 categories + 4-step process
04 Systems         "Systems" — 4 quadrants + framework docs
05 Portfolio       "Deployed Systems Portfolio" — 6 project cards
Footer             © + social (GH/LinkedIn/X/IG/CodePen)
```

### 2.2 Strengths (keep)

- Dark navy `#0B1220` + electric blue `#0074FF` identity — trust + innovation, on-brand.
- Terminal hero visual is distinctive and memorable.
- Strong trust signals already present (verification matrix, metrics, 6 real projects).
- Good accessibility baseline: skip-nav, `aria-labelledby`, `aria-hidden` icons,
  `sr-only`, `focus-visible`, `prefers-reduced-motion`, `prefers-color-scheme`.
- Design System tokens connected (C1) — the site now speaks the shared design language.

### 2.3 Weaknesses (fix)

| Issue | Evidence |
|---|---|
| Person-first: H1 is the human's name, not the company's value | Hero H1 "Ayman Elmasry" |
| Conversion narrative inverted — Services before proof | Order: Services(03) before Systems(04)/Portfolio(05) |
| No Contact at all (removed earlier); no conversion path | No CTA section, nav has no Contact |
| Identity duplicated: hero + Identity section + About link + Sovereign | 4 places to tell "who" |
| Ad-hoc typography (not a scale) | ~30 distinct font-sizes incl. inline `style="font-size:1.3rem"` on 6 cards |
| Visual hierarchy flat within sections | Multiple competing headers per section |
| Sovereign section overlaps Identity and Credentials | Legal + IP + verification mixed |

---

## 3. Design Principles

1. **Product-first, proof-driven.** Show the work before describing services.
2. **One page, one narrative.** A single downward scroll = one argument for AEL.
3. **Show, don't tell.** Systems/Projects carry the page; text supports.
4. **Systemic consistency.** Every value from the Design System tokens (C1 already connected).
5. **Trust by evidence.** Metrics, verification, real links — never decorative claims.
6. **Accessible by default.** WCAG 2.1 AA; keyboard, reduced-motion, contrast, focus.
7. **Preserve the soul.** Keep dark-navy identity, terminal motif, verification matrix.

---

## 4. Information Architecture

### 4.1 Target site map

```
Nav:  Systems · Services · Projects · Credentials · Founder(→ aymanelmasry.me)
01 Hero (no number)          — AEL Digital Studio™ — Engineering Intelligent Digital Systems.
02 Selected Systems          — 4 flagship systems (core IP) + "Explore All Systems" card.
03 Core Capabilities         — 3 service categories + process (4 steps).
04 Projects                  — 6 shipped projects with live links.
05 Verified Credentials      — Legal + IP + verification matrix + metrics.
[Contact]                    — NOT in this HTML. Native Wix Studio Contact component,
                               added later inside Wix. Page ends cleanly before it.
Footer                       — © + social + brand-system link.
```

> **No Contact section is implemented in the HTML** (per decision §18.1). No mailto CTA,
> no Web3Forms, no custom form, no nav entry, no CSS/JS for Contact. The file ends cleanly
> after Verified Credentials / Footer, ready for the future Wix Contact section.

### 4.2 Why this order

| Position | Section | Job | Buyer psychology |
|---|---|---|---|
| Above fold | Hero | Hook + position | "Is this relevant to me?" |
| 2 | Selected Systems | Credibility by flagship | "They build real things." |
| 3 | Core Capabilities | Match needs | "Can they do MY thing?" |
| 4 | Projects | Proof with links | "Real work, real clients." |
| 5 | Credentials | Trust closure | "Are they legitimate?" |
| — | Contact (Wix) | Action — added later in Wix | "Let's start." |

Rationale: **proof precedes capability.** An agency page that lists services first forces the
reader to trust before seeing evidence. Leading with flagship systems converts "who are you?"
into "what did you ship?" in the first scroll.

---

## 5. User Journey

**Primary persona:** C-level / founder commissioning a digital product or brand system.
**Secondary:** technical evaluator; journalist/collaborator.

```
LAND ──> POSITION ──> VALIDATE ──> MATCH ──> TRUST
Hero      tagline      Systems      Capabilities  Credentials
(3s)      + terminal   (flagship)   (3 categories) (matrix)
          + 2 CTAs     + 4 cards    + process      + metrics
```

- **0–3s:** Read eyebrow + H1 + terminal animation → "AEL Engineering Intelligent Digital Systems."
- **3–10s:** Skim Systems cards → flagship proof.
- **10–30s:** Core Capabilities → "fits my need?"
- **30s+:** Projects (open links) → real evidence.
- **Decision:** Credentials close risk. Conversion → Wix Contact component (added later) + social links.

**Conversion path:** each section ends with a subtle micro-link into the next; the loud action
(Contact) is provided by Wix Studio's native Contact component after migration.

---

## 6. Content Mapping (current → future)

| Current | New home | Action |
|---|---|---|
| Hero "Ayman Elmasry" H1 | Hero — new company-first H1 | Rewrite copy |
| Terminal animation | Hero (keep) | Reframe as "AEL systems" terminal script |
| Identity: photo/bio/title | Move to `aymanelmasry.me`; keep "Founder — Ayman Elmasry" line in Hero | Relocate |
| Identity: expertise (3) | Fold into Core Capabilities | Merge |
| Identity: metrics (6+) | Verified Credentials | Move |
| Sovereign: 3 glass cards | Verified Credentials (merge w/ matrix) | Merge |
| Platform Verification Matrix | Verified Credentials (centerpiece) | Keep/upgrade |
| Services: 3 categories | Core Capabilities | Rename + reorganize |
| Process Architecture (4 steps) | Core Capabilities (sub-block) | Keep |
| Systems: 4 quadrants | Selected Systems | Reframe as flagship systems |
| Framework docs | Selected Systems (link row) | Keep links |
| Portfolio: 6 projects | Projects | Keep cards, standardize type scale |
| — | Contact | **Not implemented** — native Wix Studio Contact component later | Note only |
| Footer | Footer | Keep + add brand-system link |

---

## 7. Visual Language

### 7.1 Token foundation (already connected, C1)

All values bind to the AEL Design System tokens (`--ael-*`), which now match `identity.html`.

### 7.2 Color roles

| Role | Token | Value | Use |
|---|---|---|---|
| Brand primary | `--ael-color-primary` | `#0074FF` | CTAs, links, accents |
| Page surface | site `--ael-bg-deep` | `#0B1220` | Page background |
| Card surface | site `--ael-bg-card` | `#131C2A` | Cards, panels |
| Text high | site `--ael-text-primary` | `#E6EEF8` | Headings, body |
| Text low | site `--ael-text-secondary` | `#94A3B8` | Secondary |
| Accent violet | `--ael-color-accent-violet` | `#6C47FF` | Category tags: Systems |
| Accent teal | `--ael-color-accent-teal` | `#00D4AA` | Category tags: Capabilities/Process |
| Accent pink | `--ael-color-accent-pink` | `#FF4D8D` | Category tags: Projects/Featured |
| Accent amber | `--ael-color-accent-amber` | `#F59E0B` | Category tags: Credentials/Verified |
| Semantic | success/error/info | — | Verification states |

> Accent colors are **category coding only** (tags, icons, thin rules) — never surfaces.
> One accent per section for quiet hierarchy.

---

## 8. Component Hierarchy

```
Layer 0  Tokens          --ael-* (connected)
Layer 1  Primitives      Icon, Button, Tag, SectionHeader, Container
Layer 2  Molecules       GlassCard, ProjectCard, SystemCard, Metric, Step, VerificationItem, NavLink
Layer 3  Sections        Hero, SelectedSystems, CoreCapabilities, Projects, Credentials
Layer 4  Layout          StickyNav, Footer, SkipNav, ProgressBar
```

**Naming:** keep `ael-` prefix + BEM-ish (`ael-card__media`, `ael-card__body`).

---

## 9. Core Sections Design

### 9.1 Hero (no number)
- **Layout:** split 56/44. Left: eyebrow (`AEL Digital Studio™`), H1, founder line, subline,
  2 CTAs (`Explore Systems` → `#systems`, `View Projects` → `#projects`), trust strip (metrics inline).
- **Right:** terminal (keep), script rewritten to a "systems build" sequence.
- **Copy (Company-first, approved):**
  - Eyebrow (mono): **AEL Digital Studio™**
  - H1: **Engineering Intelligent Digital Systems.**
  - Founder line: **Founder — Ayman Elmasry**
  - Subline: short capability sentence (Draft: *"We design and engineer AI, brand, and digital
    systems for modern businesses."* — final wording in C2 copy pass)
- **Scale:** H1 `clamp(2.5rem, 5vw + .5rem, 4.5rem)`, mono eyebrow `var(--ael-typography-font-mono)`.

### 9.2 Selected Systems (01)
- **4 flagship systems** (core IP — approved selection):
  | # | System (official name) | Core capability |
  |---|---|---|
  | 1 | AEL Ωmega Platform™ | AI Orchestration |
  | 2 | AEL Prompt IP System™ | Prompt Engineering |
  | 3 | AEL Sovereign Reference Engine™ | Knowledge Systems |
  | 4 | AEL Design System™ | Design Systems |
  - Selection criteria (per Ayman): core IP · distinct capabilities (AI / Prompt / Knowledge /
    Design) · mature & representative (not newest).
  - "Sovereign" alone was ambiguous → full official name **AEL Sovereign Reference Engine™**
    (Sovereign brand + descriptive "Reference Engine").
- **SystemCard anatomy:** icon, name, one-sentence value proposition, key-capability tag,
  **"Learn more"** action (→ live system page).
- **5th card:** "Explore All Systems" → complete systems catalog
  (target: `https://github.com/aymanelmasryael` — AEL organization).
- Layout: 2×2 grid on ≥1024, 1-col mobile (5th card spans full row or 3×2 arrangement).

### 9.3 Core Capabilities (02)
- 3 **CapabilityCards** (icon, title, 4 bullets) — from current service categories.
- Below: Process Architecture strip (4 steps with connecting line + step numbers).

### 9.4 Projects (03)
- 6 **ProjectCards** in 3-col grid (≥1200) / 2-col (≥768) / 1-col.
- Standardized type (remove inline `font-size`), overlay + "Visit live project" primary button.

### 9.5 Verified Credentials (04)
- **VerificationMatrix** as centerpiece (keep ✓ pattern).
- Side/merged: 3 credential cards (Legal, IP, Metrics grid).
- Tags use success/amber for verified states.

### 9.6 Contact (Wix — NOT implemented here)
Per decision §18.1: **no custom Contact in the HTML.** No mailto CTA, no Web3Forms, no form,
no nav entry, no CSS/JS. The page ends cleanly (Verified Credentials + Footer). The future
**native Wix Studio Contact component** will be added later inside Wix.

### 9.7 Nav (updated)
`Systems · Services · Projects · Credentials · Founder(→ aymanelmasry.me)`
Keep sticky glass + scrollspy + mobile hamburger. **"Founder"** replaces "About" and links to
the personal site, separating corporate identity from personal identity (per §18.4).

---

## 10. Grid System

- Source of truth: `--ael-grid-*` tokens (12-col, max-width **1280px**, gutter 32/24/16, margin 64/32/16).
- Container: `max-width: 1280px; padding-inline: clamp(24px, 5vw, 64px)` (already in place).
- Layout recipes:
  - Hero split: `grid-template-columns: clamp(460px, 56%, 1fr) 1fr`
  - Systems/Projects: `repeat(3, 1fr)` → `repeat(2, 1fr)` (≥768) → `1fr`
  - Capabilities: `repeat(3, 1fr)` → `1fr`
  - Credentials: `2fr 1fr` matrix + stack
- No hardcoded widths; all via tokens + `minmax`/`clamp`.

---

## 11. Spacing System

- Scale: `--ael-spacing-*` (4,8,16,24,32,40,48,56,64,80,96,128) + site 12px.
- Vertical rhythm: section padding `clamp(64px, 8vw, 128px)`; section→section gap same.
- Intra-section: header→content `--ael-spacing-xl` (32) / `2xl` (40) / `3xl` (48).
- Card padding: `--ael-spacing-lg` (24); card gap in grids: `--ael-spacing-lg/xl`.
- Rule: **never** invent a new value — bind to the scale.

---

## 12. Typography Scale

Base 16px, Inter (body/display) + JetBrains Mono (eyebrows, labels, terminal).

| Role | Fluid | Token (desktop) |
|---|---|---|
| Display (Hero H1) | `clamp(2.5rem, 5vw + .5rem, 4.5rem)` | — |
| H1 | `clamp(2rem, 4.5vw, 3rem)` | — |
| H2 (section title) | `clamp(1.75rem, 4vw, 2.25rem)` | — |
| H3 (card title) | `clamp(1.25rem, 3vw, 1.75rem)` | — |
| H4/body-lead | `1.25rem` | `--ael-typography-size-h4` |
| Body | `1rem` | `--ael-typography-size-body` |
| Small/label | `0.875rem` | `--ael-typography-size-small` |
| Mono eyebrow | `0.75rem` mono, letter-spacing `.12em`, uppercase | — |

- Section headers: **eyebrow (mono) + title + subtitle** — one voice per section.
- Remove all inline `font-size` (6 project cards) and orphan sizes (0.65rem, 0.95rem drift).

---

## 13. Card System

| Prop | Value | Token |
|---|---|---|
| Surface | `#131C2A` | site `--ael-bg-card` |
| Border | `rgba(255,255,255,.08)` | site `--ael-border-light` |
| Radius | 16px (lg) / 12px (md) | site `--ael-site-radius-lg` |
| Padding | 24px | `--ael-spacing-lg` |
| Hover | translateY(-4px) + border→`rgba(255,255,255,.12)` + glow | site shadows/`--ael-glow-primary` |
| Icon chip | 40px rounded-lg, tinted bg 10% accent | — |

Anatomy: `media (optional) / icon-chip + title + body + tags + action`.
States: default / hover / focus / (disabled not used on cards).

---

## 14. Button System

From `identity.html` (already token-bound):

| Variant | Surface | Hover |
|---|---|---|
| Primary | `--ael-color-primary` | `--ael-color-primary-hover` (`#0062D6`) |
| Secondary | transparent + border | `rgba(255,255,255,.04)` |

- Sizes: md (44px) default; lg (52px) hero CTA.
- Radius: `--ael-site-radius-md` (12px); padding 12×24.
- States: hover / `:focus-visible` (2px outline + 2px offset) / `:active` / `:disabled` (0.4 opacity).
- All buttons are `<a>` (external) — keep `rel="noopener noreferrer"`, `target="_blank"` for projects.
- One primary per section; rest secondary/ghost.

---

## 15. Motion Principles

- Tokens: `--ael-motion-duration-*` (150/300/500ms) + `--ael-motion-easing-default`.
- Allowlist: hover lift (cards, buttons), fade+slide on section reveal (IntersectionObserver,
  `translateY(12px)→0`), terminal typing, nav underline, scrollspy active state.
- **Reduced motion:** `@media (prefers-reduced-motion: reduce)` → disable typing/reveal/lift
  (already present — extend to new components).
- No spinning, no marquee, no infinite motion.

---

## 16. Responsive Strategy

Breakpoints (from tokens): **1440 → 1280 → 1024 → 768 → 640 → 480**.

| Width | Behavior |
|---|---|
| ≥1200 | 3-col grids (Systems/Capabilities/Projects), hero 56/44 |
| 1024 | 3-col→2-col, nav compressed |
| 768 | 2-col→1-col, hero stacks (visual below content) |
| ≤640 | single column, hamburger nav, H1 clamp min |
| ≤480 | spacing 24/32, touch targets ≥44px, terminal simplifies |

- Mobile-first authoring in C2 (`min-width` queries where practical).
- `scroll-margin-top: calc(var(--ael-nav-height) + 24px)` on all `[id]` sections (already in place).
- Test matrix: 1440, 1024, 768, 480 + Safari/Chrome/Firefox + print.

---

## 17. Accessibility Strategy

**Keep:** skip-nav, landmarks, `aria-labelledby`, `aria-hidden` icons, `sr-only`, focus-visible.
**Add/extend (C2):**
- Contrast: verify text on `#0B1220`/`#131C2A` meets AA (E6EEF8 = 15+:1; secondary 94A3B8 ≈ 6.5:1 ✓).
- Focus rings on ALL interactive (buttons, cards-as-links, social).
- Touch targets ≥44×44 (nav, social, buttons).
- Forms (if Contact=form): real `<label>`, `aria-required`, `aria-invalid`, `aria-live` status.
- Cards must be link-first (`<a class="ael-project-card">`) — never clickable `<div>`.
- `aria-current="true"` on active nav item (scrollspy).
- Keyboard: skip-link → main → all sections reachable; no trapped focus in mobile menu.
- Terminal: `aria-hidden` decorations; output announced via `aria-live="polite"` (exists).

---

## 18. Decisions (resolved 2026-08-06)

1. **Contact.** ✅ **No Contact section in the HTML.** Native Wix Studio Contact component will
   be added later inside Wix. No mailto CTA, no Web3Forms, no form, no nav entry, no CSS/JS.
   Page ends cleanly before the future Wix Contact section.
2. **Hero copy (Company-first).** ✅
   - Eyebrow: **AEL Digital Studio™** · H1: **Engineering Intelligent Digital Systems.**
   - Founder line: **Founder — Ayman Elmasry**
   - `aymanelmasry.me` keeps person-first (Visionary Architect / AI Orchestrator / Brand
     Designer) — the two sites do not duplicate each other.
3. **"About" → "Founder".** ✅ Nav item renamed **Founder**, links to `https://aymanelmasry.me`.
   Clean separation: corporate (systems/projects/services) vs personal (bio/story/philosophy).
4. **Section numbering.** ✅ 01 Selected Systems · 02 Core Capabilities · 03 Projects ·
   04 Verified Credentials (hero unnumbered).
5. **Selected Systems count.** ✅ Exactly 4 flagship systems (Ωmega Platform™ / Prompt IP
   System™ / Sovereign Reference Engine™ / Design System™) + a 5th **"Explore All Systems"**
   card → catalog (`github.com/aymanelmasryael`).
6. **Nav labels.** ✅ `Systems · Services · Projects · Credentials · Founder`.
7. **Terminal script content.** Rewrite to a systems theme (draft supplied in C2).

---

## 19. Implementation Notes (Phase C2 scope)

### Execution Rules (mandatory)

1. **Create a timestamped backup** before any modification.
2. **Implement one section at a time.**
3. **Run the full C1 verification harness after each completed section**
   (pixel diff, DOM structure, brace balance, undefined `var()`).
4. **Do not continue if any regression is detected** — stop, fix the section, re-verify.
5. **Commit only after the entire phase passes verification.**

This isolates any error to the section being edited instead of letting regressions
accumulate across sections and become untraceable.

### Execution order

- **Backup first** (destructive per AGENTS.md), then section-by-section:
  Nav → Hero → Selected Systems → Core Capabilities → Projects → Credentials → Footer → Motion/A11y.
- After each section: run verification harness; only proceed on green.
- **No Contact work at all** — do not create, wire, or reference any Contact element.
- Translate this blueprint exactly; any deviation = a new decision, not on-the-fly design.
- Deliverable: C2 Migration/Redesign Report + updated Blueprint (post-implementation).
- Target: **one page, dark-navy identity preserved, all tokens from the Design System.**

---

*End of C2 Design Blueprint v0.2 — approved. Ready for Phase C2 implementation.*
