# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a single-file Hebrew RTL landing page for an AI consulting and automation business targeting small and medium businesses in Israel. The entire site lives in `index.html` — no build tools, no framework, no dependencies beyond a Google Fonts CDN link.

To preview the page, open `index.html` directly in a browser (no server needed).

## Architecture

The entire codebase is `index.html`, which contains:
- Inline `<style>` block with all CSS (using CSS custom properties defined in `:root`)
- Semantic HTML sections in order: `<nav>`, `.hero`, `.value-prop`, `.benefits`, `.cta-strip`, `.contact`, `<footer>`
- No JavaScript

**CSS design system** (`:root` variables):
- `--primary` (#0f172a) — dark navy backgrounds
- `--accent` (#3b82f6) — blue for highlights and icons
- `--whatsapp` / `--whatsapp-dark` (#25d366 / #1db954) — all CTA buttons
- `--text`, `--muted`, `--light`, `--border` — content typography and layout

**RTL/Hebrew**: The page uses `lang="he" dir="rtl"` and `direction: rtl` on `body`. All content is in Hebrew. The font is Heebo (loaded from Google Fonts).

## Key Details

**WhatsApp links**: All CTAs link to `https://wa.me/972500000000` with URL-encoded Hebrew pre-filled messages. The phone number `972500000000` is a placeholder — update it in all four occurrences across the file when deploying.

**Placeholder contact info** in `.contact-card`:
- Name: `פאולה הרשקו`
- Phone: `054-9932138`
- Email: `autollab.ai@gmail.com`

**WhatsApp SVG icon** is inlined repeatedly (4 times) rather than extracted to a reusable component — this is intentional given the single-file architecture.

**Responsive breakpoint**: Single breakpoint at `max-width: 640px` collapses the benefits grid to single column and reduces padding.
