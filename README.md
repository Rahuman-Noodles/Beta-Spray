# Beta Spray — PM Portfolio Project

A fully interactive product prototype for a social bouldering platform. Built as a PM portfolio piece to showcase user segmentation, jobs-to-be-done framework, and end-to-end feature design.

---

## The Idea

Climbers currently use 4–5 disconnected tools to manage their climbing life: Mountain Project for route research, paper logbooks or spreadsheets to track sends, Instagram to share beta, Discord or Reddit to talk about technique, and Google Maps to find gyms.

**Beta Spray** is a single platform that brings it all together. The core insight: climbers are intensely social about their sport — they film each other constantly, obsess over technique, and celebrate every send — but none of that social energy is captured in any existing app. It lives in DMs, story mentions, and gym-floor conversations that disappear.

---

## PM Framework: How I Got Here

### 1. User Segmentation

Rather than designing for all climbers, I identified three distinct behavioral segments with meaningfully different needs:

| Segment | % of Climbers | Core Behavior | Current Pain |
|---|---|---|---|
| **Gym Regulars** | ~55% | Session 2–4x/week, social, grade-motivated | No way to track progress or share sends without leaving the gym ecosystem |
| **Outdoor Climbers** | ~30% | Route-research heavy, travel to crags, beta-hungry | Beta is scattered across Mountain Project, YouTube, and random Reddit threads |
| **Coaches & Setters** | ~15% | Content creators, technique teachers, route builders | No dedicated platform to share expertise; forced onto Instagram which buries context |

**Primary target: Gym Regulars** — largest segment, highest session frequency = best retention opportunity. Secondary: Outdoor Climbers for content depth and long-tail engagement.

### 2. Jobs-to-be-Done

**Gym Regulars:**
> *"When I finally send a hard project, I want to log it and share the moment with my climbing friends, so they can celebrate with me and I can track my progression over time."*
> 
> Current workaround: Text friends manually, post to Instagram (no context), or just don't document it at all.

**Outdoor Climbers:**
> *"When I'm projecting a route at an unfamiliar crag, I want to find specific beta from someone who's sent it recently, so I don't waste limited outdoor sessions figuring out moves from scratch."*
>
> Current workaround: Comb through 5-year-old Mountain Project comments, post to Reddit, or DM strangers on Instagram.

**Coaches & Setters:**
> *"When I set a new problem or develop a training insight, I want to share it with climbers who'll actually use it, so my knowledge has impact beyond my own gym."*
>
> Current workaround: Instagram (no search, no context, no longevity) or YouTube (high production bar, not mobile-first).

### 3. Solutions Mapped to Segments

| Feature | Target Segment | Key Metric |
|---|---|---|
| **Beta Clips** — 15–30s video pinned to specific routes | All segments | Clips posted per DAU |
| **Send Logbook** — grade pyramid, attempt tracking, style tags | Gym Regulars | Logbook entries per user per week |
| **Social Feed** — reactions, comments, follow graph | Gym Regulars | D7/D30 retention lift |
| **Gym Discovery** — reset dates, crowd levels, membership compare | Gym Regulars | Gym page visits → day pass bookings |
| **Route Search** — searchable by grade, style, location, setter | Outdoor Climbers | Beta clip views from search |

### 4. Prioritization (RICE)

| Feature | Reach | Impact | Confidence | Effort | Score | Phase |
|---|---|---|---|---|---|---|
| Send Logbook | High | High | Very High | Low | **9.2** | 1 — MVP |
| Social Feed + Reactions | High | High | High | Medium | **8.1** | 1 — MVP |
| Beta Clips (video) | Medium | Very High | Medium | High | **7.0** | 1 — MVP |
| Gym Discovery | Medium | High | High | Medium | **6.8** | 2 |
| Route Search | Medium | Very High | Medium | High | **6.5** | 2 |
| Coaching Tools | Low | High | Medium | High | **4.5** | 3 |

**Why logbook first:** It's the killer retention hook. Once a climber has 20+ sends logged, the switching cost to leave the platform becomes very high — their history lives here. This is the equivalent of Strava's "your running history" lock-in.

---

## Features Built in This Prototype

### Feed
- Post beta clips with route name, grade, gym, and caption
- Like posts, toggle emoji reactions (🔥 💡 👏)
- Trending routes rail — see what's getting sent at your gym today
- Follow suggested climbers
- Compose button opens full post modal with clip type selection

### Logbook
- Grade pyramid — visual representation of your send distribution, animates on load
- Recent sends table — route, grade, style, date, attempts
- Log a Send modal — route name, grade, gym, hold style chips (Crimp, Sloper, Compression etc.), attempt counter, notes
- New sends post to feed automatically and appear in logbook instantly

### Discover
- Gym cards showing distance, route count, member count, rating
- Reset date badge (critical info for climbers — fresh routes = reason to visit)
- Click through to gym profile

### Profile
- Peak grade, current project, session streak
- Beta clip grid — your personal library of sends
- Stats: total sends, followers, following

---

## Success Metrics I'd Track

| Metric | Target | Why |
|---|---|---|
| **Weekly Logbook Entries** | North Star | Direct proxy for core habit formation — if people log, they retain |
| D30 Retention | 45%+ | Climbing is a habitual sport; D30 should be high if we nail the logging loop |
| Beta Clip Posts per DAU | >0.3 | Measures content health; if no one posts, feed dies |
| Send → Share Rate | 60%+ | What % of logged sends get posted to feed — viral loop indicator |
| Gym Discovery → Visit | Track UTM to gym bookings | Validates the discovery use case; enables B2B gym partnerships |
| Avg Grade Progression | +0.5 grades / 3 months | Product health metric — are climbers actually improving with Beta Spray? |

---

## Risks & Mitigations

| Risk | Mitigation |
|---|---|
| Content cold start — empty feed kills early retention | Seed with coach/setter content; partner with 3 gyms for launch cohort |
| Video hosting costs scale fast | Start with 30s cap + compression; explore gym-sponsored storage model |
| Mountain Project / Strava have data moats | Focus on social layer MP lacks; integrate with Strava for run/strength cross-training data |
| Niche audience limits growth ceiling | Bouldering is the fastest-growing gym sport globally — TAM is expanding rapidly |
| Grade sandbagging (community trust) | Community-reported grades with consensus system, like OpenBeta |

---

## Why Bouldering Specifically

Bouldering (vs. rope climbing) is the ideal product beachhead:
- **No gear barrier** — show up and climb, massive growth in urban gym openings
- **Short sessions** — 1–2 hours, high frequency, perfect for habit loop products
- **Naturally social** — problems are short enough that groups watch and cheer each other; beta is shared constantly on the floor
- **Grade obsession** — V-grades create a clear progression system that maps perfectly to gamification and tracking features

---

## Tech Stack (Prototype)
Single-file HTML/CSS/JS — no dependencies, no build step required.

**If built for real:**

| Layer | Stack |
|---|---|
| Frontend | React Native (iOS + Android — mobile is where climbers live) |
| Web | React + TypeScript |
| Video | Cloudflare Stream (cost-effective, global CDN) |
| Backend | Node.js + PostgreSQL |
| Search | Algolia (route search by grade, style, location) |
| Auth | Auth0 |
| Maps | Mapbox (gym discovery, crag locations) |
| Analytics | Mixpanel (funnel: discover → log → share → return) |

---

## How to Run

```bash
# Option 1: Just open it
open beta-spray.html

# Option 2: Local server
npx serve .
# → http://localhost:3000/beta-spray.html
```
---
*Built as a PM portfolio project. Concept, research framework, and prototype by Rahul Adusumalli.*
