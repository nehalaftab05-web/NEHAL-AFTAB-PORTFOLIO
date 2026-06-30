# NEHAL-AFTAB-PORTFOLIO


A fully responsive, single-file personal portfolio website built with **vanilla HTML, CSS, and JavaScript**. This is the current, polished iteration of my portfolio — featuring a custom Blue-Black Ocean color system, animated dot-grid hero background, bento stat panel with a live terminal widget, and a fully showcased 13+ project catalog.

**🔗 Live:** [nehalaftab05-web.github.io](https://nehalaftab05-web.github.io)

---

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Sections](#sections)
- [Design System — Ocean Palette](#design-system--ocean-palette)
- [Tech Stack](#tech-stack)
- [File Structure](#file-structure)
- [How to Run](#how-to-run)
- [Deployment](#deployment)
- [Customization Guide](#customization-guide)
- [Evolution Notes](#evolution-notes)
- [Author](#author)

---

## Overview

This portfolio is built around a custom **"Blue-Black Ocean"** color system — a palette derived from a reference image, mapped to five core tones (`#042B44`, `#096B90`, `#A1CCDC`, `#08171E`, `#71B7D5`) and extended into a complete design token system.

Every section, animation, and interaction is hand-written. The entire site is a single `index.html` file — no build tools, no package manager, no framework.

---

## Features

### Visual Design
- **Animated dot-grid hero background** — radial-gradient dot pattern with a slow drift animation, masked into an elliptical vignette
- **Dual glow orbs** — layered, offset-animated `radial-gradient` blobs for atmospheric depth
- **Bento stat panel** — 4 stat tiles (Live Projects, CGPA, Disciplines, Campus Roles) each with an animated progress bar
- **Live terminal widget** — mock `cat about.json` output with syntax-highlighted keys/values and a blinking cursor
- **"Open to Work" pulse indicator** — animated green dot in the nav logo

### Interactivity
- **Active section nav tracking** — `IntersectionObserver` at 35% threshold updates the active nav link in real time as you scroll
- **Scroll reveal system** — staggered fade-in (`.rv`, `.d1`–`.d4`) with `rootMargin` offset for natural timing
- **Bento bar animation trigger** — progress bars animate into view only when their container enters the viewport
- **Hamburger menu** — animated burger icon, full-screen mobile overlay, closes on outside click or link tap
- **Contact form** — client-side validation, `mailto:` handler with pre-filled subject/body, button state feedback

### Responsive Design
- **Fluid typography** via `clamp()` on hero name and section titles
- **Three breakpoints** — 980px (hero bento hides, grids stack), 720px (mobile nav), 480px (single-column skills/footer stack)
- **CSS Grid skills layout** with 1px gap "seams" creating a divided table look, collapsing from 3 → 2 → 1 columns

---

## Sections

| # | Section | Content |
|---|---|---|
| 0 | **Nav** | Logo with pulse indicator, nav links, "Hire Me" CTA, hamburger |
| 1 | **Hero** | Role badges, bio, CTA buttons, bento stat panel + terminal widget |
| 2 | **About** | Bio prose, achievement badges (CGPA, Battle 101, CS50 SQL, TA role, Figma cert), tech stack chips, info cards |
| 3 | **Skills** | 7 skill blocks — Frontend, UI/UX, AI/ML, Programming, Software Dev, Courses & Certs |
| 4 | **Projects** | 11 project cards + GitHub overflow card |
| 5 | **Experience** | 4 timeline-style experience cards — TA role, Photography Society, Battle 101, self-learning |
| 6 | **Contact** | 3 contact links + working contact form |
| — | **Footer** | Logo, copyright with location, social links |

---

## Design System — Ocean Palette

### Core Colors

| Token | Hex | Role |
|---|---|---|
| `--ocean-deep` | `#042B44` | Deepest accent / glow base |
| `--ocean-mid` | `#096B90` | Primary buttons, links |
| `--ocean-sky` | `#71B7D5` | Hover states, gradient highlight |
| `--ocean-mist` | `#A1CCDC` | Light accent (reserved) |
| `--abyss` | `#08171E` | Button hover text contrast |

### Background Stack

| Token | Hex | Usage |
|---|---|---|
| `--bg` | `#07121A` | Page background |
| `--bg2` | `#0A1D28` | Cards, alt sections |
| `--bg3` | `#0D2535` | Inputs, nested elements |
| `--bg4` | `#0F2D40` | Reserved depth layer |

### Text & Borders

| Token | Hex | Usage |
|---|---|---|
| `--txt` | `#E8F4F8` | Primary text |
| `--txt2` | `#8BABB8` | Secondary text |
| `--txt3` | `#4D6E7A` | Muted labels |
| `--br` | `rgba(9,107,144,.25)` | Borders |
| `--br-hover` | `rgba(113,183,213,.45)` | Hover borders |

### Status & Tag Colors

| Token | Hex | Usage |
|---|---|---|
| `--green` | `#3FB950` | Open-to-work indicator, live demo tags |
| `--yellow` | `#E3B341` | Tertiary tag color |
| `--purple` | `#A78BFA` | AI / logic tags |
| `--orange` | `#F97316` | Assembly / capstone tags |

### Typography

| Font | Usage |
|---|---|
| **Inter** (300–900) | Body, headings, UI |
| **JetBrains Mono** (400–600) | Labels, badges, terminal, code |

### Easing

| Token | Value |
|---|---|
| `--ease` | `cubic-bezier(.22,1,.36,1)` |
| `--ease2` | `cubic-bezier(.4,0,.2,1)` |

---

## Tech Stack

| Technology | Purpose |
|---|---|
| **HTML5** | Semantic structure, full meta/OG tag suite |
| **CSS3** | Custom properties, Grid, Flexbox, `clamp()`, `mask-image`, animations |
| **Vanilla JavaScript** | Nav tracking, scroll reveal, bento animation trigger, contact form |
| **Google Fonts** | Inter + JetBrains Mono via CDN |

**Zero dependencies. Zero npm. Zero build step.**

---

## File Structure

```
portfolio/
│
└── index.html      # Entire site — HTML + CSS + JS, single file
```

---

## How to Run

### Locally

```bash
git clone https://github.com/nehalaftab05-web/nehalaftab05-web.github.io.git
cd nehalaftab05-web.github.io

open index.html        # macOS
start index.html       # Windows
xdg-open index.html    # Linux
```

No server, no build step — open and view.

---

## Deployment

### GitHub Pages

```
1. Repo name must match: nehalaftab05-web.github.io
2. Push index.html to the root of the main branch
3. Settings → Pages → Source: Deploy from branch → main / root
4. Live instantly at https://nehalaftab05-web.github.io
```

> **Note:** Repos named `username.github.io` deploy automatically without needing to enable Pages manually in most cases — but always double check under Settings → Pages.

---

## Customization Guide

| What to change | Where |
|---|---|
| Color palette | `:root` Ocean tokens at top of `<style>` |
| Hero name / bio | `.hero-name`, `.hero-bio` |
| Role badges | `.hero-roles` — add/remove `.rtag` spans |
| Bento stats | `.hero-bento` — update `.bento-num` and `.bento-bar-fill` width |
| Terminal content | `.bento-terminal` block — edit the mock JSON output |
| Skill blocks | `.skills-layout` — each `.sk-block` is self-contained |
| Project cards | `.proj-grid` — duplicate a `.pc` article and edit content |
| Achievement badges | `.badge-row` in About section |
| Social links | `.c-links` in Contact + `.f-soc` in Footer |
| Dot-grid density | `background-size:36px 36px` in `.hero-grid` |
| Glow orb position/size | `.glow-orb.a` / `.glow-orb.b` |

---

## Evolution Notes

This is the **second major iteration** of my portfolio. Compared to the first version, this one introduces:

- A fully custom color system instead of a generic dark theme
- A bento-grid hero layout with live data visualization (animated bars)
- A mock terminal widget for a more "developer-native" feel
- Expanded achievement badges (Battle 101, CS50 SQL, Figma certification)
- A 7th skills category specifically for courses and certifications
- Tighter, more consistent spacing and border system across all cards

---

## Author

**Nehal Aftab**
Roll No: 24F-0518 · BCS-2E · Batch 2024–2028
FAST-NUCES CFD Campus, Faisalabad

[![LinkedIn](https://img.shields.io/badge/LinkedIn-nehal--aftab-blue)](https://linkedin.com/in/nehal-aftab)
[![GitHub](https://img.shields.io/badge/GitHub-nehalaftab05--web-black)](https://github.com/nehalaftab05-web)
[![Email](https://img.shields.io/badge/Email-nehalaftabwork%40gmail.com-red)](mailto:nehalaftabwork@gmail.com)
