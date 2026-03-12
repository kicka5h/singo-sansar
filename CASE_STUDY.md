# Case Study: Singo Sansar Website

**Client:** Singo Sansar
**Industry:** Non-Profit / Community Development
**Region:** Sarlahi District, Madhesh Province, Nepal
**Stack:** HTML · CSS · Vanilla JavaScript

---

## Overview

Singo Sansar — meaning "the whole world" in Nepali — is a non-profit organization working to provide women in the Sarlahi region of Nepal with employment training and financial literacy skills. The organization required a clean, inspirational public-facing website that could communicate their mission to potential donors, volunteers, and partners, showcase their community through photography, and provide a direct contact channel — all without the overhead of a backend or ongoing hosting infrastructure.

---

## Challenge

The client needed a website that could serve several goals simultaneously while remaining simple enough for a non-technical team to maintain and update independently:

- **Mission communication** — clearly convey the organization's purpose and programs to an international audience unfamiliar with the Sarlahi region
- **Community representation** — give prominent space to photography of the region and its people, treating the images as a core part of the storytelling rather than decoration
- **Contact accessibility** — provide a direct way for interested parties to reach the organization without requiring a server, database, or form-handling service
- **Maintainability** — the team needed to be able to swap photos, update text, and change the contact email without developer assistance

---

## Solution

A fully static single-page website delivered as a single `index.html` file with no build step, no dependencies, and no server requirements. The site can be opened directly in a browser from a local file system or served from any static hosting provider.

### Design & Visual Identity

The color palette was derived directly from the organization's own photography rather than chosen arbitrarily. Sampling across the community photos produced a set of four accent colors used throughout the site:

- **Forest green** (`#1B4A33`) and **gold** (`#C8922A`) — the primary palette, drawn from the landscape and dry-grass harvest imagery
- **Terracotta** (`#C4583A`) — sampled from the vibrant red-orange saris worn in the working photos
- **Teal** (`#2E8B80`) — from the teal fabric and painted architecture in the community photos
- **Lime green** (`#7CA020`) — from a subject's bright green sweater

Each section of the site uses a distinct background tone — alternating between a warm terracotta tint and a light teal tint — to create visual rhythm and section separation without hard borders. Section labels, card accent borders, icon gradients, and interactive elements each draw from this palette in a consistent rotation.

### Page Structure

The site is organized as five scrollable sections accessible via fixed navigation links:

- **Hero** — a full-viewport background photo with headline, subheading, and a scroll prompt
- **Who We Are** — a two-column layout pairing a mission statement with a community photograph, accented with a terracotta left border on the text block
- **What We Do** — four program cards (Vocational Skills Training, Financial Literacy, Community Mentorship, Education Support), each with a colored top border, a matching gradient icon, and a faint community photo behind the card content at low opacity
- **Life in Sarlahi** — a horizontally scrolling photo gallery with snap scrolling, arrow navigation, and click-and-drag support on desktop
- **Get In Touch** — a contact section with a `mailto:` button and a decorative leaf asset positioned at the footer boundary

### Photography Integration

Photography is woven into every section of the site rather than isolated in a single gallery:

- The hero uses a full-bleed background photo with a dark green gradient overlay to keep the text legible
- The About section features a framed community photo alongside the mission text
- Each of the four program cards has a relevant photo rendered at low opacity as a background, chosen to reflect the nature of each program
- The gallery slider presents six community photos in a side-scrolling track with smooth scroll-snap behavior
- Decorative assets (a transparent leaf, a physalis illustration) are placed at low opacity as ambient background elements in the nav and contact sections

### Navigation & Contact

The fixed navigation bar contains text links to the "Who We Are" and "What We Do" sections alongside a terracotta pill button for "Contact Us." On mobile viewports, the text links collapse and only the button remains visible.

The contact section uses a `mailto:` anchor rather than a form, opening the user's default email client with a pre-filled subject line. This eliminates any need for a backend, form-handling service, or third-party integration while still providing a functional contact channel.

---

## Technical Decisions

**No framework or build step.** The entire site is a single `index.html` file. There is no npm, no bundler, no template engine, and no server-side rendering. This keeps the operational footprint at zero — the site can be hosted on GitHub Pages, Netlify, or any static host for free, and the team can edit it in a plain text editor.

**CSS custom properties for theming.** All colors are defined as CSS variables in `:root`, making palette-wide changes a single-line edit. The four photo-derived accent colors are registered alongside the primary palette and referenced consistently throughout the stylesheet.

**Opacity-based photo integration for cards.** Rather than using `<img>` elements with absolute positioning for the program card backgrounds, photos are applied as CSS `background-image` with a white gradient overlay (`linear-gradient(rgba(255,255,255,0.87), ...), url(...)`) . This approach requires no additional HTML elements, degrades gracefully if an image fails to load, and keeps the card content fully legible at all viewport sizes.

**Scroll-snap gallery with drag support.** The photo gallery uses native CSS `scroll-snap-type` and `overflow-x: auto` for touch and trackpad scrolling, supplemented by a JavaScript mouse-drag handler for desktop users. Arrow buttons provide an explicit navigation affordance. This avoids any carousel library dependency while delivering equivalent interactivity.

**Palette sampled from real photos.** Deriving accent colors from the organization's own photography rather than an external brand guide ensures the design feels grounded in the community it represents. Colors were sampled manually from prominent subjects across four photos — clothing, architecture, and landscape — and adjusted slightly for contrast accessibility.

---

## Outcomes

| Area | Result |
| --- | --- |
| Delivery | Single self-contained `index.html`, no dependencies or build step |
| Design | Five-section single-page layout with photo-derived color palette |
| Photography | Integrated across hero, about, program cards, and a six-photo scrolling gallery |
| Contact | Functional `mailto:` button, no backend required |
| Navigation | Fixed nav with section links and a contact button, mobile-responsive |
| Maintainability | Full editing guide (README.md) written for non-technical users |
| Hosting | Compatible with any static host (GitHub Pages, Netlify, etc.) at no cost |
