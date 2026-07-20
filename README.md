# WorldFirst × AFA — World Cup campaign dashboard

Meta Ads data for the twelve campaigns that ran under the WorldFirst × AFA sponsorship,
17 June to 20 July 2026: match-moment reactive posts, the signed-jersey draw, the
Mastercard card reveal, the World Card registration push, and the final-weekend burst.

Live: https://socialworldfirst.github.io/worldcup-campaign-dashboard/

Password gated (`wf`). Content is AES-GCM encrypted client-side with PBKDF2 key
derivation, so the figures are not readable from source or git history.

## Source

Meta Ads API, ad account KR Post `1915691362502143` (USD), WorldFirst page
`126600647086`, `@worldfirst` on Instagram. Pulled 20 July 2026 with
`date_preset=maximum`.

## Build

`build.py` holds the campaign data inline and is gitignored for that reason. It renders
the inner HTML, encrypts it, and writes `index.html`. `fetch_images.py` pulls the
creative stills from the Meta CDN into `img/` so the page is self-contained.

```
python3 fetch_images.py   # once, or when creative changes
python3 build.py          # writes index.html
```

## Scope

Excluded: the UK World Card traffic flight `120251291102340127`, which runs in the same
account and window but on non-AFA creative. Organic reach is excluded — this is boosted
delivery only. Registration and activation outcomes live in the WorldFirst backend, not
in Meta, and are not represented here.
