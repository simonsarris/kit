---
title: Cloudflare Pages
---

To deploy to [Cloudflare Pages](https://developers.cloudflare.com/pages/), use [`adapter-cloudflare`](https://github.com/sveltejs/kit/tree/master/packages/adapter-cloudflare).

This adapter will be installed by default when you use [`adapter-auto`](/docs/adapter-auto), but adding it to your project is recommended so that `event.platform` is automatically typed.

## Comparisons

- `adapter-cloudflare` – supports all SvelteKit features; builds for [Cloudflare Pages](https://blog.cloudflare.com/cloudflare-pages-goes-full-stack/)
- `adapter-cloudflare-workers` – supports all SvelteKit features; builds for Cloudflare Workers
- `adapter-static` – only produces client-side static assets; compatible with Cloudflare Pages

> Unless you have a specific reason to use `adapter-cloudflare-workers`, it's recommended that you use this adapter instead. Both adapters have equivalent functionality, but Cloudflare Pages offers features like GitHub integration with automatic builds and deploys, preview deployments, instant rollback and so on.

## Usage

Install with `npm i -D @sveltejs/adapter-cloudflare`, then add the adapter to your `svelte.config.js`:

```js
// @errors: 2307
/// file: svelte.config.js
import adapter from '@sveltejs/adapter-cloudflare';

export default {
	kit: {
		adapter: adapter()
	}
};
```

## Deployment

Please follow the [Get Started Guide](https://developers.cloudflare.com/pages/get-started) for Cloudflare Pages to begin.

When configuring your project settings, you must use the following settings:

- **Framework preset** – None
- **Build command** – `npm run build` or `svelte-kit build`
- **Build output directory** – `.svelte-kit/cloudflare`
- **Environment variables**
	- `NODE_VERSION`: `16`

> You need to add a `NODE_VERSION` environment variable to both the "production" and "preview" environments. You can add this during project setup or later in the Pages project settings. SvelteKit requires Node `16.14` or later, so you should use `16` as the `NODE_VERSION` value.

## Environment variables

The [`env`](https://developers.cloudflare.com/workers/runtime-apis/fetch-event#parameters) object, containing KV/DO namespaces etc, is passed to SvelteKit via the `platform` property along with `context` and `caches`, meaning you can access it in hooks and endpoints:

```js
// @errors: 7031
export async function POST({ request, platform }) {
	const x = platform.env.YOUR_DURABLE_OBJECT_NAMESPACE.idFromName('x');
}
```

To make these types available to your app, reference them in your `src/app.d.ts`:

```diff
/// file: src/app.d.ts
declare namespace App {
	interface Platform {
+		env?: {
+			YOUR_KV_NAMESPACE: KVNamespace;
+			YOUR_DURABLE_OBJECT_NAMESPACE: DurableObjectNamespace;
+		};
	}
}
```

> `platform.env` is only available in the production build. Use [wrangler](https://developers.cloudflare.com/workers/cli-wrangler) to test it locally

## Notes

Functions contained in the `/functions` directory at the project's root will _not_ be included in the deployment, which is compiled to a [single `_worker.js` file](https://developers.cloudflare.com/pages/platform/functions/#advanced-mode). Functions should be implemented as [server endpoints](https://kit.svelte.dev/docs/routing#server) in your SvelteKit app.

The `_headers` and `_redirects` files specific to Cloudflare Pages can be used for static asset responses (like images) by putting them into the `/static` folder.

However, they will have no effect on responses dynamically rendered by SvelteKit, which should return custom headers or redirect responses from [server endpoints](https://kit.svelte.dev/docs/routing#server) or with the [`handle`](https://kit.svelte.dev/docs/hooks#server-hooks-handle) hook.

## Troubleshooting

### Accessing the file system

You can't access the file system through methods like `fs.readFileSync` in Serverless/Edge environments. If you need to access files that way, do that during building the app through [prerendering](https://kit.svelte.dev/docs/page-options#prerender). If you have a blog for example and don't want to manage your content through a CMS, then you need to prerender the content (or prerender the endpoint from which you get it) and redeploy your blog everytime you add new content.
