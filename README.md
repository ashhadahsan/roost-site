# roost-site

Marketing site for [Roost](https://github.com/ashhadahsan/roost) — the Postgres-backed background job queue for Python.

Static. Astro 6 + Tailwind 4. ~100KB total bundle. Deploys anywhere that serves files.

## Local

```bash
npm install
npm run dev      # http://localhost:4321
npm run build    # static output in dist/
npm run preview  # preview the prod build
```

## Pages

- `/` — landing (hero, demo, features, architecture)
- `/comparison` — Roost vs Celery / RQ / dramatiq / arq / procrastinate / pgqueuer
- `/recipes` — eight focused patterns (FastAPI / Django / cron / chaining / rate limit / wait / auth / typed args)

## Deploy

### Cloudflare Pages (recommended)

```bash
npm run build
npx wrangler pages deploy dist --project-name=roost-site
```

Or connect this repo to Cloudflare Pages with build command `npm run build` and output directory `dist`.

### Vercel / Netlify

Build command `npm run build`, output directory `dist`, Node 22+.

## Structure

```
src/
├── layouts/Base.astro        # navbar + footer + meta tags
├── components/
│   ├── Hero.astro            # hero + code teaser
│   ├── Demo.astro            # 3-step quickstart
│   ├── Features.astro        # 9-card feature grid
│   └── Architecture.astro    # ASCII diagram + 3 primitives
├── pages/
│   ├── index.astro
│   ├── comparison.astro
│   └── recipes.astro
└── styles/global.css         # @theme tokens + code block hand-tuning
```

## License

MIT.
