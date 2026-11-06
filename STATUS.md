# Status: site

**Last updated:** 2026-11-06

## Current state
Moving hosting from GitHub Pages to Cloudflare. The site content (index.html plus logos) is unchanged. A DNS snapshot from before the move is in the session notes; iCloud email records must survive the move.

## Next steps
1. Cloudflare: add typolabs.io; check the imported DNS records, especially the email ones.
2. Porkbun: switch nameservers to Cloudflare's.
3. Cloudflare: connect this repo, then attach typolabs.io and www.typolabs.io.
4. Turn off GitHub Pages, archive the `CNAME` file, and make the repo private.
5. Porkbun: forward typolabs.co to https://typolabs.io (301).

## Blockers
None.

## Open questions
- Home page design: how to list or link the ideas.
