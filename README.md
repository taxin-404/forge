# ⬡ Forge — Free Developer Tools

8 essential developer tools built with Astro. Runs entirely in your browser — no server, no tracking, no cost.

## Tools

| Tool | Description |
|------|-------------|
| **JSON** | Format, validate, minify, sort keys |
| **Base64** | Encode/decode text and files |
| **Hash** | SHA-1/256/384/512 via Web Crypto API |
| **UUID** | Bulk RFC-4122 v4 UUID generation |
| **Color** | HEX ↔ RGB ↔ HSL + palette generator |
| **Timestamp** | Unix ↔ Human date converter + live clock |
| **Regex** | Live regex tester with match highlighting |
| **Diff** | Line-by-line text comparison |

## Tech Stack

- **Framework**: [Astro](https://astro.build) (static output)
- **Hosting**: [Cloudflare Pages](https://pages.cloudflare.com) (free tier)
- **Fonts**: Space Mono (Google Fonts)
- **No JS frameworks** — vanilla TypeScript in Astro script tags
- **No backend** — everything runs client-side
- **No dependencies** except Astro itself

---

## Local Development

```bash
# Install dependencies
npm install

# Start dev server
npm run dev
# → http://localhost:4321

# Build for production
npm run build

# Preview production build
npm run preview
```

---

## Deploy to Cloudflare Pages (Free)

### Option 1 — GitHub + Cloudflare Dashboard (Recommended)

1. Push this repo to GitHub
2. Go to [Cloudflare Dashboard](https://dash.cloudflare.com) → **Workers & Pages** → **Create**
3. Click **Connect to Git** → select your repo
4. Set build settings:
   - **Framework preset**: Astro
   - **Build command**: `npm run build`
   - **Build output directory**: `dist`
   - **Node.js version**: `20` (set in Environment Variables: `NODE_VERSION = 20`)
5. Click **Save and Deploy**

Done! You get a free `.pages.dev` domain. Every push to `main` auto-deploys.

### Option 2 — Wrangler CLI

```bash
# Install Wrangler
npm install -g wrangler

# Login to Cloudflare
wrangler login

# Build + deploy
npm run build
wrangler pages deploy dist --project-name=forge-tools
```

---

## Custom Domain (Free)

1. In Cloudflare Pages → your project → **Custom domains**
2. Add your domain (must be on Cloudflare DNS)
3. Done — automatic HTTPS, no cost

---

## Environment Variables (Cloudflare Pages)

None required. All tools are purely client-side.

---

## Project Structure

```
forge/
├── public/
│   └── favicon.svg
└── src/
    ├── layouts/
    │   └── Layout.astro        # Base layout, global CSS, sidebar nav
    ├── components/
    │   └── PageHeader.astro    # Reusable page header
    └── pages/
        ├── index.astro         # Home / tool grid
        ├── json.astro          # JSON formatter
        ├── base64.astro        # Base64 encoder/decoder
        ├── hash.astro          # Hash generator
        ├── uuid.astro          # UUID generator
        ├── color.astro         # Color converter
        ├── timestamp.astro     # Timestamp converter
        ├── regex.astro         # Regex tester
        └── diff.astro          # Text diff
```

---

## License

MIT — free to use, modify, and deploy.
