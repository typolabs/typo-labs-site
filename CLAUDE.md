# site: typolabs.io

**Pitch:** The Typo Labs home page, and the front door to every idea.
**Repo:** typolabs/typo-labs-site (local folder `~/Desktop/typo/site`)

## Purpose
The main typolabs.io website: the home page plus links into each idea. Each idea (filo, adlib, english…) lives in its own repo and its own Cloudflare project, served at `typolabs.io/<idea>` through a Cloudflare route. This repo only holds the home page; it never contains idea code.

## Stack and hosting
- Plain static HTML and images, with no build step.
- Hosted on **Cloudflare Workers (static assets)**, configured in `wrangler.jsonc`. Cloudflare redeploys automatically when `main` changes on GitHub.
- **Merging to `main` publishes to the live site.** Treat the pull request as the review gate.
- Anything that must not be published goes in `.assetsignore`.
- DNS for typolabs.io is managed at Cloudflare; the domain is registered at Porkbun.
- ⚠️ typolabs.io has **iCloud email**: MX, SPF TXT, `apple-domain` TXT and `sig1._domainkey` CNAME records. Never remove or change those DNS records.

## Commands
- Preview locally: `npx wrangler dev`, then open http://localhost:8787
- Check what would deploy: `npx wrangler deploy --dry-run`

## Session protocol
Same as every idea:
1. Read `STATUS.md`, then the latest entries in `DECISIONS.md`.
2. Run `git status`. If there are uncommitted changes you didn't make, stop and ask.
3. Work on a `claude/<task>` branch, never on `main`.
4. On "wrap up": rewrite `STATUS.md`, append to `DECISIONS.md`, commit, `git push -u origin claude/<task>`, and tell the user how to merge.

## Hard rules
- Never commit on, push to, or work directly on `main`. Never merge; the user merges.
- Never force-push, never `git reset --hard`, never use `--no-verify`, never touch the git hooks.
- Never delete files without asking first.
- Never commit secrets.
- Never change DNS or Cloudflare settings yourself. Tell the user exactly what to click.
