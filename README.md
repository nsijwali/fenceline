# Fenceline

A Qix-style territory game in a single offline HTML file. No dependencies, no login, no network.

Open `public/index.html` in a browser and press Play.

## How to play
- Walk along the walls. Step into open ground to draw a line, then reach a wall again to claim the land.
- Whatever the pterodactyl cannot reach becomes yours. Claim the target percentage to clear the level.
- Pterodactyls kill your unfinished line. Crawling babies on the walls cost you a life if they touch you.
- Controls: arrow keys or WASD. Swipe or the on-screen pad on touch. P pauses, M mutes.

## Looks
The look rotates each level: Day, Night, Handheld. Each has its own palette, music variant and land texture, in a pixel style after the offline dinosaur page.

## Music
The background music is built around a two-note whistled call (C#5 then A4), generated live with WebAudio. No audio files are used.

## Deploy (Cloudflare Workers static assets)
The site is the `public/` folder. `wrangler.jsonc` serves it at `fenceline.nitinsijwali.com`.

```sh
npx wrangler login
npx wrangler deploy
```

Or connect this repo in the Cloudflare dashboard (Workers & Pages > Create > Import a repository). The build command is empty and the deploy command is `npx wrangler deploy`. The custom domain is created on first deploy when `nitinsijwali.com` is a zone in the same Cloudflare account.

To use another domain, change the host in `wrangler.jsonc` and replace `https://fenceline.nitinsijwali.com/` in `public/index.html`, `public/robots.txt` and `public/sitemap.xml`.

## Google Search Console
1. Add the domain `nitinsijwali.com` as a Domain property and verify it with the DNS TXT record (one click in Cloudflare DNS). This covers every subdomain.
2. Sitemaps > submit `https://fenceline.nitinsijwali.com/sitemap.xml`.
3. URL Inspection > paste the home URL > Request indexing.

Created by [Nitin Sijwali](https://github.com/nsijwali).
