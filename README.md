# Solomon Padilla — Developer Portfolio

Hi, I'm Solomon, a Phoenix-based full stack web developer. This repo is the source for my personal portfolio: a single-page, section-scrolling site built with **Nuxt 3**, **Vue 3**, and **Tailwind CSS** that showcases the products I've designed, built, and shipped.

📫 **Contact:** [dev.spadilla@gmail.com](mailto:dev.spadilla@gmail.com) · **GitHub:** [@solpadilla](https://github.com/solpadilla)

---

## Featured Projects

| Project | What it is | Links |
| --- | --- | --- |
| **MCC Stats** | Stats and leaderboards site for Halo: The Master Chief Collection — player profiles, season leaderboards, and community features. | [Live](https://mccstats.pythonanywhere.com/) |
| **Halo Record** | A Halo MCC player statistics platform featuring TrueSkill ratings, service records, match history with carnage reports, and season leaderboards. | [Live](https://halorecord.com) · [Code](https://github.com/solpadilla/halo) |
| **Omnislash** | A platform where gamers explore and share their media, achievements, and stats using the Omnislash app. | — |
| **M2M** | Membership-management software offering streamlined memberships and event planning to foster community engagement. | [Live](https://m2mnow.com) |
| **FNAF Pizzeria** | A Five Nights at Freddy's themed pizza-ordering app with real-time order tracking, admin management, and Stripe payments — wrapped in a VHS security-camera aesthetic. | [Live](https://fnafpizzaria.netlify.app) · [Code](https://github.com/fnafpizza/fnaf-pizza-app) |
| **Emotesizer** | A free, browser-based emote maker for Twitch, Discord, Kick, 7TV, BTTV, and FFZ — search GIFs, then resize, crop, and compress them into platform-ready emotes entirely client-side. | [Live](https://emotesizer.com) · [Code](https://github.com/solpadilla/emotesizer) |
| **Sportseekr** | A multi-tenant SaaS platform connecting parents, athletes, coaches, and youth-sports organizations — featuring Stripe Connect payouts and native iOS/Android apps via Capacitor. | [Live](https://sportseekr.netlify.app) |
| **Legitski** | A multi-tenant inventory platform where teams define their own item schema, scan barcodes, and track stock in real time — with low-stock alerts, Excel/PDF exports, and Stripe billing. | [Live](https://legitski.com) |

## About This Site

The portfolio itself is a hand-built showcase rather than a template:

- **Full-page section scrolling** implemented from scratch — custom wheel and touch handlers with smooth scroll-snapping between project sections (no scroll library).
- **Dark / light mode** persisted across visits with Pinia + `pinia-plugin-persistedstate`.
- **Performance-minded** — lazy-loaded media (`nuxt-lazy-load`), gzip/brotli asset compression at build time (`vite-plugin-compression2`), and SEO meta/robots configuration out of the box.
- **Custom UI details** — CSS-only illustrated keyboard and mouse on the hero, per-project theming, and animated section accents built with Tailwind.

## Tech Stack

- **Framework:** Nuxt 3 (Vue 3, Composition API, `<script setup>`)
- **Styling:** Tailwind CSS + Sass
- **State:** Pinia with persisted state
- **Tooling:** Vite, nuxt-icon, @nuxtjs/robots, vite-plugin-compression2

## Running Locally

```bash
npm install
npm run dev      # http://localhost:3000
```

```bash
npm run build    # production build
npm run preview  # preview the production build
```

---

Thanks for stopping by — if you'd like to talk about a role or a project, reach me at [dev.spadilla@gmail.com](mailto:dev.spadilla@gmail.com).
