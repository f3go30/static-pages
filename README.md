# F3Go30 static-pages

Static content for the F3Go30 program, published via GitHub Pages ("deploy from a branch",
`main`/root).

This repo holds only built output — it is not hand-edited. Source lives in the `F3Go30` repo's
`static-pages/src/`; `npm run publish:static-pages` there builds it and pushes the result here
(`tools/publish-static-pages.js`, `tools/build-static-pages.js`).

## Layout

```
dist/
  sit/   <- SIT-stamped build, https://f3go30.github.io/static-pages/dist/sit/
  prod/  <- PROD-stamped build, https://f3go30.github.io/static-pages/dist/prod/
```
