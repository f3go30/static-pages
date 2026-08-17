# static-pages (multi-app static host)

Static content published via GitHub Pages ("deploy from a branch", `main`/root). Originally
F3Go30-only; now shared by more than one app, each namespaced under its own top-level folder —
same multi-app-per-static-host convention as `nuuc-it/Static`'s `pub/` (`pub/AS`, `pub/AS-sit`, ...).

This repo holds only built output — it is not hand-edited. Each app's source lives in its own
project repo; that project's `tools/publish-static-pages.js` (+ `build-static-pages.js`) builds
and pushes the result here as the last step of its own deploy.

## Layout

```
dist/
  sit/            <- F3Go30 SIT build,  https://f3go30.github.io/static-pages/dist/sit/
  prod/           <- F3Go30 PROD build, https://f3go30.github.io/static-pages/dist/prod/
ballot/
  sit/            <- RankChoiceVoting SIT build,  https://f3go30.github.io/static-pages/ballot/sit/
  prod/           <- RankChoiceVoting PROD build, https://f3go30.github.io/static-pages/ballot/prod/
```
