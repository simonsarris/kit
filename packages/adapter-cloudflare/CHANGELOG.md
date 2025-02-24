# @sveltejs/adapter-cloudflare

## 1.0.4

### Patch Changes

- docs: move adapter docs to site ([#8531](https://github.com/sveltejs/kit/pull/8531))

## 1.0.3

### Patch Changes

- chore: remove superfluous main field from package.json ([#8519](https://github.com/sveltejs/kit/pull/8519))

- Updated dependencies [[`7e2d3405`](https://github.com/sveltejs/kit/commit/7e2d34056e99f371e22406d941b764df365a2649)]:
  - @sveltejs/kit@1.1.1

## 1.0.2

### Patch Changes

- fix: don't load ambient worker types ([#8483](https://github.com/sveltejs/kit/pull/8483))

## 1.0.1

### Patch Changes

- docs: add note about inability to access file system at runtime ([#8441](https://github.com/sveltejs/kit/pull/8441))

- Updated dependencies [[`9c01c32e`](https://github.com/sveltejs/kit/commit/9c01c32ef72bbed630fadcb8283f8f8533ced5e1), [`b6ca02a6`](https://github.com/sveltejs/kit/commit/b6ca02a684dbf13a3138b552e2d2be64697f2254), [`130abe43`](https://github.com/sveltejs/kit/commit/130abe43cef2cfbaf922aa16b20cbd4332a07c15), [`c4137536`](https://github.com/sveltejs/kit/commit/c4137536f2c6572eaeec1a82ccea0852f5be6b98), [`40464efa`](https://github.com/sveltejs/kit/commit/40464efab172a17f0b637d7dadea30d77ef1ed10), [`ce028470`](https://github.com/sveltejs/kit/commit/ce0284708184198efdd30f3ff72fd579cef830b4)]:
  - @sveltejs/kit@1.0.12

## 1.0.0

### Major Changes

First major release, see below for the history of changes that lead up to this.
Starting from now all releases follow semver and changes will be listed as Major/Minor/Patch

## 1.0.0-next.45

### Patch Changes

- breaking: remove warnings/errors about removed/changed APIs ([#8019](https://github.com/sveltejs/kit/pull/8019))
- Updated dependencies [[`f42604a2`](https://github.com/sveltejs/kit/commit/f42604a2b4c04026d3d8bad95807720b79529539)]:
  - @sveltejs/kit@1.0.0-next.589

## 1.0.0-next.44

### Patch Changes

- chore: add peerDependencies, add more specific next version ([#8141](https://github.com/sveltejs/kit/pull/8141))

## 1.0.0-next.43

### Patch Changes

- fix: revert platform change from browser to neutral ([#8122](https://github.com/sveltejs/kit/pull/8122))

## 1.0.0-next.42

### Patch Changes

- fix: set esbuild platform to neutral ([#8083](https://github.com/sveltejs/kit/pull/8083))

## 1.0.0-next.41

### Patch Changes

- update esbuild to ^0.16.3 ([#7543](https://github.com/sveltejs/kit/pull/7543))

## 1.0.0-next.40

### Patch Changes

- update dependencies ([#7355](https://github.com/sveltejs/kit/pull/7355))

## 1.0.0-next.39

### Patch Changes

- Use config.kit.paths.base prefix for static assets ([#4448](https://github.com/sveltejs/kit/pull/4448))

## 1.0.0-next.38

### Patch Changes

- Ensure all excluded paths in `_routes.json` start with / ([#6952](https://github.com/sveltejs/kit/pull/6952))

## 1.0.0-next.37

### Patch Changes

- Support Cloudflare Pages `_routes.json` specification ([#6530](https://github.com/sveltejs/kit/pull/6530))

## 1.0.0-next.36

### Patch Changes

- Include ambient.d.ts files in adapter packages. ([#6917](https://github.com/sveltejs/kit/pull/6917))

## 1.0.0-next.35

### Patch Changes

- fix: return 404 instead of 200 for missing assets ([#6879](https://github.com/sveltejs/kit/pull/6879))

## 1.0.0-next.34

### Patch Changes

- chore: bump esbuild ([#6829](https://github.com/sveltejs/kit/pull/6829))

## 1.0.0-next.33

### Patch Changes

- Update to esbuild 0.15 ([#6740](https://github.com/sveltejs/kit/pull/6740))

## 1.0.0-next.32

### Patch Changes

- feat: Moved hooks.js initialization from Server.respond into Server.init ([#6179](https://github.com/sveltejs/kit/pull/6179))

## 1.0.0-next.31

### Patch Changes

- Initialise `env` ([#5663](https://github.com/sveltejs/kit/pull/5663))

## 1.0.0-next.30

### Patch Changes

- breaking: remove writeStatic to align with Vite ([#5618](https://github.com/sveltejs/kit/pull/5618))

## 1.0.0-next.29

### Patch Changes

- Update dependencies ([#5005](https://github.com/sveltejs/kit/pull/5005))

## 1.0.0-next.28

### Patch Changes

- breaking: Don't pass arbitrary options to esbuild ([#4639](https://github.com/sveltejs/kit/pull/4639))

## 1.0.0-next.27

### Patch Changes

- Expose App interfaces ([#5386](https://github.com/sveltejs/kit/pull/5386))

## 1.0.0-next.26

### Patch Changes

- chore: upgrade TypeScript to 4.7.4 ([#5414](https://github.com/sveltejs/kit/pull/5414))

## 1.0.0-next.25

### Patch Changes

- Expose Cloudflare Worker Cache API through `caches` in Platform ([#5081](https://github.com/sveltejs/kit/pull/5081))

## 1.0.0-next.24

### Patch Changes

- Generate sourcemaps for server-side functions when bundling with esbuild ([#5258](https://github.com/sveltejs/kit/pull/5258))

## 1.0.0-next.23

### Patch Changes

- Update dependencies ([#5121](https://github.com/sveltejs/kit/pull/5121))

## 1.0.0-next.22

### Patch Changes

- Update adapter entrypoint typings to be NodeNext/ESNext-compatible ([#5111](https://github.com/sveltejs/kit/pull/5111))

## 1.0.0-next.21

### Patch Changes

- only serve `_app/immutable` with immutable cache header, not `_app/version.json` ([#5051](https://github.com/sveltejs/kit/pull/5051))

## 1.0.0-next.20

### Patch Changes

- Add types to pkg.exports ([#5045](https://github.com/sveltejs/kit/pull/5045))

## 1.0.0-next.19

### Patch Changes

- breaking: Remove try-catch around server.respond ([#4738](https://github.com/sveltejs/kit/pull/4738))

## 1.0.0-next.18

### Patch Changes

- chore: more restrictive cache lookup & save conditions ([#4669](https://github.com/sveltejs/kit/pull/4669))

## 1.0.0-next.17

### Patch Changes

- Check for Cache match sooner; use `worktop` for types & Cache operations ([#4453](https://github.com/sveltejs/kit/pull/4453))
- Add cloudflare cache to store responses with a cache header. ([#4412](https://github.com/sveltejs/kit/pull/4412))

## 1.0.0-next.16

### Patch Changes

- Provide getClientAddress function ([#4289](https://github.com/sveltejs/kit/pull/4289))

## 1.0.0-next.15

### Patch Changes

- breaking: replace builder.prerender() with builder.writePrerendered() and builder.prerendered ([#4192](https://github.com/sveltejs/kit/pull/4192)) ([#4229](https://github.com/sveltejs/kit/pull/4229))

## 1.0.0-next.14

### Patch Changes

- Bumping versions again ([#4090](https://github.com/sveltejs/kit/pull/4090))

## 1.0.0-next.13

### Patch Changes

- Attempt to force @next version bump ([#4088](https://github.com/sveltejs/kit/pull/4088))

## 1.0.0-next.12

### Patch Changes

- breaking: rename `app.render` to `server.respond` ([#4034](https://github.com/sveltejs/kit/pull/4034))

## 1.0.0-next.11

### Patch Changes

- Add `context` to `event.platform` object ([#3868](https://github.com/sveltejs/kit/pull/3868))

## 1.0.0-next.10

### Patch Changes

- update to Vite 2.8 and esbuild 0.14 ([#3791](https://github.com/sveltejs/kit/pull/3791))

## 1.0.0-next.9

### Patch Changes

- Pass `env` object to SvelteKit via `platform` ([#3429](https://github.com/sveltejs/kit/pull/3429))

## 1.0.0-next.8

### Patch Changes

- Breaking: change app.render signature to (request: Request) => Promise<Response> ([#3384](https://github.com/sveltejs/kit/pull/3384))

## 1.0.0-next.7

### Patch Changes

- Add immutable cache headers to generated assets ([#3222](https://github.com/sveltejs/kit/pull/3222))

## 1.0.0-next.6

### Patch Changes

- use posix to resolve relative path ([#3214](https://github.com/sveltejs/kit/pull/3214))

## 1.0.0-next.5

### Patch Changes

- Overhaul adapter API ([#2931](https://github.com/sveltejs/kit/pull/2931))
- Remove esbuild options ([#2931](https://github.com/sveltejs/kit/pull/2931))
- Update adapters to provide app.render with a url ([#3133](https://github.com/sveltejs/kit/pull/3133))

## 1.0.0-next.4

### Patch Changes

- Updated Cloudflare adapter to allow static files with spaces (eg. "Example File.pdf") to be accessed. ([#3047](https://github.com/sveltejs/kit/pull/3047))

## 1.0.0-next.3

### Patch Changes

- update to esbuild 0.13.15 and other dependency updates ([#2957](https://github.com/sveltejs/kit/pull/2957))

## 1.0.0-next.2

### Patch Changes

- Allow `npm publish` to succeed via `publishConfig.access` config ([#2834](https://github.com/sveltejs/kit/pull/2834))

## 1.0.0-next.1

### Patch Changes

- Add new `adapter-cloudflare` package for Cloudflare Pages with Workers integration ([#2815](https://github.com/sveltejs/kit/pull/2815))

## 1.0.0-next.0

- Initial release
