# CardioVarsity -> cardiovarsity.shehadehlab.com

Static single-page app (built by the summer 2026 high-school students in Replit).
Railway runs: npm install (adds `serve`) -> npm start -> `serve -s dist` on $PORT.
`serve -s` sends unknown paths to index.html, so /learn, /glossary, etc. refresh correctly.
(.htaccess and _redirects in dist/ are for Apache/Netlify hosts and are ignored here.)

Hosting pattern is identical to vapor.shehadehlab.com:
- GitHub repo LinaShehadeh/cardiovarsity, branch main
- Railway service deploys from that repo
- Wix DNS: CNAME  cardiovarsity -> <target Railway shows for the custom domain>

## To update later
1. Rebuild from the source (in ../context/cardiovarsity-handoff/source: `npm ci && npm run build`),
   keeping Vite `base: "/"`.
2. Replace the contents of `dist/` with the new build.
3. git add . && git commit -m "update" && git push   -> Railway redeploys in ~1 min.
