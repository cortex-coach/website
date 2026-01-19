# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Cortex Coach landing page - a static marketing site with a cyberpunk aesthetic for an AI-powered workout conversion product. The entire site is self-contained in single HTML files with inline CSS/JS for easy deployment to GitHub Pages.

## Development Commands

**Local Development Server:**
```bash
# Python (no installation needed on most systems)
python -m http.server 8000

# Node (requires npx)
npx http-server
```

Then open `http://localhost:8000`

**No build step required** - directly edit `index.html` and refresh browser.

## Architecture

### Single-File Design Philosophy
- **index.html**: All HTML, CSS, and JavaScript in one file (~1000 lines)
- **404.html**: Custom error page following same pattern
- All assets are inline or loaded from CDN (Google Fonts)
- No bundler, no preprocessors, no package.json

This architecture choice enables zero-config deployment to GitHub Pages and other static hosts.

### Code Organization within index.html

**CSS Structure (line ~20):**
- Minified CSS in `<style>` tag
- CSS custom properties at `:root` define color palette
- Organized by component: nav, hero, features, pricing, etc.

**JavaScript (bottom of file):**
- Particle animation system (canvas-based, ~60 particles)
- Interactive terminal demo with workout conversion simulation
- Mobile menu toggle
- FAQ accordion
- Email signup form handler (currently logs to console - needs integration)

### Color System
CSS variables define the cyberpunk theme:
```css
--cyber-purple: #9f7aea
--cyber-cyan: #22d3ee
--cyber-pink: #ec4899
--cyber-yellow: #fbbf24
--cyber-green: #22c55e
--cyber-red: #ef4444
--bg-dark: #0a0014
```

## Key Customization Points

### Email Signup Integration
The `handleSignup()` function at the bottom of index.html currently logs to console. To integrate:
1. Replace the function body with API call to email service
2. Popular options: Mailchimp, ConvertKit, Buttondown
3. Keep the success message display logic intact

### Pricing Updates
Pricing is hardcoded in the pricing section. Search for `$3/month` and `$2/month` to update values.

### Content Sections
Major sections are clearly marked with HTML comments:
- Hero with animated terminal demo
- Features grid (6 feature cards)
- How It Works (3-step process)
- Pricing (2 tiers: Pro and Team)
- FAQ accordion
- CTA section

## Deployment

**Primary deployment target: GitHub Pages**

Requirements:
- `.nojekyll` file (prevents Jekyll processing)
- Branch set to `main` or deployment branch
- Root folder selected in Pages settings

**Custom domain:** Add `CNAME` file with domain name if needed.

## Testing Checklist

When making changes, verify:
1. **Mobile responsiveness** - site uses CSS Grid with breakpoints at 768px and 968px
2. **Particle animation** - canvas element should render particles
3. **Terminal demo** - interactive textarea should accept input and show conversion output
4. **FAQ accordion** - clicking questions toggles answers
5. **Navigation** - smooth scroll to sections, mobile menu toggle works
6. **Forms** - email input validation and submission handler

## Technical Constraints

- **No external dependencies** except Google Fonts
- **No JavaScript frameworks** - vanilla JS only
- **Browser support**: Chrome 80+, Firefox 75+, Safari 13+, Edge 80+
- **Performance target**: Minimal footprint, particles kept to ~60 for smooth 60fps

## Visual Effects

The site uses several CSS animation techniques:
- **Glitch effect** on logo (pseudo-elements with clip-path)
- **Scanlines overlay** (fixed position repeating gradient)
- **Animated grid background** (CSS grid with translate animation)
- **Particle system** (Canvas 2D API, animated via requestAnimationFrame)
- **Scroll animations** (Intersection Observer for fade-ins)

These effects are core to the cyberpunk aesthetic - maintain or enhance them when making changes.
