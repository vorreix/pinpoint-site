# pinpoint-site

The public site for **Pinpoint**, at [pinpoint.vorreix.com](https://pinpoint.vorreix.com).

It exists mainly because both app stores require a reachable privacy policy URL,
and because the app links to these pages from Settings, About and Help.

| Page | Path | Linked from |
|---|---|---|
| Landing | `/` | — |
| Privacy Policy | `/privacy` | App: Privacy & data, About |
| Terms of Use | `/terms` | App: About |
| Support | `/support` | App: Help & support |

Plain HTML and one stylesheet. No framework, no build step, no dependencies —
there is nothing here to keep up to date, which is the point for pages that must
stay reachable for as long as the app is listed.

`vercel.json` enables `cleanUrls`, so `/privacy` serves `privacy.html`. The app's
`LINKS` constant uses those extensionless paths, so keep it on.

## Local preview

```bash
python3 -m http.server 4000
```

Then open <http://localhost:4000>. Note that `cleanUrls` is a Vercel feature, so
locally you need `/privacy.html` rather than `/privacy`.

## Deploying

Connected to Vercel and deployed on push to `main`.

## Keeping it honest

The privacy policy describes what the app actually does: usable with no account,
no analytics or tracking SDKs, and a synced data set of exactly four document
types. If the app's data handling changes, this has to change with it. The app
side of that contract lives in `sync.ts` and `credentials/README.md` in the main
[pinpoint](https://github.com/vorreix/pinpoint) repository.
