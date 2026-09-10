# Meghkala — Crochet Studio Website

A single-page, pastel-aesthetic static site for Meghkala, a handmade crochet studio.
No build step — plain HTML/CSS/JS, deployable as-is on Vercel.

## Before you deploy

1. Open `index.html` and find this near the bottom, inside the `<script>` tag:

   ```js
   var WHATSAPP_NUMBER = "910000000000";
   ```

   Replace `910000000000` with the real WhatsApp number, country code first, no `+` or spaces
   (e.g. a number `+91 98765 43210` becomes `"919876543210"`). This one line updates every
   WhatsApp button on the page (nav, hero, mobile menu, contact section, floating button, footer).

2. (Optional) Swap any remaining illustrated gallery image in `images/` for a real product photo —
   keep the same filename or update the `src` attribute in the `#gallery` section of `index.html`.

3. The domain is already set to `https://meghkala.in` throughout `index.html`, `robots.txt`, and
   `sitemap.xml`. When you connect `meghkala.in` as a custom domain in Vercel (Project → Settings →
   Domains), everything will line up automatically. If you ever change the domain, update those
   three files the same way — this is what search engines and link-preview cards (WhatsApp,
   Instagram, Twitter/X) read, so a mismatch means shared links won't preview correctly.

## SEO included

This site ships with the basics already wired in:
- Unique `<title>` and meta description
- Open Graph + Twitter Card tags (so WhatsApp/Instagram/Facebook links show a nice preview card
  with the bouquet photo)
- `schema.org` structured data (`Store` type) so Google can understand this as a local handmade
  business
- `robots.txt` and `sitemap.xml`
- Clean single-`<h1>` heading hierarchy, descriptive `alt` text on every image

After deploying, submit the site to [Google Search Console](https://search.google.com/search-console)
(add your Vercel URL, verify ownership, submit `sitemap.xml`) so it actually gets crawled — none of
the above matters until Google knows the page exists.

## Deploy to Vercel

**Option A — Vercel dashboard**
1. Push this repo to GitHub (already done if you're reading this from the repo).
2. Go to [vercel.com/new](https://vercel.com/new), import the `meghkala` repo.
3. Framework preset: **Other** (no build command needed — it's static HTML).
4. Deploy.

**Option B — Vercel CLI**
```bash
npm i -g vercel
vercel login
vercel --prod
```

## Local preview

Just open `index.html` in a browser, or serve it locally:
```bash
npx serve .
```

## Structure

```
index.html      the whole site (single page)
images/          logo, product photos, and gallery illustrations
robots.txt       tells search engines they can crawl the site
sitemap.xml      lists the page for search engines
vercel.json      deployment config
```
