# Mashiel Khan — Multi-page portfolio

A working Next.js App Router starter based on the provided single-file HTML portfolio, visually inspired by the Lantern River theme. This is an original CSS reimplementation of the atmosphere; it does not embed the original template's bundled Three.js experience.

## Run locally

1. Install Node.js 20.9+ (Node 22 or later recommended).
2. Run `npm install` and `npm run dev`.
3. Open http://localhost:3000.
4. Copy `.env.example` to `.env.local`, then configure services if required.

## Pages

- `/` Home
- `/about` About
- `/projects` Curated work
- `/projects/[slug]` Detailed project pages
- `/skills` Skills
- `/contact` Contact with server-side email API
- `/sitemap.xml` and `/robots.txt`

## Enable the contact form

Use a Resend account, verify a sending domain, and supply `RESEND_API_KEY`, `CONTACT_FROM_EMAIL` (verified sender) and `CONTACT_TO_EMAIL` in `.env.local` / deployment secrets. The contact endpoint validates input using Zod and submits from a server route. Before the credentials are set, it intentionally returns an error and never claims the message was sent. For public high-traffic deployment add distributed rate-limiting, Turnstile and monitoring; the included honeypot is NOT sufficient spam protection by itself.

## Personalization

- `src/lib/projects.ts`: edit project claims and verified links. Entries marked planned are not production claims.
- `src/lib/site.ts`: personal introduction and links.
- `src/app/globals.css`: styling, colors and scene.
- `NEXT_PUBLIC_SITE_URL`: deployed canonical URL.
- `NEXT_PUBLIC_CV_URL` reserved for future CV download feature; do not claim environment changes go live without a deployment.

## Pre-release checks

- Verify each project description, screenshots, status and URLs.
- Add real project screenshots and a verified CV link when supplied.
- Confirm current skills and contact details.
- Set Resend secrets and test successful delivery.
- Add production abuse mitigation and stronger automated testing.
- Run `npm run build` before deployment.
- Deploy to Vercel or another Next.js-compatible host.

**Note:** The original Lantern River ZIP is included as a user-supplied design reference only and has not been copied wholesale into this rebuild. GitHub browsing is a link to the profile; dynamic GitHub repo loading has deliberately been removed to keep curated projects truthful and predictable.


## Creative Edition upgrade (November 2026)
- High-impact editorial homepage with responsive kinetic-style artwork, accessible reduced-motion support and animated marquee.
- Curated projects, case study routes, and new `/github` public repository directory with search/language filter.
- GitHub profile + repository metadata fetched from the public REST API **server-side**, cached for 1 hour. When the API fails, a verified PUBLIC repo index is displayed (no private data).
- Set `NEXT_PUBLIC_SITE_URL` to your deployed origin and configure `RESEND_API_KEY`, `CONTACT_TO_EMAIL`, `CONTACT_FROM_EMAIL` for real contact submission.
- All gradient artworks are intentional placeholders. Replace with screenshots of your actual apps for the final portfolio.
- Verify specific feature claims and statuses in project case studies before publishing; avoid inventing demos and achievements.
