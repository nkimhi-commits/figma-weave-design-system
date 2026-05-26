# DESIGN.md — Figma Weave

> Drop this file into your project root. AI coding agents read it to generate UI that matches Figma Weave's visual identity.

**Product**: Figma Weave (weave.figma.com)  
**Tagline**: Artistic Intelligence  
**Brand position**: AI as material, humans in control. Node-based creative workflow platform for professional image and video generation.

---

## 1. Visual Theme & Atmosphere

Figma Weave operates at the intersection of creative craft and technical systems. The aesthetic is **restrained so the work can breathe** — the UI steps back to let generated imagery take center stage.

- **Dual-mode identity**: Light surfaces (lemon yellow + white) for marketing and community; dark surfaces (near-black) for product UI
- **Design philosophy**: The palette is deliberately quiet. Color does not compete with content. Every non-neutral hue earns its place.
- **Density**: Medium. Generous whitespace in marketing contexts; structured density in product/node interfaces.
- **Imagery-first**: Layouts are built to frame and showcase generated creative work. Typography and UI chrome should never overpower visuals.
- **Technical but human**: The node-based interface metaphor (connections, wires, iterators) is a brand asset — geometric, precise, but warm in its function.
- **Tone**: Editorial. Not playful, not corporate. Confident and considered.

---

## 2. Color Palette & Roles

### Primary Brand Colors

| Token | Hex | Role |
|---|---|---|
| `yellow-100` | `#F5FF7A` | Primary brand accent. Background, badges, highlights, CTA fills. |
| `yellow-40` | `#F8FFB2` | Soft tint. Light-mode page backgrounds, hover states, subtle panels. |
| `yellow-64` | `#F3FF9E` | Mid-weight yellow. Cards on light backgrounds, tag fills. |
| `yellow-16` | `#FCFFE8` | Near-white yellow. Very subtle tinted surfaces. |
| `yellow-secondary` | `#E8EDB4` | Muted yellow-beige. Dividers, secondary panel backgrounds. |
| `black-100` | `#0A0A0A` | Primary text, dark UI backgrounds, icon fills. |
| `black-92` | `#141414` | Dark card backgrounds, dark nav. |
| `black-88` | `#1E1E1E` | Elevated dark surfaces (node canvas). |
| `black-64` | `#5C5C5C` | Secondary text on light, muted labels. |
| `black-40` | `#999999` | Placeholder text, disabled states. |
| `black-16` | `#D6D6D6` | Borders on light backgrounds. |
| `black-8` | `#EBEBEB` | Dividers, subtle separators. |
| `white` | `#FFFFFF` | Light-mode surface, text on dark. |

### Functional / Product Data-Type Colors (Product UI only)

These map to node connection port types in the Weave interface. Use sparingly — data-type signals only, never decorative.

| Role | Hex |
|---|---|
| Image / visual data | `#7FD99A` (soft green) |
| Prompt / text input | `#6B8AFF` (medium blue) |
| Neutral / passthrough | `#ADADAD` (grey) |
| Style / reference | `#D17FFF` (soft violet) |
| Mask / alpha | `#7FECDA` (mint) |
| Output / export | `#FF8A8A` (coral) |
| Iterator | `#A5C9FF` (sky blue) |
| Number / param | `#C9FF7F` (chartreuse) |

### Error / Status

| State | Hex |
|---|---|
| Error | `#FF4D4D` |
| Warning | `#FF8C00` |
| Processing | `#B57FFF` |
| Success | `#2ECC71` |

---

## 3. Typography

**Primary font**: `Figma Sans` (variable, by Grilli Type for Figma, 2024)  
**Secondary font**: `Figma Mono` (monospace, for technical labels, node names, code, data values)

### Rules

- **Figma Sans Regular (400)** for most content — body, labels, nav, UI copy
- **Figma Sans Medium (500)** for first sentences, subheads, emphasis within body
- **Figma Sans** scales from large expressive headlines down to 11px technical copy — no font switching needed, hierarchy comes from size alone
- **Figma Mono** for node names, model identifiers, parameter keys, code snippets, technical annotations — use sparingly; it should signal "data/code", not replace Sans
- Headlines: **sentence case**, short, punchy. The larger the type, the fewer the words.
- Body copy: Regular weight. Let hierarchy do the work.
- Never use all-caps for body. All-caps reserved for: navigation items, label chips, and status badges only.

### Type Scale

| Use | Size | Weight | Font |
|---|---|---|---|
| Hero headline | 64–96px | 400 | Figma Sans |
| Section headline | 40–56px | 400 | Figma Sans |
| Sub-headline | 28–36px | 500 | Figma Sans |
| Body large | 18–20px | 400 | Figma Sans |
| Body default | 15–16px | 400 | Figma Sans |
| Label / caption | 12–13px | 400–500 | Figma Sans |
| Node label | 11–12px | 400 | Figma Mono |
| Badge / tag | 11px | 500 | Figma Sans (all-caps) |

### Fallback stack

```css
font-family: 'Figma Sans', 'Inter', system-ui, sans-serif;
font-family: 'Figma Mono', 'JetBrains Mono', 'Fira Code', monospace;
```

---

## 4. Component Styling

### Buttons

**Primary (light context)**
- Background: `#F5FF7A` (yellow-100)
- Text: `#0A0A0A`
- Border radius: `100px` (fully rounded pill)
- Padding: `12px 24px`
- Font: Figma Sans Medium 14px
- Hover: darken background to `#ECFF50`, no shadow

**Primary (dark context)**
- Background: `#F5FF7A`
- Text: `#0A0A0A`
- Same pill shape — yellow reads the same on dark

**Secondary / Ghost**
- Border: `1.5px solid currentColor`
- Background: transparent
- Text: inherits context (black on light, white on dark)
- Hover: fill with 8% opacity of text color

**Destructive / Error**
- Background: `#FF4D4D`
- Text: white

**Disabled**
- Opacity: 0.35
- Cursor: not-allowed

### Cards

**Light**
- Background: `#FFFFFF`
- Border: `1px solid #EBEBEB`
- Border radius: `12px`
- Padding: `20px`
- Box shadow: none (flat)

**Dark (node cards / product UI)**
- Background: `#1E1E1E`
- Border: `1px solid rgba(255,255,255,0.08)`
- Border radius: `10px`
- Padding: `16px`

**Image/media cards (portfolio, workflow gallery)**
- No border
- Border radius: `8px`
- Overflow hidden
- Hover: slight scale `1.02`, transition 200ms ease

### Inputs / Form Fields

**Light**
- Background: `#FFFFFF`
- Border: `1.5px solid #D6D6D6`
- Focus border: `1.5px solid #0A0A0A`
- Border radius: `8px`
- Padding: `10px 14px`
- Font: Figma Sans 15px Regular
- Placeholder color: `#999999`

**Dark (product)**
- Background: `#141414`
- Border: `1px solid rgba(255,255,255,0.12)`
- Focus border: `1px solid #F5FF7A`
- Text: `#FFFFFF`

### Navigation (Marketing Site)

- Background: transparent on scroll, `rgba(255,255,255,0.92)` pinned / `rgba(10,10,10,0.92)` dark
- Backdrop filter: `blur(12px)`
- Nav items: Figma Sans 14px Regular, all-caps, letter-spacing 0.05em
- Logo: left-aligned, Weave W mark + wordmark
- CTA button in nav: yellow pill (primary button style)

### Node UI Elements (Product)

- Node cards: dark background (`#1E1E1E`), white text, Figma Mono node name 11px
- Connection ports: colored dots (data-type colors above), 8px diameter
- Connection lines: 1.5px strokes matching port color, cubic bezier curves
- Canvas background: `#0A0A0A` or `#141414`
- Selected state: port/node outline in `#F5FF7A`

### Tags / Badges

- Background: `#F5FF7A` on light; `rgba(245,255,122,0.15)` on dark
- Text: `#0A0A0A` on light; `#F5FF7A` on dark
- Border radius: `100px`
- Padding: `4px 10px`
- Font: Figma Sans 11px, Medium, all-caps, letter-spacing 0.08em

### Text Highlight / "Office Hours" label style (community/marketing)

Yellow rounded rectangle labels used over imagery:
- Background: `#F8FFB2`
- Text: `#0A0A0A`, Figma Sans Bold ~32–48px depending on context
- Border radius: `12px`
- Padding: `12px 20px`
- Two stacked blocks (word-wrapped as separate pills)

---

## 5. Layout Principles

### Spacing Scale (8px base)

| Token | Value | Use |
|---|---|---|
| `space-1` | `4px` | Inline gaps, tight pairs |
| `space-2` | `8px` | Component internal padding |
| `space-3` | `16px` | Card padding, list gaps |
| `space-4` | `24px` | Section internal spacing |
| `space-5` | `40px` | Component blocks |
| `space-6` | `64px` | Section gaps |
| `space-7` | `96px` | Major section breaks |
| `space-8` | `128px` | Hero padding, large breaks |

### Grid

- Max content width: `1280px`
- Page padding: `24px` mobile, `48px` tablet, `80px` desktop
- Column grid: 12-column, `24px` gutters
- Node canvas: free-form infinite canvas, no grid constraints

### Philosophy

- Design is restrained so imagery leads
- Full-width image panels are preferred over boxed thumbnails for hero moments
- Generous negative space is a feature, not wasted room
- Text blocks should never fight with image panels — separate them clearly or overlay with high-contrast treatment
- Asymmetric layouts are acceptable and encouraged in editorial contexts

---

## 6. Depth & Elevation

Figma Weave uses a **flat hierarchy** in most surfaces. Avoid drop shadows except:

| Level | Use | Shadow |
|---|---|---|
| 0 | Default surfaces | none |
| 1 | Floating panels, dropdowns | `0 4px 16px rgba(0,0,0,0.12)` |
| 2 | Modals, overlays | `0 8px 40px rgba(0,0,0,0.24)` |

On dark surfaces: use border opacity (`rgba(255,255,255,0.08)`) to delineate surfaces instead of shadows.

---

## 7. Do's and Don'ts

### Do
- Let generated imagery be the hero — never crop or obscure it with UI chrome
- Use yellow sparingly and with purpose — it's an accent, not wallpaper
- Use Figma Mono only for technical, data-type contexts (node names, model IDs, parameters)
- Maintain the product's "node UI as brand language" — the flow graph aesthetic is part of the visual identity
- Use sentence case for all headlines
- Keep the palette restrained: black, white, yellow. Add color only for data-type signaling or error states.
- Prefer pill shapes (fully rounded) for CTAs; prefer slightly rounded corners (8–12px) for cards and inputs

### Don't
- Don't use gradients on backgrounds — Figma Weave backgrounds are flat
- Don't use multiple accent colors in non-product contexts (yellow is the one accent)
- Don't use all-caps for body copy or headlines — only nav labels and badges
- Don't add shadows to cards unless the card is floating (dropdown, modal)
- Don't use Figma Mono for general body or headline copy
- Don't use purple, blue, or other hues in marketing UI — those belong exclusively to the product node data-type system
- Don't crowd generated imagery with text overlays — give it room
- Don't use border-radius larger than `100px` (pill) or smaller than `6px` on interactive elements
- Don't use fonts other than Figma Sans and Figma Mono

---

## 8. Responsive Behavior

| Breakpoint | Width | Behavior |
|---|---|---|
| Mobile | `< 768px` | Single column, full-width images, stack all grid items |
| Tablet | `768px – 1024px` | 2-column grids, condensed nav |
| Desktop | `> 1024px` | Full layout as designed |
| Wide | `> 1440px` | Max content width caps at 1280px, outer paddings expand |

- Touch targets: minimum `44×44px`
- Nav collapses to hamburger at mobile
- Node canvas: desktop-only (no mobile node editing)
- Image-heavy sections reorder to single column on mobile with full-bleed images

---

## 9. Brand Voice & Copy Patterns

- **Tagline**: "Artistic Intelligence" — always exactly this phrase, Title Case
- **Product name**: "Figma Weave" — never "Weavy" alone in new contexts
- **Core concept pairs**: AI + Human, Vision + Workflow, Models + Craft
- **Footer CTA**: "Artificial Intelligence + Human Creativity" (rendered as a node-like equation)
- Headline tone: declarative, not interrogative. "Use all AI models, together at last." not "Want to use all AI models?"
- Never use "powerful", "seamless", "cutting-edge", "game-changer", "revolutionary"

---

## 10. Agent Prompt Guide

### Quick reference

```
Primary accent:  #F5FF7A  (yellow-100)
Light background: #F8FFB2 (yellow-40) or #FFFFFF
Dark background:  #0A0A0A or #141414
Primary text:    #0A0A0A (light) / #FFFFFF (dark)
Secondary text:  #5C5C5C (light) / #999999 (dark)
Border (light):  #EBEBEB
Border (dark):   rgba(255,255,255,0.08)
Primary font:    Figma Sans (fallback: Inter)
Mono font:       Figma Mono (fallback: JetBrains Mono)
Border radius:   8px cards, 100px buttons/pills, 12px tags
```

### Prompt templates

**Marketing page section:**
> Build a section using the Figma Weave DESIGN.md. Light background (#F8FFB2 or white), Figma Sans typography, yellow (#F5FF7A) pill CTA button, imagery-forward layout. Flat. No gradients. No shadows on cards.

**Product UI panel (dark):**
> Build a dark product UI panel using the Figma Weave DESIGN.md. Background #141414, white text in Figma Sans, node labels in Figma Mono 11px, connection ports as 8px colored dots using data-type colors. Yellow (#F5FF7A) for selected/active states only.

**Community event card (Office Hours style):**
> Create an event card in Figma Weave style: full-bleed editorial image, yellow rounded-rectangle (#F8FFB2) label overlaid over the lower portion of the image, Figma Sans Bold for the event name. No other colors.

**Node flow diagram:**
> Render a node graph in Figma Weave style: dark canvas (#0A0A0A), rounded rectangle nodes (#1E1E1E, white border rgba 8%), colored connection ports (green=image, blue=prompt, grey=neutral), curved bezier connection lines, Figma Mono node labels.
```
