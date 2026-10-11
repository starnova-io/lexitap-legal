# lexitap-legal

Public landing / support page for the LexiTap app, served by GitHub Pages at
https://starnova-io.github.io/lexitap-legal/

## Why this repo exists

AdMob verifies app-ads.txt at the **root of the developer-website domain** on the
App Store listing. `lexitap-legal` gives LexiTap a listing URL under
`starnova-io.github.io`, whose root already serves:

```
google.com, pub-3847722511208491, DIRECT, f08c47fec0942fa0
```

That single file covers every app pointed at this host, so no per-app file is
needed. Before this, LexiTap's listing pointed at
`https://api.devx.im/lexitap-service/privacy`, and `api.devx.im/app-ads.txt` is a
404 because that host is an API, not a static site.

## One source of truth for the legal text

The Privacy Policy and Terms of Use are **not** copied here. They are canonical in
`lexitap-service/app/legal.py`, which is served by the app's own backend:

- https://api.devx.im/lexitap-service/privacy
- https://api.devx.im/lexitap-service/terms

That module deliberately keeps the text next to the code that does the collecting.
Copying it here would create a second copy that can silently drift out of date —
which is worse than a link, because a stale privacy policy is a false statement
rather than a broken link. This page links to those URLs instead.
