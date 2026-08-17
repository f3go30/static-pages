# ballot — RankChoiceVoting static front end

Static content for the RankChoiceVoting app. Built from that repo's
`static-pages/src/index.html` by `tools/build-static-pages.js` and published here by
`tools/publish-static-pages.js`, as the last step of `npm run deploy:sit` / `npm run deploy:prod`
(`tools/manage-deployments.js`). Not hand-edited — see the RankChoiceVoting repo for source.

- `sit/`  — https://f3go30.github.io/static-pages/ballot/sit/
- `prod/` — https://f3go30.github.io/static-pages/ballot/prod/

Each build calls its GAS deployment's `?cmd=api` JSON endpoint as its backend (baked in at
build time from `local.settings.json`'s `sitDeploymentId`/`prodDeploymentId` — see
RankChoiceVoting's `script/ApiBridge.js` for the server side).
