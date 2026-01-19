# Cortex Coach Design Systems

## Overview

Cortex Coach uses **two distinct design systems** optimized for different contexts:

| System | Codename | Use Case | Primary Goal |
|--------|----------|----------|--------------|
| **Marketing** | Cyberpunk Neon | Landing pages, ads, social | Capture attention |
| **Application** | Muted Digital | Product UI, daily use | Reduce fatigue |

---

## When to Use Each System

### 🎯 Marketing Design System (Cyberpunk Neon)

**Use for:**
- Landing pages and marketing websites
- Social media graphics and ads
- Email campaigns and newsletters
- Promotional videos and animations
- Conference presentations
- Press kit materials
- Onboarding splash screens (first-time only)

**Characteristics:**
- High-saturation neon colors
- Animated backgrounds (particles, grid, scanlines)
- Glitch effects and visual noise
- Bold gradients with glow effects
- Orbitron typography throughout
- Maximum visual impact

**Files:**
- `index.html` — Landing page
- `Cortex_Coach_Design_System___Component_Library.html` — Full component library
- `Cortex_Coach_Design___Brand_Strategy.md` — Brand guidelines

---

### 💻 Application Design System (Muted Digital)

**Use for:**
- Main application interface
- Dashboard and analytics views
- Workout conversion tools
- Settings and preferences
- Account management
- API documentation
- Help center and support docs

**Characteristics:**
- Desaturated, muted color palette
- Static backgrounds (no animations)
- Subtle shadows and glows
- Clean, functional typography
- Inter for body text, Orbitron for headers only
- Optimized for extended daily use

**Files:**
- `cortex-app-design-system.html` — Component library and tokens

---

## Color Palette Comparison

### Backgrounds

| Purpose | Marketing | Application |
|---------|-----------|-------------|
| Base | `#0a0014` | `#12151c` |
| Elevated | `#1a0033` | `#1a1e28` |
| Surface | `#2a0044` | `#232834` |

### Brand Colors

| Color | Marketing | Application |
|-------|-----------|-------------|
| Primary | `#9f7aea` (saturated) | `#6b4d9e` (muted) |
| Cyan | `#22d3ee` (neon) | `#3d8a94` (muted) |
| Yellow | `#fbbf24` (bright) | `#b8901e` (muted) |

### Semantic Colors

Both systems use the same semantic colors for consistency:

| Status | Color |
|--------|-------|
| Success | `#22c55e` / `#2d9262` |
| Warning | `#eab308` / `#b8901e` |
| Error | `#ef4444` / `#b33d49` |
| Info | `#3b82f6` / `#2a6a94` |

---

## Typography

### Marketing System

```css
/* Single font family for brand consistency */
font-family: 'Orbitron', monospace;
font-family: 'Share Tech Mono', monospace; /* code/terminal */
```

### Application System

```css
/* Three-tier typography for readability */
--font-display: 'Orbitron', sans-serif;     /* Headers, brand moments */
--font-body: 'Inter', sans-serif;            /* Body text, UI elements */
--font-mono: 'JetBrains Mono', monospace;    /* Data, code, metrics */
```

---

## Animation Guidelines

### Marketing
- **Particle systems:** 60-100 particles, constant motion
- **Glitch effects:** On hover, 0.3-0.5s duration
- **Scanlines:** Subtle, always-on
- **Transitions:** 200-500ms, ease-in-out
- **Neon pulse:** 2s infinite alternate

### Application
- **No decorative animations**
- **Transitions:** 150-200ms, ease (functional only)
- **Loading:** Simple spinner or progress bar
- **Hover states:** Color change only, no movement
- **Focus states:** Subtle glow, no animation

---

## Component Mapping

| Component | Marketing | Application |
|-----------|-----------|-------------|
| Primary Button | Gradient + glow + sweep animation | Subtle gradient + muted glow |
| Card | Pixel border + animated outline | Simple border + shadow |
| Input | Neon green border + terminal style | Neutral border + focus ring |
| Alert | Colored border + icon | Left accent bar + muted background |
| Badge | High contrast + glow | Muted background + subtle border |
| Navigation | Glitch on hover | Color change only |

---

## CSS Custom Properties

### Marketing System

```css
:root {
  /* Core */
  --cyber-purple: #9f7aea;
  --cyber-cyan: #22d3ee;
  --cyber-pink: #ec4899;
  --cyber-yellow: #fbbf24;
  --cyber-green: #22c55e;
  
  /* Backgrounds */
  --bg-void: #0a0014;
  --bg-dark: #1a0033;
  
  /* Effects */
  --glow-purple: 0 0 20px rgba(159, 122, 234, 0.5);
  --glow-cyan: 0 0 20px rgba(34, 211, 238, 0.5);
}
```

### Application System

```css
:root {
  /* Core */
  --primary-500: #6b4d9e;
  --accent-500: #3d8a94;
  
  /* Backgrounds */
  --bg-void: #0c0e14;
  --bg-base: #12151c;
  --bg-elevated: #1a1e28;
  --bg-surface: #232834;
  
  /* Text */
  --text-primary: #e8eaed;
  --text-secondary: #9ca3af;
  --text-tertiary: #6b7280;
  
  /* Effects */
  --glow-primary: rgba(107, 77, 158, 0.15);
  --shadow-md: 0 4px 6px rgba(0, 0, 0, 0.25);
}
```

---

## Accessibility Notes

### Marketing
- High contrast ratios (neon on dark)
- Motion can be disabled with `prefers-reduced-motion`
- Alternative static version for accessibility

### Application
- WCAG 2.1 AA compliant contrast ratios
- No essential information conveyed by color alone
- Focus indicators on all interactive elements
- Reduced motion by default

---

## Implementation Checklist

### New Marketing Page
- [ ] Use Orbitron for all text
- [ ] Include particle background
- [ ] Add scanline overlay
- [ ] Implement glitch effects on CTAs
- [ ] Use pixel-border on featured elements
- [ ] Include neon glow on buttons

### New Application Screen
- [ ] Use Inter for body, Orbitron for headers only
- [ ] No animated backgrounds
- [ ] Use muted color palette
- [ ] Implement subtle hover states
- [ ] Add focus rings for accessibility
- [ ] Keep transitions under 200ms

---

## File Structure

```
cortex-coach/
├── marketing/
│   ├── index.html                    # Landing page
│   ├── 404.html                      # Error page
│   ├── design-system.html            # Marketing components
│   └── assets/
│       └── logo.svg
│
├── app/
│   ├── design-system.html            # App components (Muted Digital)
│   └── components/
│       ├── buttons.css
│       ├── forms.css
│       ├── cards.css
│       └── navigation.css
│
└── docs/
    ├── DESIGN_SYSTEMS.md             # This file
    └── brand-strategy.md
```

---

## Quick Reference

### Need to grab attention?
→ Use **Marketing** (Cyberpunk Neon)

### Need to be usable daily?
→ Use **Application** (Muted Digital)

### Building the product?
→ Use **Application** (Muted Digital)

### Building a landing page?
→ Use **Marketing** (Cyberpunk Neon)

### Unsure?
→ Default to **Application** — it's always safe for extended use

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0.0 | Jan 2025 | Initial dual design system |
