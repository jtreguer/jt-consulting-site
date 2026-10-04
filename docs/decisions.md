# Decisions — overrides to the spec and methodology

*Where this file disagrees with `website-design-spec.md` or `audit-methodology.md`, this file wins.*

## Decided (2026-10-04)

- **Audience.** SMEs in the French Basque Country, Pau and as far as Bordeaux. Not remote Europe, not Spain.
- **Message.** These companies know AI matters but don't know what they can do or what they should do. The page speaks to that uncertainty, not to companies whose AI pilot failed.
- **Shape.** One page plus legal pages (mentions légales, confidentialité). No `/method`, `/work`, `/training` and so on at launch.
- **Language.** French only at launch. Copy lives in `src/pages/index.astro`; an English version later would be a translated copy under `/en/`.
- **Main call to action.** A free 30-minute call. The paid diagnostic is presented as the step that follows.
- **Prices.** No figures on the page. Only a well-defined package gets a fixed price announced upfront (today, the diagnostic). Implementation is quoted from the diagnostic. No race to the bottom on rates.
- **Timing.** The 2–3 weeks apply to the diagnostic only. Implementation (agentic systems, data pipelines, model training and deployment) usually takes months; the diagnostic estimates it.

- **Experience.** About 15 years in finance and in management consulting for finance practices (BNP Paribas 7 years, ADI Alternative Investment 3 years, SGAM AI, consulting 3 years).
- **Bordeaux argument.** Dropped.
- **Offers.** Two entry questions only: "Que valent mes données ?" (data science, data audit) and "Que change l'IA pour mon entreprise ?" (GenAI, automation, process redesign, audit). Each answers what, how long, how much, and what result.
- **Proof.** All references and case studies kept, Spanish ones included.
- **Little or no data.** A good fit. Telling a company what to start collecting, and how, is a valid result.
- **Data/ML experience.** About 8 years: PhD (4 years of cosmological data analysis), Vicomtech 2 years, ESTIA 1 year, QuantsUnited 6 months, Astroteq.ai 4 months.
- **Teaching.** Data science since 2018 (Simplon.co, ESTIA 2025); GenAI uses at ESTIA from November 2026.
- **Booking.** Calendly free tier, as a plain link (no embedded script).
- **Stack.** Astro static, plain CSS with tokens (no Tailwind), self-hosted fonts. One small inline script for the theme switcher.
- **Look.** Inspired by omarchy.org: JetBrains Mono headings, Geist body, square corners, offset shadows, terminal-style hero, ASCII ranking bars. Four themes cycled with T: côte (light default), piment, rhune, nuit (dark default).

## Still open

- Before launch: email, Calendly link, LinkedIn URL, SIRET, legal address, hosting provider (`src/site.ts`, `src/pages/mentions-legales.astro`), portrait photo.
- Case studies have titles only. Julien is gathering a publishable result line for each.
