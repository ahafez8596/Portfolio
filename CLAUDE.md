# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static personal portfolio website - a single-page application built with vanilla HTML5, CSS3, and JavaScript (ES6+). No build tools or external dependencies required.

## Development

```bash
# Run locally (choose one)
python -m http.server 8000
npx http-server
# Or simply open index.html directly in a browser
```

## Architecture

**Single-File Structure**: The entire application is contained in `index.html` (~700 lines) with embedded CSS and JavaScript.

**Content Management**: Portfolio content is stored in JavaScript data objects at the bottom of the file:
- `PROJECTS` - Featured project cards
- `CERTS` - Certifications list
- `SKILLS` - Skills organized by category (Languages, Frameworks, Databases, Tools)
- `EXPERIENCE` - Work history timeline

To update content, modify these objects directly - the DOM is rendered dynamically from this data.

**Theme System**: Dark mode is default. Theme toggling works via CSS custom properties defined at `:root` level, with `.light` class applied to toggle themes. User preference persists in localStorage.

**Key Patterns**:
- `el()` helper function creates DOM elements programmatically
- IntersectionObserver handles scroll-triggered animations
- Three-layer parallax star background using CSS box-shadow technique
- Glassmorphism effects with CSS backdrop-filter

## Deployment

Deploy `index.html` directly to any static host (GitHub Pages, Vercel, Netlify). No build step needed.
