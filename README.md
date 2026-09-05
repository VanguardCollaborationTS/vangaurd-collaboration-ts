# Vanguard Collaboration Transportation Services

Marketing website for Vanguard Collaboration Transportation Services LLC — a non-emergency medical transportation (NEMT) and Special Transportation Service (STS) provider serving the Minneapolis–St. Paul metro.

Built with [Astro](https://astro.build) and deployed to Cloudflare Workers.

**Live site:** https://vanguardcollaborationts.com (the `*.workers.dev` URL and `www.` redirect here)

## Pages

| Route       | Description                                          |
| :---------- | :--------------------------------------------------- |
| `/`         | Home — hero, services overview, why us, how it works |
| `/about`    | Mission, owner, key facts, standards, FAQs           |
| `/services` | Full service catalog, destinations, service area     |
| `/request`  | Ride request form (Formspree)                        |
| `/contact`  | Contact details and inquiry form (Formspree)         |

## Project structure

```
src/
  components/   Header, Footer, BaseHead, Icon, CtaBand, FormHandler
  layouts/      Layout.astro — page shell used by every page
  pages/        One .astro file per route
  styles/       global.css — design tokens, buttons, cards, forms
  consts.ts     Business info (phone, email, hours, address, nav links)
public/         Static assets (van-hero-person.webp/.jpg for the home hero & social card, van-hero.png for About, favicon.svg, fonts)
```

Business details (phone number, email, address, hours) live in `src/consts.ts` — update them there and every page picks up the change.

## Design

- **Orange** `#e8630a` — primary / calls to action
- **Ivory** `#fffbf0` — page background
- **Navy** `#1b2a4a` — header, footer, headings, dark sections

## Commands

| Command          | Action                                        |
| :--------------- | :-------------------------------------------- |
| `npm install`    | Install dependencies                          |
| `npm run dev`    | Start local dev server at `localhost:4321`    |
| `npm run build`  | Build production site to `./dist/`            |
| `npm run deploy` | Deploy to Cloudflare Workers (`wrangler deploy`) |

## Forms

Both forms post to Formspree using the address in `FORMSPREE_ACTION` (`src/consts.ts`). Once a Formspree form ID is created, replace that value with `https://formspree.io/f/<FORM_ID>`.
