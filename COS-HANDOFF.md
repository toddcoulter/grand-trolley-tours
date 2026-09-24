# CoS handoff — Grand Trolley soft-launch site

**As of:** Thu Sep 17, 2026  
**Agent did not change** `toddcoulter/jarvis-core` product code.

## Blocker

Cursor’s GitHub App token can only see **`toddcoulter/jarvis-core`** (private). It cannot create repositories (`createRepository` → 403, resource not accessible by integration).

`toddcoulter/grand-trolley-tours` is **not taken**. Alternate names under the same user also fail for the same permission reason (not a name collision).

## What is ready

One-page coming-soon site, verified locally (desktop + ~390px mobile):

- Brand: **The Grand Trolley**
- Soft-launch only: **Coming soon** — no licensed / insured / book-now / currently-operating claims
- Footer: **Grand Traverse Trolley, LLC · Rapid City, MI**
- Contact: `mailto:info@grandtrolleytours.com` and `(855) 430-6321`
- Drive folder: https://drive.google.com/drive/folders/1u9vovPurX0kcRMl0KSxCBhCWg4ePyEOF
- Local package: `/home/ubuntu/grand-trolley-tours`

## Todd / CoS — finish in ~2 minutes

1. While logged in as **toddcoulter**, create the public repo:

```bash
gh repo create toddcoulter/grand-trolley-tours \
  --public \
  --description "The Grand Trolley — soft-launch site for grandtrolleytours.com" \
  --disable-wiki
```

Or: https://github.com/new → name `grand-trolley-tours` → Public.

2. Grant the **Cursor GitHub App** access to that repo (or All repositories).

3. Push this folder to `main`, then **Settings → Pages** → Deploy from branch → `main` / root.

4. Pages custom domain: `grandtrolleytours.com` (CNAME file is already in the tree). **Then** change GoDaddy DNS (not before).

## Intended URLs (after step 3)

| What | URL |
|------|-----|
| Repo | https://github.com/toddcoulter/grand-trolley-tours |
| Pages | https://toddcoulter.github.io/grand-trolley-tours/ |
| Custom domain (after DNS) | https://grandtrolleytours.com |

## GoDaddy DNS (exact)

Leave parking IPs in place until Pages custom domain is saved. Then replace them.

**A** `@` → `185.199.108.153` / `185.199.109.153` / `185.199.110.153` / `185.199.111.153`  
**AAAA** `@` → `2606:50c0:8000::153` / `2606:50c0:8001::153` / `2606:50c0:8002::153` / `2606:50c0:8003::153`  
**CNAME** `www` → `toddcoulter.github.io`

Remove GoDaddy parking `A` records `13.248.243.5` and `76.223.105.230`. No wildcard. No `ALIAS` (GoDaddy cannot). Then Enforce HTTPS on Pages.

Full table and `dig` checks: `README.md` in this folder.
