# Community merge log

Fork: `mjanker4247/calibre-web`  
Base before pass: `janeczku/calibre-web` @ `6e840acb` (0.6.28b, identical)  
Pass date: 2026-11-09  
Result tip: see `git log upstream/master..HEAD`

Goal: pull important useful patches from open contributor PR forks that upstream has not merged. Skip noise, conflicting WIP, Bootstrap 5 Develop rewrite, and product forks (CWA / NextGen / autocaliweb).

## Merged this pass (19)

| PR | Author / branch | Title |
| --- | --- | --- |
| #3744 | kayaal34 | Fix log messages with mismatched format arguments |
| #3738 | courville | Add more french articles in the title sorting |
| #3726 | hippi345 | Restore stored settings when a configuration save is refused |
| #3725 | hippi345 | Serve thumbnails on the OPDS thumbnail routes |
| #3712 | LaoChouPro | Serve the OpenSearch description with the correct content type |
| #3720 | Juice-de-Orange | Don't deep copy all authors for the authors list |
| #3689 | lpinner | Hide read books from Discover (#2588) |
| #3717 | kossoy | Fix data loss when uploading an additional book format |
| #3713 | FaintLocket424 | Ensure parent author directory exists before moving book |
| #3711 | JSmid6 | Trust X-Forwarded-For for REMOTE_ADDR behind trusted proxy |
| #3682 | bit-incarnas | Fix EPUB3 cover detection via `properties="cover-image"` |
| #3707 | 0xhanlie | EPUB 3 belongs-to-collection metadata |
| #3739 | courville | Configurable download file name format |
| #3724 | splitsec2 | Reverse proxy login: optional Cloudflare Access JWT verify |
| #3352 | xdgc | Kobo sync bugfixes |
| #3701 | xarthurx | Fix Douban cover preview/download (CDN hotlink / HTTP 418) |
| #3729 | IgorKurkov | Probe Wand/ImageMagick once (faster startup without IM) |
| #3607 | leahjessie | Fix remaining Kobo "Sync to last page read?" popup |
| #3358 | dotknott | Kobo sync: include subtitle from custom columns |

## Tried, conflicted (not merged)

| PR | Author | Title | Reason |
| --- | --- | --- | --- |
| #3381 | AsherMaximum | Updated metadata/covers/deleted books on Kobo Sync | Conflict in `cps/kobo.py` after #3352/#3607/#3358 |
| #3394 | AsherMaximum | Re-download on Kobo when book file changed | Conflict in `cps/kobo.py` |

## Skipped this pass

| Source | Reason |
| --- | --- |
| `upstream/Develop` (28 commits, Bootstrap 5) | Large WIP UI rewrite; defer wholesale merge |
| #3743 Project analysis | Not a product change |
| #3736 pylint baseline | Noise / tooling dump |
| #3733 in-browser MOBI reader | Huge (+4500); defer |
| #3730 Wand→Pillow | Large dependency swap; overlaps #3729 |
| #3734 PDF range optimization | Defer; needs careful review over slow links |
| #3369 reverse-proxy env overrides | CONFLICTING with upstream |
| #3630 series sort by date added | CONFLICTING |
| #3685 Authentik OIDC | CONFLICTING; large auth surface |
| #3287 new EPUB reader | Huge (+4970); defer |
| #3645 / #3647 composite/second series | Large features; defer |
| #3513 EPUB reader columns | Larger UI change; defer |
| #3177 Kobo metadata sync | Draft |
| #2799 auto-create LDAP users | Auth behavior change; defer |
| `crocodilestick/Calibre-Web-Automated` | Different product (automation layer) |
| `new-usemame/Calibre-Web-NextGen` | CWA continuation; different product |
| `gelbphoenix/autocaliweb` | Archived / moved; different product |

## Remotes kept

- `origin` → `mjanker4247/calibre-web`
- `upstream` → `janeczku/calibre-web`

Local `pr-*` branches are throwaway fetch refs for merges.

## How to continue

```bash
git fetch upstream
# pick more from: gh pr list -R janeczku/calibre-web --state open
git fetch upstream pull/<N>/head:pr-<N>
git merge --no-ff pr-<N> -m "<title> Merge pull request #<N> from <author>"
# update this file
```
