---
title: Cloudflare Workers
---

To deploy to [Cloudflare Workers](https://workers.cloudflare.com/), use [`adapter-cloudflare-workers`](https://github.com/sveltejs/kit/tree/master/packages/adapter-cloudflare-workers).

Unless you have a specific reason to use this adapter, we recommend using [`adapter-cloudflare`](adapter-cloudflare) instead.

> Requires [Wrangler v2](https://developers.cloudflare.com/workers/wrangler/get-started/).

## Usage

Install with `npm i -D @sveltejs/adapter-cloudflare-workers`, then add the adapter to your `svelte.config.js`:

```js
// @errors: 2307
/// file: svelte.config.js
import adapter from '@sveltejs/adapter-cloudflare-workers';

export default {
	kit: {
		adapter: adapter()
	}
};
```

## Basic Configuration

This adapter expects to find a [wrangler.toml](https://developers.cloudflare.com/workers/platform/sites/configuration) file in the project root. It should look something like this:

```toml
/// file: wrangler.toml
name = "<your-service-name>"
account_id = "<your-account-id>"

main = "./.cloudflare/worker.js"
site.bucket = "./.cloudflare/public"

build.command = "npm run build"

compatibility_date = "2021-11-12"
workers_dev = true
```

`<your-service-name>` can be anything. `<your-account-id>` can be found by logging into your [Cloudflare dashboard](https://dash.cloudflare.com) and grabbing it from the end of the URL:

```
https://dash.cloudflare.com/<your-account-id>
```

> You should add the `.cloudflare` directory (or whichever directories you specified for `main` and `site.bucket`) to your `.gitignore`.

You will need to install [wrangler](https://developers.cloudflare.com/workers/wrangler/get-started/) and log in, if you haven't already:

```
npm i -g wrangler
wrangler login
```

Then, you can build your app and deploy it:

```sh
wrangler publish
```

## Custom config

If you would like to use a config file other than `wrangler.toml`, you can do like so:

```js
// @errors: 2307
/// file: svelte.config.js
import adapter from '@sveltejs/adapter-cloudflare-workers';

export default {
	kit: {
		adapter: adapter({ config: '<your-wrangler-name>.toml' })
	}
};
```

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

## Troubleshooting

### Accessing the file system

You can't access the file system through methods like `fs.readFileSync` in Serverless/Edge environments. If you need to access files that way, do that during building the app through [prerendering](https://kit.svelte.dev/docs/page-options#prerender). If you have a blog for example and don't want to manage your content through a CMS, then you need to prerender the content (or prerender the endpoint from which you get it) and redeploy your blog everytime you add new content.