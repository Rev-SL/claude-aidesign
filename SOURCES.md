# External Skill Sources — Safety Review

Two external skill packs were reviewed for safe use as content/marketing tooling (primarily for
the `content-engine` and `ads-reviewer` agents). **Both passed.** Review date: 2026-07-16.

## 1. coreyhaines31/marketingskills — ✅ SAFE

- **Author:** Corey Haines · **License:** MIT · **Stars:** ~40.2k · **Latest:** v2.6.0 (Jul 2026)
- **What it is:** 50+ marketing skills as markdown (SEO, CRO, copywriting, ads, prospecting,
  pricing, analytics, etc.). Skills are knowledge/workflow prompts, not code.
- **Review:** No shell execution, no external fetches for unauthorized purposes, no credential
  or secret access, no data exfiltration, no hidden instructions. Spot-checked `prospecting`
  (clean; enforces no-scraping compliance guardrails). Install is user-controlled (copy/plugin).
- **Verdict:** Safe to vendor. High-value skills for CC: `prospecting`, `cold-email`, `offers`,
  `pricing`, `copywriting`, `ad-creative`, `launch`, `customer-research`.

## 2. charlie947/social-media-skills — ✅ SAFE (with two operational notes)

- **Author:** Charlie Hills · **License:** MIT · **Stars:** ~1.8k
- **What it is:** Claude skills for social content (voice-builder, post-writer, hook-generator,
  reels-scripting, thumbnails, carousels, analytics-dashboard, etc.).
- **Review:** Spot-checked `niche-research` (the highest-risk skill — it drives a browser). It
  only navigates public sites (Reddit/X/Google) for research, has strong anti-hallucination
  guardrails, and contains no shell/secret/exfiltration instructions. Clean.
- **Operational notes (not safety issues):**
  1. Some skills need paid API keys — `APIFY_API_TOKEN` (post-scorer, reels-scripting) and
     `GOOGLE_AI_API_KEY` (Gemini video/image). Only set these if you use those specific skills.
  2. Browser-driving skills need Claude-for-Chrome or Playwright MCP. Review each such skill's
     `SKILL.md` before first run, since it takes actions in a browser session.
- **Verdict:** Safe to vendor. High-value skills for CC/RED: `voice-builder`, `hook-generator`,
  `post-writer`, `reels-scripting`, `post-scorer`, `content-matrix`.

## How to vendor (when ready)

Copy only the specific skill folders you want into `skills/`, e.g.:

```
# from a local clone of the source repo:
cp -r marketingskills/skills/prospecting        skills/
cp -r social-media-skills/skills/hook-generator  skills/
```

Pin to a reviewed commit rather than tracking `main` blindly, and re-review on update. Do not
wire in the credential/browser skills until you actually need them and have re-read their
`SKILL.md`.
