```
 ██████╗  ██████╗  ██████╗
 ██╔══██╗ ██╔══██╗ ██╔══██╗      DENSITY · DAILY · DESIGN
 ██║  ██║ ██║  ██║ ██║  ██║      ──────────────────────────────
 ██║  ██║ ██║  ██║ ██║  ██║      five tasks · sequential · 365 days
 ██████╔╝ ██████╔╝ ██████╔╝      v1.0 · kinoshita studio · 2026
 ╚═════╝  ╚═════╝  ╚═════╝       updated: 2026-04-20
```

<p align="center">
  <img src="https://img.shields.io/badge/stack-vanilla_JS-0B111F?style=flat-square" alt="stack">
  <img src="https://img.shields.io/badge/deps-tailwind_cdn-0B111F?style=flat-square" alt="deps">
  <img src="https://img.shields.io/badge/storage-localStorage-E13437?style=flat-square" alt="storage">
  <img src="https://img.shields.io/badge/offline-first-E13437?style=flat-square" alt="offline">
  <img src="https://img.shields.io/badge/license-MIT-0B111F?style=flat-square" alt="license">
</p>

---

A ritual task app for people who know **five is plenty**.
One HTML file. Sequential completion. 365-day density grid.
**No cloud. No account. No streak anxiety — only a mirror.**

```
open app.html
```

That's the install. Or visit the live build:

```
https://ddd-app.github.io/ddd/app.html
```

---

## The rules

```
5 tasks max per day        — if it doesn't fit, it's a next-day thought
tasks run top-down         — the second task locks until the first is done
durations from 1 to 180    — the timer honors what you set
today acts, past archives  — finished days are read-only
the grid sees everything   — dense weeks glow, light weeks stay dim
```

---

## What's in v1.0

```
FOCUS              today's five + date-nav · plan future, audit past
                   inline editing · 1–180 min per task · sequential lock

LOG                365-day density grid (GitHub-style, ink & red)
                   streak · best day · active days · click any cell → FOCUS

TIMER              Time Timer aesthetic · red conic-gradient sweep
                   60 tick SVG overlay · START · PAUSE · RESET · COMPLETE

TERMINAL (new)     right dock on desktop / bottom dock on mobile
                   drag edge to resize · persisted in localStorage
                   commands: light / dark / help / stats / today / about
                   version / clear / reset today

THEMES (new)       dark (ink ground · default) / light (paper · ink text)
                   type `light` or `dark` in the terminal — persisted

CALENDAR           custom month view · tap any day to jump
                   green dot = tasks exist · brighter = all done

TOUCH              horizontal swipe between views (mobile)
                   safe-area-inset respected on iPhone
                   haptic-light button press (no vibration API)
```

---

## Philosophy

**Five tasks.** Anything more is a wish, not a plan.
**Sequential.** No skipping — finish the first or change your life.
**Density, not count.** The grid rewards showing up, not perfection.
**Local.** Your data is on your disk. No server, no sync, no spy.
**Subtractive.** One file. Tailwind CDN + a little CSS. Zero build.

---

## Quick start

```sh
# no install. open directly:
open app.html

# or serve locally (recommended for Safari):
python -m http.server 8000
# → http://localhost:8000/app.html
```

---

## Terminal commands

```
> help / ?            list every command
> light / dark        theme toggle (persisted across sessions)
> today               today's task count + completion
> stats               total completed · best day · streak · active days
> about               DDD ASCII logo + philosophy
> version             build info + storage keys
> clear / flush       wipe the terminal log
> reset today         (requires confirmation)
> reset today yes     actually clears today's tasks
```

---

## Shortcuts

```
Enter              submit (new task / save edit / cast command)
Esc                close calendar / cancel edit
↑ / ↓              command history in terminal
Swipe ← / →        next / previous view (mobile)
Drag term edge     resize terminal panel
```

---

## Data model

```
state                                 (persisted to localStorage / ddd.v1)
├── tasksByDate
│   └── YYYY-MM-DD: [
│         { id, text, durationMin, done, completedAt }, ...
│       ]
└── timer
    └── { taskId, duration, remaining, startedAt, paused }

prefs                                 (persisted to localStorage / ddd.prefs.v1)
├── theme     dark | light
├── termW     panel width in px (desktop)
└── termH     panel height in px (mobile)
```

Nothing leaves the browser.

---

## Files

```
ddd/
├── app.html          ← the entire engine · one file · all v1.0 features
├── index.html        ← product landing page
├── og-image.svg      ← OGP social preview (1200×630)
└── README.md         ← you are here
```

---

## Stack

```
render       HTML + CSS Grid + conic-gradient (timer)
input        pointer events · swipe (touch) · keyboard (enter / esc / ↑↓)
storage      localStorage (ddd.v1 + ddd.prefs.v1)
styling      Tailwind CDN + inline CSS custom tokens
font         Space Mono (Google Fonts)
theming      body.ddd-light class · paper ↔ ink swap
terminal     fixed dock + drag resize + history + dispatcher
```

---

## Deploy

GitHub Pages. No build, no CI, no config.

```
https://ddd-app.github.io/ddd/app.html
```

Push. Done.

---

## Contact

```
feedback   →  blackmirror.board@gmail.com     (shared studio inbox)
              subject: DDD Feedback

studio     →  kinoshita studio · shiga · japan
x          →  @bmboards               x.com/bmboards
instagram  →  @bmboard.official        instagram.com/bmboard.official

dev log    →  99letters.github.io/md.html
```

---

<p align="center">
  <em>Five tasks a day. Keeps the chaos away. — kinoshita studio / 2026-04-20</em>
</p>
