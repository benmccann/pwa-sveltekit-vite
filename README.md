# SvelteKit, Vite 3.1 and PWA Plugin

## Latest Changes: 2022-09-07

Updated PWA Plugin with https://github.com/antfu/vite-plugin-pwa/pull/370 local copy (we need to fix types).

Added logic that will go to the SvelteKit integration: check Vite config file.

**WARNING**: SvelteKit not updated, failing post install script when installing latest version (474).

**WARNING**: current version failing on build running the adapter, I need to fix it.

## 2022-08-31

**UPDATED to Vite 3.1.0-beta1 and latest SvelteKit 1.0.0-next.454**:
- hacking `VitePluginPWA` to configure the new `Rollup` sequential hook in `closeBundle`: check the `vite.config.js` module (**DON'T DO THIS**, we're preparing a new version to support Vite 3.1)
- migrated project with `pnpm dlx svelte-migrate routes`
- requires `node 16.14+`: tested with `node 16.17.0 LTS`.

## OLDER ENTRIES

**WARNING - DON'T USE THIS**: we're awating Rollup and Vite to add sequential parallel hooks support:
- RFC: https://github.com/vitejs/vite/discussions/9442
- Rollup PR (Lukas Taegert-Atkinson and Anthony Fu): https://github.com/rollup/rollup/pull/4600
- Vite PR (Anthony Fu): https://github.com/vitejs/vite/pull/9634

Finally!, it works.

Using a local build of the PWA PR: https://github.com/antfu/vite-plugin-pwa/pull/327.

If you had a previous version, just remove the `node_modules` and run `pnpm install`.

To test it just run:
- `pnpm run build && pnpm run preview` or
- `pnpm run build && pnpm run https` to test with https
