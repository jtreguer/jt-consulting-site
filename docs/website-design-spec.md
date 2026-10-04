# treguer.com — Website Design & Build Specification

*Companion to `audit-methodology.md`*
*v0.1 — build brief for Claude Code*

---

## 1. Purpose and priorities

A single-page-led marketing site for an independent AI and data consulting practice, selling three shapes of the same expertise: **consulting, training, and development**.

**Priority order for traffic:**

1. Remote clients — mid-sized companies anywhere in France, Spain, or English-speaking Europe, arriving from LinkedIn, referral, or search
2. Local clients — French and Spanish Basque Country, arriving from cluster events, training engagements, and word of mouth

**Design consequence:** the site reads international first, with local presence as a credibility detail rather than a headline. A visitor from Amsterdam should not feel they have landed on a regional practice; a visitor from Bilbao should still find the proof that this person is twenty minutes away.

**Primary conversion goal:** book a 30-minute call. One goal, one button, everywhere.
**Secondary goal:** training enquiry, for visitors not ready to commit to a diagnostic.
**Tertiary goal:** email list, for visitors not ready for either.

---

## 2. Language and localisation

Three languages at launch: **English, French, Spanish**.

- **Default: English.** Root URLs (`/`, `/audit`, `/training`) serve English.
- **French: `/fr/` prefix.** Full version.
- **Spanish: `/es/` prefix.** Full version. Peninsular Spanish, not neutral or Latin American — the target is Euskadi, Navarre and the rest of Spain.
- Language switcher in the header, always visible, showing the current language and the alternatives. Use language names (`EN` / `FR` / `ES`), never flags — flags map to countries, not languages, and Spanish-speaking visitors in particular notice.
- Preserve the current page when switching language. `/fr/audit` ↔ `/es/auditoria` ↔ `/audit`, never dumping the user back to the homepage. This requires a route-mapping table if slugs are localised; if that adds too much complexity, keep English slugs across all three and localise only the content.
- No automatic redirection based on browser locale. Serve English by default and let the visitor choose. Auto-redirect breaks shared links and annoys bilingual users, of whom this audience has many.
- `hreflang` on every page covering all three versions, plus `x-default` to the English page.

### Positioning differs by language — this is the important part

The three versions share structure and differ in emphasis. Same nine pages, same components, different hero framing and different ordering of proof.

| | English | French | Spanish |
|---|---|---|---|
| Primary audience | Remote, Europe-wide | Remote France + local Iparralde | Euskadi, Navarre, industrial |
| Hero emphasis | Method and judgment | Method and judgment | Industrial results, proximity |
| Lead credibility | BNP Paribas, QuantsUnited | BNP Paribas, Crédit Agricole, ESTIA | **Vicomtech**, ESTIA, industry |
| Lead case study | Finance or automation | Banking chatbot, remote-sensing | Refinery thermal monitoring |
| Location line | Understated footer detail | "Pays basque, missions à distance" | Prominent — proximity is the asset |

The logic: on the English site, being in the Basque Country is a neutral detail that must not make the practice look regional. On the Spanish site it is the selling point. Vicomtech is a Donostia research centre with real standing in that ecosystem — on the Spanish pages it is a reference people recognise, and it should sit first in the credibility strip rather than fourth.

Implement this through per-language content files, not per-language components. The ordering of the logo strip and the case study list comes from the content collection, so the same component renders all three.

### Writing rule

Each version is written, not translated. French B2B prose has a different rhythm and a lower tolerance for the direct second person. Spanish industrial B2B is more formal than English and expects *usted* throughout.

**Have the Spanish reviewed by a native professional before launch.** Fluency is sufficient for conversation and insufficient for marketing copy, where a slightly off register reads as foreign and undermines the proximity argument the Spanish version exists to make. A contact at Vicomtech or ESTIA reading it once will catch what matters.

---

## 3. Information architecture

```
/                       Homepage — the landing page proper
/audit                  Consulting: the diagnostic, method, deliverable
/training               Training catalogue
/build                  Development & implementation
/work                   Case studies (index + individual pages)
/about                  Who I am — the background, the proof
/contact                Form + booking embed
/method                 The published methodology (long-form, SEO asset)
/legal/privacy          Privacy policy (GDPR, mandatory)
/legal/notice           Mentions légales (mandatory in France)

/fr/… mirror of all of the above
/es/… mirror of all of the above
```

Nine pages plus legal. Resist growth. A larger site is a way of avoiding prospects.

**`/method` deserves particular attention.** It is the public version of the audit methodology document — the framework, the scoring grid, the deliverable structure. Long, substantive, genuinely useful. It does three jobs: it is the main organic search asset, it pre-qualifies visitors, and it converts scepticism into trust faster than any sales copy. Publishing the map sells the guide.

---

## 4. Global elements

### 4.1 Header

Sticky on scroll, condensing to a slimmer bar after ~80px. Height 72px at rest, 56px condensed.

```
[ Julien Treguer ]          Consulting  Training  Build  Work  Method  About     [ EN|FR ]  [ Book a call ]
```

- Wordmark left: name, set in the display face, not a logo image. Links home.
- Navigation centre-right. Six items maximum. Current page marked with a subtle underline or weight change, not colour alone.
- Language switcher then primary CTA button, far right. The CTA is the only filled button on the page — that exclusivity is what makes it work.
- **Mobile:** wordmark, language switcher, hamburger. Full-screen overlay menu, large tap targets, CTA repeated at the bottom of the overlay. A sticky bottom bar with the CTA on mobile is worth testing — it lifts conversion noticeably on long pages.

### 4.2 Footer

Four columns on desktop, stacked on mobile.

- **Column 1 — Identity.** Name, one-line descriptor, base location ("Basque Country, France — working remotely across Europe"), email as a real `mailto:` link.
- **Column 2 — Services.** Consulting, Training, Build, Method.
- **Column 3 — Company.** Work, About, Contact, LinkedIn, GitHub.
- **Column 4 — Newsletter.** One-field email capture. Honest label: what they get and how often. "Notes on AI in practice — roughly monthly, no promotion."
- **Bottom bar.** © year, SIRET number, Mentions légales, Privacy, language switcher repeated.

The location line in the footer is deliberate: internationally invisible, locally reassuring, and it does the regional signalling without compromising the international read of the homepage.

---

## 5. Homepage structure

Ten sections. Order matters — it follows a visitor's actual sequence of doubts.

| # | Section | Job |
|---|---|---|
| 1 | Hero | State the value proposition and the CTA |
| 2 | Credibility strip | Prove this is not a first-timer, immediately |
| 3 | The problem | Name the situation the visitor is in |
| 4 | Three shapes | Consulting / Training / Build |
| 5 | How it works | The three-step path, benefit-framed |
| 6 | Proof | Case studies and testimonials |
| 7 | Who this is for | Qualify in and out |
| 8 | About, condensed | The person, the unusual background |
| 9 | Objections | The questions nobody asks out loud |
| 10 | Final CTA | Close |

### Section 1 — Hero

Full viewport height on desktop, auto on mobile. Text left, generous whitespace right, or centred single-column — no stock photography, no abstract AI imagery, no neural-network graphics. Restraint reads as seniority here.

**Contents:** eyebrow line, H1, subheading, primary CTA button, secondary text link, one-line trust cue below.

The secondary link goes to `/method`, not to a second service page. Visitors not ready to book will read something; give them the substantial thing.

### Section 2 — Credibility strip

Immediately below the fold. A quiet row of names worked with, in muted monochrome: **BNP Paribas · Crédit Agricole · Vicomtech · ESTIA · QuantsUnited · Astroteq.ai**

Prefaced by a small, honest label — "Selected engagements and past roles" — because some are consulting clients and some are employment history, and conflating them is the kind of thing that gets noticed.

Logos only where usage rights are clear. Text set in a clean face at 60% opacity works nearly as well and carries no legal risk.

### Section 3 — The problem

Three short blocks, each naming a real situation rather than describing a service. This is where the visitor recognises themselves.

Suggested three: *the data you already collect is doing nothing*; *the AI pilot that never shipped*; *the process that quietly eats a full-time role*.

### Section 4 — Three shapes

Three cards, equal weight, each with a title, one-line description, three bullets, price anchor, and a text link through to the full page. No CTA buttons on the cards — the buttons compete with the single primary CTA. Text links only.

Including a price anchor on the homepage is unusual and deliberate. It filters out the visitors who were never going to buy and it signals confidence.

### Section 5 — How it works

The three-step path, framed as benefits rather than process steps. Numbered, horizontal on desktop, vertical on mobile.

Each step gets: number, title, one sentence on what happens, one sentence on what the client ends up with. The second sentence is the one that matters — clients buy outcomes, not stages.

### Section 6 — Proof

**The honest position at launch:** there are no testimonials. Build the section so it functions without them and absorbs them as they arrive.

Launch configuration — three case study cards, each anonymised to sector where the client is not named:
- *Real-time thermal monitoring of a refinery furnace* (industrial, Spain)
- *Automated crypto market screener with alerting* (finance, remote)
- *HR chatbot delivered with a two-person team* (banking, France)

Card format: context, problem, what was built, result. Result as a number wherever one exists. Where no number can be published, state the qualitative outcome plainly rather than inflating it.

Testimonial slots sit below, hidden until populated. Three is the target. **Ask for them now** — two of these clients are likely still reachable, and a two-line quote with a name and title is worth more than any amount of copy.

### Section 7 — Who this is for

Two columns, plainly labelled: **A good fit** / **Not a good fit**.

The second column is the more persuasive of the two. Naming who you do not serve — companies wanting the cheapest possible day rate, organisations with no data at all, anyone wanting a chatbot bolted on for appearances — reads as confidence and costs nothing, because those people were never going to buy.

### Section 8 — About, condensed

Portrait photograph, three short paragraphs, link to `/about`.

The photograph matters more than is comfortable. The product is one person's judgment; the visitor wants to see them. Professional, natural light, neutral background, looking at the camera. Not a studio corporate portrait, not a conference snapshot.

The paragraphs should lead with the combination that is genuinely rare — a decade in investment banking and asset management followed by a decade in machine learning — because that is the thing no competitor can copy.

### Section 9 — Objections

Accordion, five or six items. The questions a prospect thinks and does not ask.

Suggested: *Isn't this something my IT team could do?* · *We tried an AI pilot and nothing came of it.* · *Our data is confidential — can this work without sending it to OpenAI?* · *What if the audit finds nothing worth doing?* · *You're one person. What happens if you're unavailable?* · *How is this different from a large consultancy?*

The fourth and fifth are the ones most sites avoid. Answering them straight is the whole point of the section.

### Section 10 — Final CTA

Contrasting background band. One heading, one sentence, one button. Nothing else — no form, no links, no navigation. This is the last thing on the page and it should feel like a door.

---

## 6. Copy drafts

Working drafts. Replace once the lead vertical is decided.

### 6.1 Hero — English

**Option A (recommended)**

> *Eyebrow:* AI & data consulting
>
> **# Find out where AI actually pays in your business — then build it.**
>
> Most AI projects fail before they start, because nobody worked out what was worth building. I run a paid diagnostic that ranks the opportunities in your business by euro value and feasibility, then build the ones that hold up.
>
> `[ Book a 30-minute call ]`  ·  *Read the full method →*
>
> *Twenty years across investment banking and machine learning. Based in the Basque Country, working remotely across Europe.*

**Option B (sharper, more opinionated)**

> **# Most AI projects fail in the scoping, not the build.**
>
> I find the three things in your business worth automating, prove one works, and put it into production. Fixed price for the diagnostic, business metrics for success, no proof-of-concept purgatory.

**Option C (outcome-led)**

> **# AI and data systems that pay for themselves — designed, built and kept running by one senior engineer.**

Recommendation: **A** for launch. It states the offer, names the failure mode, and the subheading does the qualifying. B is better copy but assumes a visitor who already knows they have a problem; revisit once traffic composition is known.

### 6.2 Hero — French

> *Surtitre :* Conseil IA & data
>
> **# Identifier ce que l'IA peut vraiment rapporter dans votre entreprise — puis le construire.**
>
> La plupart des projets d'IA échouent avant d'avoir commencé, faute d'avoir déterminé ce qui méritait d'être construit. Je réalise un diagnostic payant qui classe les opportunités de votre entreprise par valeur et par faisabilité, puis je développe celles qui tiennent la route.
>
> `[ Réserver un appel de 30 minutes ]`  ·  *Lire la méthode complète →*
>
> *Vingt ans entre banque d'investissement et machine learning. Basé au Pays basque, missions à distance dans toute l'Europe.*

### 6.2b Hero — Spanish

Note the different lead: the Spanish version opens on industrial proximity rather than on method, per the positioning table in §2.

> *Antetítulo:* Consultoría en IA y datos
>
> **# Identificar dónde la IA aporta valor real en su empresa — y construirlo.**
>
> La mayoría de los proyectos de IA fracasan antes de empezar, porque nadie determinó qué merecía la pena construir. Realizo un diagnóstico de pago que clasifica las oportunidades de su empresa por valor económico y viabilidad, y desarrollo las que resisten el análisis.
>
> `[ Reservar una llamada de 30 minutos ]`  ·  *Consultar el método completo →*
>
> *Veinte años entre banca de inversión y machine learning. Con proyectos industriales en Euskadi — Vicomtech, ESTIA — y presencia a ambos lados de la frontera.*

### 6.3 Three shapes — English

**Consulting — Know what to build**
Start with a paid diagnostic. Two to three weeks, fixed price, and a ranked portfolio of opportunities costed in euros.
- Process and data mapping across your operations
- Every opportunity scored on value, feasibility and risk
- A recommended first project with success criteria in business terms

*From €5,000 · Learn about the audit →*

**Training — Build the capability in-house**
One to three days with your teams, at least 60% hands-on. Management or engineering, tailored to your systems.
- GenAI for decision-makers — one day, non-technical
- Building with LLMs — three days, for development teams
- Data science for industry — time series, vision, deployment

*From €1,800/day · See the catalogue →*

**Build — Ship it to production**
Proof of concept, then a production system: integrated, monitored, documented, and maintained.
- POC with business success criteria agreed in writing
- Production build with monitoring, evaluation and handover
- Ongoing operation, or transfer to your team

*Project-based · How I build →*

### 6.4 Three shapes — French

**Conseil — Savoir quoi construire**
Commencer par un diagnostic payant. Deux à trois semaines, prix fixe, et un portefeuille d'opportunités classées et chiffrées.
- Cartographie des processus et des données
- Chaque opportunité évaluée en valeur, faisabilité et risque
- Un premier projet recommandé, avec des critères de réussite métier

*À partir de 5 000 € · Découvrir le diagnostic →*

**Formation — Monter en compétence en interne**
Un à trois jours avec vos équipes, 60 % de pratique au minimum. Direction ou ingénierie, adapté à vos systèmes.
- L'IA générative pour les décideurs — une journée, sans prérequis technique
- Développer avec les LLM — trois jours, pour les équipes de développement
- Data science industrielle — séries temporelles, vision, déploiement

*À partir de 1 800 €/jour · Voir le catalogue →*

**Développement — Mettre en production**
Une preuve de concept, puis un système en production : intégré, supervisé, documenté, maintenu.
- POC avec critères de réussite métier définis par écrit
- Développement, supervision, évaluation et transfert
- Exploitation continue, ou reprise par vos équipes

*Au projet · Ma façon de travailler →*

### 6.4b Three shapes — Spanish

**Consultoría — Saber qué construir**
Empezar por un diagnóstico de pago. De dos a tres semanas, precio cerrado, y una cartera de oportunidades clasificada y cuantificada en euros.
- Cartografía de procesos y datos de su operación
- Cada oportunidad evaluada en valor, viabilidad y riesgo
- Un primer proyecto recomendado, con criterios de éxito de negocio

*Desde 5.000 € · Conocer el diagnóstico →*

**Formación — Desarrollar la capacidad internamente**
De uno a tres días con sus equipos, con un mínimo del 60 % de práctica. Dirección o ingeniería, adaptado a sus sistemas.
- IA generativa para directivos — una jornada, sin requisitos técnicos
- Desarrollar con LLM — tres días, para equipos de desarrollo
- Data science industrial — series temporales, visión, despliegue

*Desde 1.800 €/día · Ver el catálogo →*

**Desarrollo — Llevarlo a producción**
Una prueba de concepto y después un sistema en producción: integrado, supervisado, documentado y mantenido.
- POC con criterios de éxito de negocio acordados por escrito
- Desarrollo, supervisión, evaluación y transferencia
- Explotación continua, o traspaso a su equipo

*Por proyecto · Cómo trabajo →*

### 6.5 How it works — English

**1. Diagnose — Stop guessing which AI project to fund**
Two to three weeks mapping your processes, systems and data. You get a ranked portfolio of opportunities, each costed in euros, with the weak ones eliminated and the reasons given.

**2. Prove — Find out in six weeks, not six months**
One opportunity, built to a success criterion agreed in advance and expressed as a business metric. A documented no is a legitimate result, and it costs a fraction of discovering the same thing after a full build.

**3. Deploy and run — A system that keeps working after I leave**
Production build, integration, monitoring and evaluation. Then either continuous operation under a monthly retainer, or a handover that your team can genuinely absorb.

### 6.6 How it works — French

**1. Diagnostiquer — Ne plus choisir au hasard le projet à financer**
Deux à trois semaines pour cartographier vos processus, vos systèmes et vos données. Vous obtenez un portefeuille d'opportunités classées et chiffrées, les moins pertinentes étant écartées avec les raisons.

**2. Prouver — Savoir en six semaines plutôt qu'en six mois**
Une opportunité, développée selon un critère de réussite défini à l'avance et exprimé en termes métier. Un non documenté est un résultat légitime, pour une fraction du coût d'un développement complet.

**3. Déployer et exploiter — Un système qui continue à fonctionner après mon départ**
Mise en production, intégration, supervision et évaluation. Puis exploitation continue au forfait mensuel, ou transfert réellement assimilable par vos équipes.

### 6.7 Final CTA

**EN:** *Not sure whether you have an AI problem or a data problem?*
That is usually the right question to start with. Thirty minutes, no preparation needed, no obligation.
`[ Book a call ]`

**FR:** *Vous ne savez pas si votre sujet relève de l'IA ou de la donnée ?*
C'est en général la bonne question de départ. Trente minutes, sans préparation ni engagement.
`[ Réserver un appel ]`

**ES:** *¿No sabe si su problema es de IA o de datos?*
Suele ser la pregunta correcta para empezar. Treinta minutos, sin preparación ni compromiso.
`[ Reservar una llamada ]`

---

## 7. Secondary pages

### `/audit`
Hero, what the diagnostic is, the twelve-day timeline as a visual, the deliverable with a table of contents and an anonymised sample extract, the scoring grid explained, two price tiers, what is expected of the client, FAQ, CTA. Drawn directly from §3–§8 of the methodology document.

### `/training`
Hero, the four courses (A–D) with one card each expanding to detail — audience, prerequisites, duration, programme outline, practice ratio, price. Delivery formats: on-site, remote, intra-company. A clear note on funding once the Qualiopi question is settled. CTA: training enquiry, which is the one place a form outranks the call booking.

### `/build`
Hero, the POC conditions stated publicly — this pre-qualifies and impresses in equal measure — the production standard (monitoring, evaluation harness, documentation, handover), the run offer, the technical competence map from §10 of the methodology, and a plain statement on on-premise and data sovereignty. That last point is a genuine differentiator and deserves its own block.

### `/work`
Index of case studies, filterable by sector and by shape. Each case study: context, problem, approach, what was built, result, technologies. Anonymise where required but never vaguely — "a Spanish industrial research centre" is credible, "a major client" is not.

### `/about`
The full story. Lead with the combination — quantitative finance and machine learning — then the trajectory, the teaching, the languages, the location. A photograph, and a downloadable CV. This page will be read by anyone considering a significant engagement; it is worth writing properly.

### `/method`
The long-form public methodology. Expect 3,000+ words. Sectioned with an anchored table of contents, downloadable as PDF in exchange for an email address. The main organic search asset and the page that converts sceptics.

---

## 8. Conversion mechanics

### 8.1 Primary — booking

Embed a scheduling tool rather than a contact form for the primary CTA. **Cal.com** (open source, self-hostable, free tier) is the recommended choice; Calendly is the alternative.

- Single 30-minute event type, "Intro call"
- Three qualifying questions on the booking form: company, what prompted the enquiry, which of the three shapes interests them
- Automatic confirmation and reminder emails
- Timezone detection on by default, which matters for the remote audience
- Embedded inline on `/contact`, opening in a modal from the header CTA

A booking removes the round-trip of a form. It also converts better, because the visitor's intent is at its peak at the moment they click.

### 8.2 Secondary — contact form

On `/contact` and `/training`. Fields:

| Field | Type | Required |
|---|---|---|
| Name | text | yes |
| Email | email | yes |
| Company | text | no |
| Interested in | select: Consulting / Training / Development / Not sure | yes |
| Message | textarea | yes |
| Preferred language | radio: EN / FR / ES | no |
| Consent | checkbox with privacy link | yes |

- Honeypot field plus time-to-submit check for spam, rather than a CAPTCHA. CAPTCHAs cost conversions and irritate exactly the senior people you want.
- Client-side and server-side validation; inline error messages, never an alert.
- On success, replace the form with a confirmation and a secondary suggestion to book a call directly.
- Backend: **Web3Forms** or **Formspree** for the static build; a Cloudflare Worker if the site moves to a platform that supports one. Do not build a mail server.

### 8.3 Tertiary — email capture

Footer and end of `/method`. One field. Honest framing about frequency and content. Buttondown or Listmonk; avoid anything that adds tracking pixels to a site whose selling point is data seriousness.

---

## 8bis. Copy patterns worth using

Observed on competitor pages that work, and applicable here.

**Name the products.** "Diagnostic", "POC" and "implementation" are categories, not products. A named, bookable thing with a fixed price, a duration and a promise converts better and is easier to talk about. Give the audit a name and put it in the navigation as a product rather than as a service category.

**Three words can carry a whole page.** A heading like *De l'audit à l'autonomie* states the offer, the philosophy and the endpoint at once. Aim for headings of that density rather than descriptive ones.

**Concrete negation.** "Not a PowerPoint vision — an executable plan" tells the reader what you are by naming what you refuse. Cheap, memorable, and it works because everyone has received the thing being refused.

**One-sentence self-definition.** Have a single sentence that says what you are and, by implication, what you are not. It should be repeatable by a client describing you to a colleague, which is how most referrals actually happen.

**A FAQ block on every offer page**, not only on the homepage. Five or six real objections, answered plainly. It carries FAQPage schema, it captures long-tail search, and it removes friction before the call. This is separate from the homepage objections section and should not duplicate it.

**Time-boxed promises.** "A first system in production in eight weeks" is a claim a prospect can hold you to, which is exactly why it is persuasive. Only publish one you will meet.

**Short declaratives.** "Every engagement has a planned end." "The data is the fuel." One idea per sentence, present tense, no hedging. French B2B prose in particular tends toward the periodic sentence; resist it.

---

## 9. Design direction

The failure mode for this kind of site is genericism — the gradient hero, the abstract network graphic, the four identical feature cards. It reads as templated and it undermines a proposition built on judgment.

**Position:** restrained, editorial, typographically confident. Closer to a serious publication than to a SaaS landing page.

**Typography.** A distinctive serif or high-contrast sans for headings; a clean, highly legible face for body text at 18px with generous line height. Two families maximum, three weights. Set body copy at a comfortable measure — 65 to 75 characters — which on its own does more for perceived quality than any decorative element.

**Colour.** A restrained neutral base — off-white or warm grey — with near-black text, and one accent colour used sparingly for the CTA and links. The accent should be unusual: deep green, oxblood, a strong slate blue. Avoid the default AI-sector blue-purple gradient entirely. Dark mode support, respecting `prefers-color-scheme`.

**Layout.** Generous vertical rhythm. Wide margins. Asymmetry rather than centred everything. Section transitions through whitespace and occasional background bands, not through borders.

**Imagery.** Almost none. One good portrait. Diagrams where they explain something — the three-step path, the audit timeline, the value-versus-effort quadrant — drawn as clean SVG, monochrome plus accent. No stock photography under any circumstances.

**Motion.** Minimal. Subtle fade-and-rise on section entry, 200–300ms, respecting `prefers-reduced-motion`. Nothing parallax, nothing that delays reading.

---

## 10. Technical specification

### Stack

**Astro**, static output. The right choice here: near-zero JavaScript by default, first-class i18n routing, content collections for case studies and courses, trivial Markdown authoring, and it deploys free on Cloudflare Pages, Netlify or Vercel.

Alternative if the developer prefers: Next.js static export or Eleventy. Not WordPress — the maintenance and security burden is disproportionate for nine pages.

- Styling: Tailwind, with a properly defined design-token layer in the config. Do not ship default Tailwind aesthetics.
- Content: Markdown/MDX in content collections, one file per language.
- Deployment: Cloudflare Pages. Automatic deploys from a Git repository, free, fast in Europe.
- Domain: `treguer.com`, with `automata.eus` redirecting if acquired.

### Structure

```
src/
  content/
    cases/        en/*.md   fr/*.md   es/*.md
    courses/      en/*.md   fr/*.md   es/*.md
    home/         en.md     fr.md     es.md    # hero, logo order, case order
  i18n/
    en.json   fr.json   es.json        # UI strings
  layouts/
    Base.astro
  components/
    Header  Footer  Hero  CTA  ServiceCard  StepList
    CaseCard  Testimonial  FAQAccordion  ContactForm
    LanguageSwitcher  LogoStrip
  pages/
    index.astro  audit.astro  training.astro  build.astro
    work/  about.astro  contact.astro  method.astro
    legal/
    fr/  … mirror
    es/  … mirror
```

All display strings in the i18n JSON files. No hard-coded English in components. The per-language `home/` content file carries the hero copy, the credibility strip ordering and the case study ordering, so the positioning differences in §2 are content changes rather than component branches.

Adding a fourth language should require a translation file, a content set and a page mirror — nothing else.

### Performance targets

- Lighthouse: 95+ on all four axes
- LCP under 1.5s on 4G
- Total page weight under 500KB for the homepage, fonts included
- Self-host fonts as WOFF2 subsets. No Google Fonts requests — a page selling data seriousness should not phone home to a third party on load.

### SEO

- Unique title and meta description per page and per language
- Open Graph and Twitter card images, generated per page
- JSON-LD: `Person`, `ProfessionalService`, `Course` on training pages, `FAQPage` on pages with accordions
- `hreflang` across all language pairs plus `x-default`
- XML sitemap covering both languages
- Semantic headings, one H1 per page
- Target terms worth building pages around, once the lead vertical is fixed: *audit IA entreprise*, *consultant IA indépendant*, *formation LLM entreprise*, *AI consultant industrial*, *consultoría IA industrial*, *auditoría de datos empresa*, *formación LLM empresas*, plus the geographic variants — Bayonne, Biarritz, Donostia, Bilbao, Gipuzkoa
- Spanish search competition in this niche is thinner than French or English. The `/es/` pages may well be the easiest organic wins on the site, which is a second argument for launching with them rather than deferring.

### Analytics and privacy

**Plausible** or **Umami**. Cookieless, GDPR-compliant, no consent banner required. Google Analytics would force a cookie banner onto a site whose proposition includes data seriousness, which is a poor trade for data you will barely use.

### Accessibility

WCAG 2.1 AA as the baseline, not an afterthought. Contrast ratios verified, full keyboard navigation, visible focus states, ARIA on the accordion and mobile menu, alt text everywhere, forms with real labels rather than placeholders.

### Legal

Mandatory in France: `mentions légales` with identity, SIRET, hosting provider details, and publication director. Privacy policy covering the form, the newsletter and analytics. Both pages in both languages.

---

## 11. Content to supply before build

The build cannot finish without these. Ordered by how long each takes to obtain.

- [ ] **Three testimonials with name, title and company.** Start now — this is the long pole. Vicomtech, ESTIA and Crédit Agricole are the likely sources.
- [ ] Portrait photograph, professional quality
- [ ] Three to five case studies, written, with anonymisation cleared where needed
- [ ] Written permission to name clients, or a decision to anonymise each
- [ ] Confirmed price points for all three shapes
- [ ] The Qualiopi decision, which determines the training page's funding section
- [ ] SIRET and legal entity details
- [ ] Final `/method` text, adapted from the methodology document
- [ ] Bio, long and short versions, all three languages
- [ ] CV as a downloadable PDF — English and Spanish versions, current
- [ ] **Native review of the Spanish copy** before launch, ideally by a contact at Vicomtech or ESTIA
- [ ] Decision on whether Vicomtech and ESTIA can be named on the Spanish pages, where it matters most

---

## 12. Build phasing

**Phase 1 — Launch.** Homepage, `/audit`, `/training`, `/build`, `/about`, `/contact`, legal pages. All three languages. Booking embed live. Case studies as a homepage section rather than separate pages. Ship this before it feels finished.

If the Spanish copy is not ready when everything else is, launch EN and FR and add `/es/` a fortnight later rather than delaying the whole site. The routing and content structure make this a content commit, not a rebuild.

**Phase 2 — Depth.** `/method` published in full, three languages. `/work` as its own section with individual case study pages. Testimonials inserted as they arrive. Newsletter live.

**Phase 3 — Reach.** Sector landing pages once the lead vertical is decided. Monthly writing, syndicated to LinkedIn.

### The real cost of three languages

Not the build — the maintenance. Every copy change is now three edits and a review cycle in a language you do not write professionally. Two consequences worth accepting now:

- **Freeze the copy after launch.** Treat it as a printed brochure, revised twice a year rather than tinkered with.
- **Keep the page count at nine.** The argument for a small site triples in force. Each new page is three pages.

---

## 13. Open decisions

- **Lead vertical.** Still unresolved, and it governs the case study selection, the sector pages in phase 3, and much of the homepage's problem framing. Everything else can proceed without it; these cannot.
- **Price display.** Recommended: show "from" anchors. The alternative — prices on request — will feel safer and will cost qualified traffic.
- **Qualiopi.** Determines whether the training page talks about OPCO funding, which materially changes its conversion.
- **Whether `/method` is gated.** Recommended: ungated HTML, gated PDF. Best of both.
- **Euskara.** Industrial B2B in Gipuzkoa and Bizkaia is conducted in Spanish, so a full Basque version would be effort without return. But euskara carries real institutional weight — SPRI, the clusters, Mondragón — and a token presence costs almost nothing: a Basque tagline in the footer, or a single short page. Worth asking a local contact whether it registers as respect or as decoration. If the `automata.eus` domain is acquired, this question answers itself more strongly.
- **Blog.** Deliberately excluded from phase 1. An empty blog is worse than no blog, and LinkedIn is the better channel until there is a publishing habit to prove.
