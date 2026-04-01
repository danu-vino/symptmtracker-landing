# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Marketing landing page for **My Symptom Tracker**, a privacy-first health tracking app. The site hosts a landing page, privacy policy, and terms of service — all required before the v1.5.0 App Store subscription submission.

- **Hosting:** Cloudflare Pages (auto-deploy from `main` branch on GitHub)
- **Repo:** `github.com/danu-vino/symptmtracker-landing`
- **Domain:** TBD (Namecheap → Cloudflare DNS)
- **Parent app bundle ID:** `com.danuvino.mysymptomtracker`
- **Developer:** Danu Vino / Venture Melody

## Architecture

Static site — plain HTML/CSS/JS with no build step. Cloudflare Pages serves files directly from the repo root.

### File Structure

| File | Route | Purpose |
|------|-------|---------|
| `index.html` | `/` | Landing page — hero, features, privacy, pricing, CTA |
| `privacy-policy.html` | `/privacy-policy.html` | Privacy policy with Apple-required subscription auto-renewal language |
| `terms.html` | `/terms.html` | Terms of service with medical disclaimer and billing terms |

### Design System

- **Fonts:** Instrument Serif (display) + Outfit (body) via Google Fonts
- **Colors:** `--teal: #1B434D` (primary), `--green: #7CB342` (accent), `--green-light: #A8E6A3`, `--bg: #FAFBF9`
- All CSS is inline (no external stylesheets). JS is minimal (~50 lines for nav scroll, mobile menu, scroll-reveal via IntersectionObserver).
- Legal pages share a consistent header/footer style but are self-contained files.

### Key Constraints

- Privacy policy and terms **must** include subscription-specific auto-renewal language for Apple review
- Pricing: Free / Pro Monthly $4.99/mo / Pro Annual $34.99/yr
- Founding Member legacy pricing: $2.99/mo or $24.99/yr
- AI Chat feature sends anonymized data to Claude API via Cloudflare Worker — disclose in privacy policy
- Copy rule: use "free to start", never "free to use"

## Deployment

Cloudflare Pages auto-deploys from the `main` branch. Push to `main` to deploy.

## Branding

| Element | Value |
|---------|-------|
| Display name | My Symptom Tracker |
| Primary color | `#1B434D` (teal) |
| Tagline | "Your health, tracked with care" |
| Contact | danuvino@gmail.com |

## Reference

Full spec with feature lists, section copy, and legal requirements: `LANDING_PAGE_SPEC.md`
