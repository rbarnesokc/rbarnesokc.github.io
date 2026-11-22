# ryanbarnes.dev

Personal site for Ryan Barnes, served at https://www.ryanbarnes.dev.

It is a single static page with no build step and no dependencies to install. Everything it uses (CSS, JavaScript, fonts, images) lives in this repo.

## Files

| Path | What it is |
| --- | --- |
| `index.html` | The whole page: markup, styles, and the script for the heading animations |
| `favicon.svg` | Browser tab icon |
| `fonts/` | Self-hosted Londrina Solid and Barlow Semi Condensed (see `fonts/README.md`) |
| `images/ryan-headshot.jpg` | Headshot in the opening section |
| `images/family.jpg` | Photo in the "Off the clock" section |
| `images/og.jpg` | 1200x630 preview image shown when the link is shared (LinkedIn, Slack, texts) |

## How the page works

- The page is a stack of full-width color bands. Each band always sits on its own color (so its text keeps its contrast) and blends in from the band above at its top edge.
- Each section heading builds itself a different way when it scrolls into view: sketched (opening), typed (fintech), poured like dirt (trucking), built from pieces (Core Compliance), painted (off the clock), and stamped (say hi).
- Every heading is fully visible without JavaScript. The animations only hide a heading once the script knows it can play it, and they are skipped for visitors who have reduced motion turned on.

## Preview locally

Any static file server works. From this folder:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Deploy

The site is hosted on DigitalOcean App Platform (app hostname `oyster-app-7xzyl.ondigitalocean.app`), built from the `main` branch of this repo. DNS for `ryanbarnes.dev` is managed at DigitalOcean.

1. Merge changes into `main` and push.
2. If the app has automatic deploys turned on, DigitalOcean redeploys within a minute or two. If not, open the app in the DigitalOcean dashboard and click **Deploy**.
3. Check https://www.ryanbarnes.dev and hard refresh to confirm the change is live.

To check a link preview after changing `images/og.jpg` or the page description, use LinkedIn's Post Inspector (https://www.linkedin.com/post-inspector/), which also refreshes LinkedIn's cached copy.

### Known gap

`ryanbarnes.dev` without `www` does not resolve, because the bare domain has no DNS record. To fix it, add `ryanbarnes.dev` as a domain on the app in DigitalOcean: open the app, go to the **Networking** tab, click **Add domain** under **Domains**, and choose **We manage your domain**. DigitalOcean then creates the record and the HTTPS certificate, since it already manages the DNS.
