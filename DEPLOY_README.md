## Auto-deploy scripts and GitHub Actions

Files added:
- .github/workflows/deploy-vercel.yml : GitHub Action to build and deploy to Vercel on push to main.
- .github/workflows/deploy-netlify.yml : GitHub Action to build and deploy to Netlify on push to main.
- scripts/deploy-vercel.sh : Local shell script using Vercel CLI (executable).
- scripts/deploy-netlify.sh : Local shell script using Netlify CLI (executable).

Secrets to add in GitHub repo settings > Secrets:
- For Vercel deploy:
  - VERCEL_TOKEN : Your Vercel personal token (create from dashboard).
- For Netlify deploy:
  - NETLIFY_AUTH_TOKEN : Personal access token from Netlify.
  - NETLIFY_SITE_ID : Your Netlify site ID (found in Site settings -> Site information).

Local usage examples:
- Vercel: VERCEL_TOKEN=xxx ./scripts/deploy-vercel.sh
- Netlify: NETLIFY_AUTH_TOKEN=xxx NETLIFY_SITE_ID=yyy ./scripts/deploy-netlify.sh

Notes:
- Both GitHub Actions and the local scripts rely on the project being buildable via `npm run build` (Vite output to dist).
- Vercel CLI `vercel --prod` requires the project to be linked to a Vercel project or you'll be prompted to select; using --token and --confirm attempts to use defaults.
- Netlify CLI uses the SITE ID to deploy directly to the correct site.
