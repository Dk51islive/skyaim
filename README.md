# Momentum Agency - Frontend scaffold

Includes:
- React + Vite + Tailwind starter
- Consent banner, analytics wrapper (GA4 + Plausible)
- Accessibility helpers (Skip link, sr-only utilities)
- Contact form wired to Mailgun serverless function (Netlify / Vercel compatible)
- Pa11y and Lighthouse CI config examples

## Setup
1. Install deps: `npm install`
2. Add env vars (for local dev put in .env):
   - `VITE_GA_ID=G-XXXXXXX`
   - `VITE_PLAUSIBLE_DOMAIN=yourdomain.com`
   - `MAILGUN_DOMAIN=...`
   - `MAILGUN_API_KEY=...`
3. Start dev: `npm run dev`

## A11Y Checks
- Run `npm run test:a11y` for pa11y checks
- Use Lighthouse CI for automated performance & accessibility thresholds

## Notes
- The analytics wrapper respects user consent stored in localStorage.
- Contact form posts to `/.netlify/functions/contact-mailgun` (Netlify functions). If using Vercel, adapt the function path to `/api/contact-mailgun`.
