# AriaNg Cloudflare Worker Template

[![Deploy to Cloudflare](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/knowlet/ariang-cf-template)

<!-- dash-content-start -->

This is an [AriaNg](https://github.com/mayswind/AriaNg) Cloudflare Worker template. It serves a prebuilt, all‑in‑one AriaNg UI as static assets from a Worker, making it easy to deploy AriaNg globally on Cloudflare.

<!-- dash-content-end -->

## Quick Start

Use C3 (`create-cloudflare`) to scaffold a new project from this template:

```bash
bun create cloudflare@latest -- --template=knowlet/ariang-cf-template
```

Then install dependencies and start the dev server:

```bash
bun i
bun dev
```

Open http://localhost:8787 in your browser.

## Prerequisites

- Bun (or Node.js) and a package manager
- Cloudflare account
- Wrangler CLI (installed automatically as a devDependency)
- (Optional) GitHub CLI for upgrading AriaNg via the script below

## Available Scripts

- `bun dev`: Start local development with Wrangler
- `bun start`: Alias of `bun dev`
- `bun run deploy`: Deploy to Cloudflare
- `bun wrangler tail`: View real-time logs
- `bun run upgrade`: Download latest AriaNg AllInOne ZIP and replace assets in `public/`

## Upgrading AriaNg

You can upgrade the AriaNg version by modifying `public/index.html` manually or using the helper script:

```bash
bun run upgrade
```

> [!NOTE]
> `bun run upgrade` requires GitHub CLI. See https://cli.github.com/

## Configuration

Project configuration is managed by `wrangler.jsonc`.

- `name`: The Worker name
- `assets.directory`: Static files directory served at `/` (defaults to `./public`)
- `observability.enabled`: Enables Cloudflare observability

Adjust or extend bindings (KV, R2, D1, AI, etc.) in `wrangler.jsonc` as needed.

## Deploying to Production

- `bun run deploy`: Deploy the Worker
- `bun wrangler tail`: Stream logs

You can also click the "Deploy to Cloudflare" button at the top of this README to deploy directly from GitHub.

## How It Works

This template serves the static AriaNg assets from `public/` using Cloudflare’s static asset support configured in `wrangler.jsonc`.

## License

The AriaNg assets included in `public/` are provided under the MIT license by the original author. See `public/LICENSE` for details.

## Learn More

- AriaNg: https://github.com/mayswind/AriaNg
- Cloudflare Workers + Static Assets: https://developers.cloudflare.com/workers/static-assets/
- Wrangler configuration: https://developers.cloudflare.com/workers/wrangler/configuration/
