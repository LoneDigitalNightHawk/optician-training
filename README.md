# VHDO Training Curriculum

Live site: **https://lonedigitalnighthawk.github.io/optician-training/**

Interactive training for Visual Health Doctors of Optometry, built as plain self-contained HTML — no build step, no dependencies. Push to `master` and GitHub Pages redeploys automatically in ~1 minute.

## Structure

| File | What it is | Status |
|---|---|---|
| `index.html` | Curriculum landing page (all 9 modules + roadmap) | Live |
| `module1.html` | Module 1 — Welcome & Corporate Anatomy | Live |
| `module2.html` | Module 2 — Foundations of Opticianry & Medical Basics | Live |
| `part2.html` | Interim sales training ("What We Sell") — folds into Modules 4 & 6 | Live |
| `part1.html` | Legacy URL — redirects to `module2.html` | Redirect only |

Modules 3–9 (Lab Ecosystem, Insurance Matrix, EPM Mastery, Clinical Sales, OM/TD/OD tracks) are **in development** — owned by the training team: Kat, Erla, Natalia, Sherief, Zee.

## Adding a module

1. Copy `module1.html` to `moduleN.html` — it's the cleanest template (styles + quiz engine in one file).
2. Replace the chapters (each is a `<section class="chapter">` with a `<div class="quiz" data-ch="N">`).
3. Update the `QUIZ` object in the `<script>` at the bottom — one key per chapter, 3 questions each, and keep `a:0` (first option is always the correct one; options are auto-shuffled at render).
4. Change `var KEY="vhdo-train-m1"` to a unique key (e.g. `vhdo-train-m3`) so progress doesn't collide.
5. Update `total=5` in `refresh()` and the static `— / 15` score to match your chapter/question count.
6. On `index.html`, convert the module's `<div class="card dev">` into an `<a class="card live" href="moduleN.html">` with a `Start Module N` link.

Look for the gold **"Training team — to complete"** callout boxes inside Module 1 — those mark real content gaps (org chart, office contacts, system provisioning) waiting on the team.

## Ground rules

- Numbers quoted in training come from real VHDO sales data (`sales-analysis` in the source workspace). Don't invent statistics — mark unknowns with a note callout instead.
- No patient names, PHI, or credentials in this repo, ever. It is public.
- Keep pages self-contained: no external scripts, fonts, or CDNs.
