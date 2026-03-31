# SymptomTrk Landing Page — Spec

## Overview

Marketing landing page for **SymptomTrk**, a privacy-first health tracking app for iOS and Android. The page must also host a privacy policy and terms of service with subscription-specific language — required before the v1.5.0 App Store submission.

---

## Hosting & Deployment

| Detail | Value |
|--------|-------|
| Repo | `github.com/danu-vino/symptmtracker-landing` |
| Hosting | Cloudflare Pages (auto-deploy from GitHub) |
| Domain | TBD — Namecheap registration → Cloudflare DNS |
| Bundle ID | `com.danuvino.mysymptomtracker` |

---

## Branding

| Element | Value |
|---------|-------|
| Display name | **SymptomTrk** |
| Slug / URL name | **symptrack** or **symptmtracker** |
| Primary color | `#1B434D` (teal) |
| Tagline candidate | *"Your health, tracked with care"* |
| Core message | Privacy-first — all data stays on device, encrypted, no accounts |
| Developer | Danu Vino / Venture Melody |

---

## Pages

### 1. Home / Landing Page

**Goal:** Convince visitors to download the app. Highlight privacy-first approach and the free-to-start model.

#### Hero Section
- App name + tagline
- App icon / device mockup
- CTA: Download on the App Store / Get it on Google Play (badge links)
- Short value prop: *"Track symptoms, moods, and health patterns — privately, on your device."*

#### Features Section — Free Tier
| Feature | Description |
|---------|-------------|
| Daily logging | Log symptoms and mood on a 1–5 severity scale |
| Biometric lock | Face ID / Touch ID / Passcode protects your health data |
| Streak tracking | Build consistency with daily logging streaks |
| History view | Browse all past entries at a glance |
| Encrypted storage | All data encrypted on-device — no cloud, no accounts, no sign-up |

#### Features Section — Pro Tier
| Feature | Description |
|---------|-------------|
| AI Chat | Ask Claude AI about your symptom patterns and get personalized insights |
| Advanced Insights | Trend analysis, correlations, and pattern detection across your history |
| Unlimited logging | No cap on symptoms per entry (free tier: 5 max) |
| Backdate entries | Log entries for past days you missed |
| Edit history | Update or correct past entries |
| Custom symptoms | Define your own symptom types beyond the defaults |
| PDF reports | Download doctor-ready reports and logs |

#### Pricing Section
| Tier | Price | Notes |
|------|-------|-------|
| Free | $0 | Free to start — core logging and privacy features included |
| Pro Monthly | $4.99/mo | Full access to all features |
| Pro Annual | $34.99/yr | Save ~42% vs monthly |

> **Copy note:** Use "free to start", never "free to use".

#### Trust / Privacy Section
- "Your data never leaves your device"
- No accounts, no cloud sync, no analytics
- Encrypted with device-bound keys
- Biometric authentication required on every launch

#### Footer
- Links to Privacy Policy and Terms of Service
- Contact: danuvino@gmail.com
- Copyright: Venture Melody

---

### 2. Privacy Policy (`/privacy-policy`)

Must include all of the following for Apple subscription review:

- What data the app collects (health symptoms, mood ratings — stored locally only)
- That no data is transmitted to external servers (except Pro AI Chat, which sends anonymized symptom context to Claude API via Cloudflare Worker)
- How data is encrypted (XOR cipher with device-bound key via expo-secure-store)
- **Subscription terms:**
  - Pricing: $4.99/month or $34.99/year
  - Payment charged to Apple ID / Google Play account at confirmation of purchase
  - Subscription auto-renews unless cancelled at least 24 hours before the end of the current period
  - Account is charged for renewal within 24 hours prior to end of current period
  - Subscriptions can be managed and auto-renewal turned off in Account Settings after purchase
  - No refunds for unused portion of a subscription period
- Founding Member / legacy pricing: $2.99/month or $24.99/year (existing one-time purchasers)
- Data deletion: users can clear all data from Settings → Delete All Data
- Contact information

---

### 3. Terms of Service (`/terms`)

Standard terms covering:

- Acceptance of terms
- Description of the service (health tracking app, not medical advice)
- Medical disclaimer: *"SymptomTrk is not a medical device. It does not diagnose, treat, or prevent any condition. Always consult a healthcare professional."*
- Subscription billing terms (mirror the privacy policy section)
- AI Chat disclaimer: AI responses are informational, not medical advice
- User responsibilities
- Limitation of liability
- Termination
- Contact information

---

## Technical Notes

- Single-page app or static HTML — keep it lightweight
- Responsive: mobile-first design
- Dark mode support recommended (matches the app's dark mode)
- App Store and Google Play badge links (update once store listings are live)
- Consider: simple analytics via Cloudflare Web Analytics (privacy-respecting, no cookies)

---

## Blocking Dependency

This landing page (specifically the privacy policy and terms) **must be live** before submitting v1.5.0 to the App Store. Apple requires:
1. A working privacy policy URL with subscription-specific auto-renewal language
2. A working terms of service URL
3. Both URLs entered in App Store Connect under "App Information"

Current app version: **1.4.7**. The subscription build (v1.5.0) is the next major milestone.
