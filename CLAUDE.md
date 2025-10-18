# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

ENIGMA 47 is a single-page luxury jewelry website (enigma47.mx) built with vanilla HTML, CSS, and JavaScript. The site showcases artisanal jewelry with a minimalist, high-end aesthetic focused on storytelling and brand identity.

## Architecture

### Single-File Structure
The entire website is contained in `index.html` with embedded CSS and JavaScript. This is intentional for simplicity and deployment ease.

### Key Sections (in order)
1. **Hero** - Main logo, tagline, and CTA button
2. **Statement** - Brand positioning statement with fade-in animation
3. **Triptych** - Three core values (Autenticidad, Legado, Consciencia) with geometric shapes
4. **Essence** - Mission statement with decorative lines
5. **Enigma** - Brand story with large background logo
6. **Connection** - Email signup form with EmailJS integration
7. **Footer** - Social links (Instagram, Facebook, WhatsApp) and business address

### Design System

**Color Variables** (defined in `:root`):
- `--negro`: #000000 (primary text/borders)
- `--blanco-hueso`: #f2eee9 (primary background)
- `--beige-arena`: #e7e2d6 (secondary background)
- `--marron-terracota`: #b19173 (accent)
- `--gris-topo`: #bbaa94 (accent)

**Typography**:
- Headers/serif: Georgia, Times New Roman
- Body: -apple-system, BlinkMacSystemFont, Segoe UI, Roboto

**Key Interactions**:
- Custom cursor with smooth follow animation and blend mode
- Intersection Observer for scroll-triggered fade-ins
- Parallax effect on hero section
- Email validation with animated submit arrow

## External Dependencies

- **Font Awesome 6.4.0** (CDN) - Icons for social media links
- **EmailJS** (CDN) - Email form handling (currently configured for mailto fallback)
- **Formspree** - Primary email service (needs form ID configured at line 910)

## Development Workflow

### Local Development
Open `index.html` directly in a browser. No build process required.

### Deployment
The site is deployed to Vercel (evidenced by `.vercel` in `.gitignore`). Simply push to the main branch.

### Email Form Setup
The email form at line 898-960 uses:
1. Primary: Formspree (requires updating `YOUR_FORM_ID` at line 910)
2. Fallback: `mailto:enigma47joyeria@gmail.com`

## Important Implementation Details

### Responsive Breakpoints
- Mobile: `max-width: 768px`
- Extra small: `max-width: 480px`

### Animation System
All animations use Intersection Observer (lines 833-858) with:
- 0.3 threshold for visibility
- Staggered delays for triptych items (0.1s, 0.2s, 0.3s)
- CSS transitions controlled by `.visible` class

### Custom Cursor
The cursor system (lines 798-830) uses:
- `requestAnimationFrame` for smooth interpolation
- `mix-blend-mode: difference` for contrast on all backgrounds
- Scale transform on interactive element hover

## Content Management

The site is in Spanish and targets the Mexican luxury market. Business information:
- Physical location: Galerías Monterrey, Nivel 1
- Address: Av. Insurgentes 2500 col. Vista Hermosa, Monterrey, N.L. 64620
- Contact: WhatsApp +52 81 1988 9060

## SVG Assets

Three logo variations are used:
- `main-logo.svg` - Hero section
- `secondary-logo.svg` - Footer
- `tertiary-logo.svg` - Enigma section background

These should maintain consistent brand identity if replaced.
