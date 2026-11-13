# Option Chain Tracker

Static page (`index.html`) plus one serverless function (`api/chain.js`) that reads NSE's public option-chain data.
No build step and no dependencies.

## Deploy on Vercel
**Option A: drag and drop / CLI**
1. Install the CLI: `npm i -g vercel`
2. In this folder run `vercel`, accept the defaults (Framework: Other), then `vercel --prod`.

**Option B: GitHub**
1. Push this folder to a new GitHub repo.
2. On vercel.com choose Add New → Project → import the repo → Deploy.

You get a `https://your-project.vercel.app` URL.

## Important: NSE may block Vercel
NSE actively blocks many cloud/datacenter IPs. If the site shows "Showing demo data":
- Redeploy, or try again after a minute; it sometimes works intermittently.
- In Vercel → Project → Settings → Functions, change the Function Region to Mumbai (`bom1`) to be closer to NSE.
- If it still fails, swap `api/chain.js` to a paid/licensed data API (e.g. Zerodha Kite Connect, Upstox, Dhan) or host the function on an Indian VPS.

## Customising
Edit the `SYMBOLS` array in `index.html` to add or remove companies.
