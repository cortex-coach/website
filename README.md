# Cortex Coach Landing Page

> Neural Workout Intelligence — AI-powered workout conversion for athletes and coaches

![Cortex Coach](https://img.shields.io/badge/CORTEX-COACH-9f7aea?style=for-the-badge&labelColor=0a0014)
![Status](https://img.shields.io/badge/STATUS-ONLINE-22c55e?style=for-the-badge&labelColor=0a0014)
![Version](https://img.shields.io/badge/VERSION-1.0.0-22d3ee?style=for-the-badge&labelColor=0a0014)

## Overview

Cortex Coach transforms any workout plan into device-ready FIT files using AI. This landing page showcases the product with a distinctive cyberpunk aesthetic.

## Features

- **Responsive Design** — Works seamlessly on mobile, tablet, and desktop
- **Cyberpunk Aesthetic** — Unique 80s sci-fi inspired visual identity
- **Interactive Terminal Demo** — Live workout conversion simulation
- **Particle Animation** — Canvas-based background effects
- **Single File Deployment** — All CSS/JS inline for easy hosting

## Quick Start

### GitHub Pages Deployment

1. Fork or clone this repository
2. Go to **Settings** → **Pages**
3. Under "Source", select **Deploy from a branch**
4. Select **main** branch and **/ (root)** folder
5. Click **Save**

Your site will be live at `https://yourusername.github.io/repo-name/`

### Local Development

Simply open `index.html` in a browser — no build step required.

```bash
# Using Python's built-in server
python -m http.server 8000

# Using Node's http-server
npx http-server
```

## File Structure

```
├── index.html      # Main landing page (self-contained)
├── README.md       # This file
├── .nojekyll       # Prevents Jekyll processing
└── CNAME           # Custom domain (optional)
```

## Customization

### Updating Content

All content is in `index.html`. Key sections to modify:

- **Pricing** — Update `$3/month` and `$2/month` values
- **Features** — Modify feature cards in the features section
- **FAQ** — Edit questions and answers in the FAQ section

### Color Palette

CSS variables are defined at the top of the `<style>` block:

```css
:root {
    --cyber-purple: #9f7aea;
    --cyber-cyan: #22d3ee;
    --cyber-pink: #ec4899;
    --cyber-yellow: #fbbf24;
    --cyber-green: #22c55e;
    --cyber-red: #ef4444;
    --bg-dark: #0a0014;
}
```

### Typography

- **Display Font**: Orbitron (Google Fonts)
- **Monospace Font**: Share Tech Mono (Google Fonts)

## Tech Stack

- **HTML5** — Semantic markup
- **CSS3** — Custom properties, Grid, Flexbox, animations
- **Vanilla JS** — No frameworks, minimal footprint
- **Google Fonts** — Orbitron + Share Tech Mono

## Performance

- No external dependencies (except Google Fonts)
- Minified inline CSS (~15KB)
- Lightweight particle system (~60 particles)
- Lazy intersection observer for scroll animations

## Browser Support

- Chrome 80+
- Firefox 75+
- Safari 13+
- Edge 80+

## Custom Domain Setup

1. Create a `CNAME` file with your domain:
   ```
   cortexcoach.com
   ```
2. Configure DNS:
   - Add a CNAME record pointing to `yourusername.github.io`
   - Or add A records pointing to GitHub's IPs

## Email Signup Integration

The email form currently logs submissions to console. To connect to your email service:

1. Replace the `handleSignup()` function with your API call
2. Popular options:
   - Mailchimp
   - ConvertKit
   - Buttondown
   - Custom backend

Example with fetch:
```javascript
function handleSignup(e) {
    e.preventDefault();
    const email = document.getElementById('emailInput').value;
    
    fetch('https://your-api.com/subscribe', {
        method: 'POST',
        body: JSON.stringify({ email }),
        headers: { 'Content-Type': 'application/json' }
    })
    .then(() => {
        document.getElementById('signupForm').style.display = 'none';
        document.getElementById('signupSuccess').style.display = 'block';
    });
}
```

## License

MIT License — Feel free to use and modify for your projects.

---

**Built for Cortex Coach** — The Neural Interface for Elite Training

