# Invixe Policy Site

Static website hosting legal documents for the Invixe app:

- **Terms of Use** — `terms.html`
- **Privacy Policy** — `privacy.html`
- **Accessibility Statement** — `accessibility.html`

## Local preview

Open `index.html` in a browser, or run a local server:

```bash
python3 -m http.server 8080
```

Then visit [http://localhost:8080](http://localhost:8080).

## Deploy (GitHub Pages)

1. Push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
4. Choose branch `main` and folder `/ (root)`.
5. Save. Your site will be live at `https://<username>.github.io/<repo-name>/`.

## Deploy (Railway)

1. Push this repo to GitHub (or deploy from local with the Railway CLI).
2. In [Railway](https://railway.app), create a **New Project → Deploy from GitHub repo** and select this repository.
3. Railway detects `package.json` and runs `npm start`, which serves the static files on the assigned `PORT`.
4. Open **Settings → Networking → Generate Domain** to get a public URL (e.g. `invixe-policy.up.railway.app`).
5. Optionally add a custom domain under the same Networking section.

No build step — Railway installs `serve` and hosts the HTML files.

## Deploy (Netlify / Vercel)

Drag and drop this folder, or connect the repo. No build step required — static HTML only.

## Link from the app

After deployment, set the URL in the Invixe app:

```ts
// invixe-app/src/config/externalLinks.ts
export const TERMS_POLICY_URL = "https://your-domain.com";
```

Use the root URL (`index.html`) or link directly to `privacy.html` / `terms.html` as needed for App Store / Google Play.

## Contact emails

Update these if your real addresses differ:

| Document        | Email                      |
|-----------------|----------------------------|
| Terms           | support@invixe.com         |
| Privacy         | privacy@invixe.com         |
| Accessibility   | accessibility@invixe.com   |

## Privacy policy notes

The privacy policy was aligned with the current Invixe app codebase (as of July 2026). If you add analytics, crash reporting, ads, or in-app purchases, update `privacy.html` accordingly.
