# Arys AI

AI chat interface powered by OpenRouter, deployed on Cloudflare Workers + GitHub Pages.

---

## Deploy in 3 steps

### Step 1 — Deploy the Worker (backend)

1. Install Wrangler: `npm install -g wrangler`
2. Login: `wrangler login`
3. Add your OpenRouter API key as a secret:
   ```
   wrangler secret put OPENROUTER_API_KEY
   ```
4. Deploy the worker:
   ```
   npm run deploy
   ```
5. Copy the Worker URL shown after deploy (e.g. `https://arys-ai.YOUR_USERNAME.workers.dev`)

### Step 2 — Update the frontend

Open `frontend/js/config.js` and replace the `API_URL` with your Worker URL:

```js
API_URL: "https://arys-ai.YOUR_USERNAME.workers.dev/api/chat",
```

### Step 3 — Deploy the frontend (GitHub Pages)

1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Set source to the `frontend/` folder (or use a `docs/` copy)
4. Your site will be live at `https://YOUR_USERNAME.github.io/YOUR_REPO`

---

## Models used (via OpenRouter)

- DeepSeek Chat V3 (primary)
- DeepSeek R1 (fallback)
- Qwen 3.5 122B (fallback)

Get your OpenRouter API key at https://openrouter.ai/keys
