# ox_lib (AshFall RP fork of ox_lib)

This repo is AshFall RP's fork of [overextended/ox_lib](https://github.com/overextended/ox_lib).

## Rules

- **The server folder is named `ox_lib`**: resources that call `exports.ox_lib:*` and `@ox_lib/init.lua` keep working.
- **Keep each patch small, on its own commit,** with a message starting `af:`, and list it below.
- Keep upstream files stock whenever possible.

## Pulling upstream updates

```sh
git remote add upstream https://github.com/overextended/ox_lib.git   # once
git fetch upstream
git merge upstream/main
```

## Our patches

- **`af: route notifications to qbx_core:client:notify`**: In `resource/interface/client/notify.lua`, `lib.notify` forwards to `qbx_core:client:notify` when `af_core` or `qbx_core` is running. This unifies all `ox_lib` notifications across all server resources with the server's notification system.
- **`af: precompiled web/build`**: Tracked production build in `web/build` so FiveM can run `ox_lib` directly without needing external node/bun build steps on server launch.
