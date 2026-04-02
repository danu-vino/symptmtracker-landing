# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Marketing landing page for **Symaura**, a privacy-first health tracking iOS app. The site hosts a landing page, privacy policy, and terms of service — required for the App Store subscription submission.

- **Hosting:** Cloudflare Pages (auto-deploy from `main` branch on GitHub)
- **App Store:** https://apps.apple.com/us/app/my-symptoms-tracker/id6747646417
- **Developer:** Venture Melody (info@venturemelody.com)

## Deployment

Push to `main` to deploy. Cloudflare Pages auto-deploys — no build step.

## Architecture

Static site — three self-contained HTML files with inline CSS/JS. No build tools, no frameworks, no external stylesheets.

| File | Purpose |
|------|---------|
| `index.html` | Landing page — hero with app screenshots, feature showcases, privacy section, pricing, CTA |
| `privacy-policy.html` | Privacy policy with Apple-required subscription auto-renewal language |
| `terms.html` | Terms of service with medical disclaimer and billing terms |
| `assets/` | App screenshots (PNG) used in phone-frame mockups on the landing page |

### How the landing page is structured

The page flows as: nav → hero (with phone-frame screenshot) → trust bar → three showcase sections (daily check-in, insights, history — each pairs a phone screenshot with feature bullets) → pro feature grid → AI chat showcase → privacy section → pricing cards → CTA → footer.

All icons are **inline SVGs** (no emoji, no icon fonts). They use `stroke: currentColor` to inherit color from CSS.

Phone screenshots are displayed inside CSS phone frames (dark background + border-radius + padding) with a fixed `height: 520px` and `overflow: hidden` to crop the tall iPhone screenshots proportionally.

### Design System

- **Fonts:** Instrument Serif (display headings) + Outfit (body) via Google Fonts
- **Primary color:** `--teal: #1B434D` — used for nav, buttons, headings, phone frames
- **Accent color:** `--green: #7CB342` — used for highlights, check marks, feature accents
- **Background:** `--bg: #FAFBF9` (warm off-white)
- CSS custom properties are defined in `:root` at the top of `index.html`
- JS is ~40 lines: nav scroll effect, mobile hamburger menu, IntersectionObserver scroll-reveal, smooth anchor scrolling

### Key Constraints

- Privacy policy and terms **must** include subscription auto-renewal language for Apple review
- AI Chat feature sends anonymized data to **OpenAI API** via Cloudflare Worker — disclosed in privacy policy section 4
- Pricing: Free / Pro Monthly $4.99/mo / Pro Annual $34.99/yr (founding members: $2.99/mo or $24.99/yr)
- Copy rule: use "free to start", never "free to use"
- All pages must attribute to **Venture Melody** (not personal name)

## Branding

| Element | Value |
|---------|-------|
| Display name | Symaura |
| Primary color | `#1B434D` (teal) |
| Tagline | "Your health, tracked with care" |
| Contact | info@venturemelody.com |
