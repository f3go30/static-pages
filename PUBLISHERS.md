# f3go30/static-pages — published static front ends

This repo is a **static host**, served by GitHub Pages ("deploy from a branch", `main`/root) at
<https://f3go30.github.io/static-pages/>. Originally F3Go30-only; now shared by more than one app,
each namespaced under its own top-level folder — the same multi-app-per-static-host convention as
`nuuc-it/Static`'s `pub/`.

## Rules

1. **This repo holds built output only. It is never hand-edited.** Every file here was written by a
   build in the project repo that owns it; an edit made here is lost at that project's next deploy.
2. **Each folder's content is owned 100 % by exactly one project repo.** No other repo ever writes
   into it. Because the paths are disjoint, two projects publishing at the same time can never
   produce a content conflict — a publish that finds the branch has moved rebases and pushes.
3. **A new folder is registered here first.** GAS-Core's `gas-static` publish pipeline reads the
   JSON block below and **refuses** to publish to a folder that is not listed, or one listed against
   a different project. Adding a folder is a deliberate, reviewed two-line edit in this repo.
4. Source for any page lives in its owning project repo, not here.

## Who publishes what

| Folder | Owning project repo | Env | Live URL |
|---|---|---|---|
| `dist/sit` | F3Go30 (`tools/build-static-pages.js` + `publish-static-pages.js`) | sit | <https://f3go30.github.io/static-pages/dist/sit/> |
| `dist/prod` | F3Go30 (same pipeline, PROD build) | prod | <https://f3go30.github.io/static-pages/dist/prod/> |
| `ballot/sit` | RankChoiceVoting (`tools/publish-static-pages.js`, SIT target) | sit | <https://f3go30.github.io/static-pages/ballot/sit/> |
| `ballot/prod` | RankChoiceVoting (same pipeline, PROD target) | prod | <https://f3go30.github.io/static-pages/ballot/prod/> |

RankChoiceVoting also publishes a single-environment build to `nuuc-it/Static` at `pub/ballot` —
see that repo's `PUBLISHERS.md`.

## Ownership map

The block below is read by `gas-static`'s publish guard (GAS-Core `adr/0003`). Keys are paths
relative to this repo's root; `project` must match the publishing project's declared `projectName`.
Keep it in step with the table above.

```json
{
  "dist/sit": { "project": "F3Go30", "env": "sit", "url": "https://f3go30.github.io/static-pages/dist/sit/" },
  "dist/prod": { "project": "F3Go30", "env": "prod", "url": "https://f3go30.github.io/static-pages/dist/prod/" },
  "ballot/sit": { "project": "RankChoiceVoting", "env": "sit", "url": "https://f3go30.github.io/static-pages/ballot/sit/" },
  "ballot/prod": { "project": "RankChoiceVoting", "env": "prod", "url": "https://f3go30.github.io/static-pages/ballot/prod/" }
}
```
