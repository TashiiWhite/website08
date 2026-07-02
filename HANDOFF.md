# Signature Auto — session handoff

Paste this as your first message in a new Claude Code session on the other machine (after cloning/copying this repo) to restore context.

## What this is
A single-page, high-end marketing website for **Signature Auto**, a mobile mechanic
business. Built with the `design-taste-frontend` skill (anti-slop landing page
conventions: dark theme, restrained motion, bento service grid, no AI-tell clichés).

Services covered: tire change, tire balance, oil change, system diagnostics,
brake change, detailing, car wash.

## Repo state
- Local git repo initialized in this folder (`signature-auto/`), not inside a
  larger parent repo. Single commit so far: `1f6ee10` "Add Signature Auto mobile
  mechanic landing page".
- **No remote configured yet.** Nothing has been pushed anywhere.
- Working tree is clean as of this handoff.

## Files
- `index.html` — the entire site (plain HTML/CSS/vanilla JS, no build step,
  no framework). Fonts via Fontshare (Satoshi), icons via Phosphor CDN.
- `assets/hero.png`, `assets/wheel.png`, `assets/diagnostic.png`,
  `assets/detailing.png` — AI-generated photography (marketing_studio_image
  model) used across hero, service bento grid, and detailing band.

## Design decisions worth knowing
- Dark theme locked page-wide (`--bg: #0e0f11`), single accent color
  `--accent: #e8622c` (burnt orange), used consistently for CTAs, icons, eyebrow text.
- One corner-radius system: pill buttons (`999px`), 18px panels (`--r-panel`).
- Hero: asymmetric split (copy left, generated photo right), max 4 text
  elements, fits in viewport, no scroll cue.
- Services shown as a 7-cell bento grid with real photography in 2 of the
  cells (not all-text tiles) plus one accent-colored cell for Detailing.
- Motion: IntersectionObserver-based scroll reveals only — no
  `window.addEventListener('scroll')`, respects `prefers-reduced-motion`.
- Zero em-dashes anywhere in copy (per skill's hard ban).
- Phone number and email in the site are placeholders
  (`(682) 341-9057`, `hello@signatureauto.co`) — replace with real business
  contact info before going live.

## Outstanding / not yet done
1. **No local preview was completed in-browser.** The user interrupted the
   PowerShell static-server setup (`.claude/serve.ps1` + `.claude/launch.json`
   under `Downloads/`, not inside this repo) before it ran. If picking this
   back up, either recreate that server or use any static file server /
   the Preview tool to sanity-check the page renders correctly (fonts,
   images, mobile breakpoint, dark mode) before calling it done.
2. **No remote/push yet.** User wants this pushed to a git remote. Need a
   remote URL (GitHub/GitLab etc.) — `gh` CLI is not installed on the
   original machine, so the repo has to be created manually or `gh` needs
   to be installed and authenticated.
3. Git identity was auto-derived as `Tashii White <tashii.white@iguzzini.com>`
   from the machine hostname on the original PC — confirm/fix this on
   whichever machine ends up owning the canonical history, or amend
   before the first push.
4. No favicon, no OG/meta image, no analytics — none were requested, flagging
   in case follow-up work wants them.

## Next likely steps
- Push to a remote and open in a browser to visually verify.
- Swap placeholder phone/email for real ones.
- Optionally add a favicon and Open Graph tags for link previews.
