# Decisions: site

_Append-only. Add new entries at the bottom and never edit or delete old ones._

## 2026-11-06: Fold the site into the typo workshop
**Why:** one place for all Typo Labs work. Cloned rather than copied, to keep history and the GitHub link.

## 2026-11-06: Host on Cloudflare instead of GitHub Pages
**Why:** free GitHub Pages requires a public repo. Cloudflare is free, works with private repos, allows commercial use, and offers server functions for API keys (needed by filo and english).
**Alternatives considered:** Vercel (free plan is non-commercial only), Netlify (path routing is fiddlier), GitHub Pro (static only).

## 2026-11-06: Ideas live at typolabs.io/<idea> as separate Cloudflare projects
**Why:** keeps one repo per idea. Each idea deploys independently and is attached with a Cloudflare route (`typolabs.io/<idea>*`). Each idea must be built to work under its subpath.

## 2026-11-06: typolabs.co forwards to typolabs.io
**Why:** one canonical site. Done with Porkbun URL forwarding (301, include path).
