# Speclint

A linter for AI-generated brand creative.

Gooseworks ([gooseworks.ai](https://gooseworks.ai)) writes its design rules as markdown so its agents can render on-brand ad creative without a person reviewing every result. That system is open source at [gooseworks-ai/goose-skills](https://github.com/gooseworks-ai/goose-skills). Speclint takes a few of those same rules, real style specs and a real legibility threshold pulled from their own QA file, and gives them a visual, testable form a person can use directly.

Live tool: [index.html](index.html)
Case study: [case-study.html](case-study.html)

## What it does

Three screens:

1. **Catalog** — a visual gallery of design specs (colors, type, mood) rendered as real swatches and components, not hex codes on a page. Two are modeled on Gooseworks' own published presets, sourced and linked. One is an original spec written in the same format.
2. **Compile** — pick a spec, watch it drive a live ad-card component through CSS custom properties. Switch specs, the component re-skins instantly, the markup never changes.
3. **Lint** — pick a deliberately broken version of the ad and watch real, computed checks run against the live DOM: WCAG contrast ratio, color distance from the spec's accent, legibility at a 256px thumbnail (the exact threshold from Gooseworks' own `verifier.md`), and safe-margin overflow. Failures draw a box on the exact offending element with the real number attached.

Nothing in the checks is hardcoded. They're standard formulas (WCAG relative luminance, Euclidean RGB distance) run against whatever's actually rendered in the browser at that moment.

## Status

An independent project built while researching Gooseworks' Design Engineer role, not affiliated with or endorsed by Gooseworks. No backend, no AI API calls, no login. Everything on screen is either sourced from Gooseworks' public repo (linked in the UI) or clearly marked as an original spec.

## Stack

Single-file HTML, CSS, and vanilla JavaScript. No build step, no dependencies beyond Google Fonts (IBM Plex Sans, IBM Plex Mono, Archivo Black, Space Grotesk, Cormorant).
