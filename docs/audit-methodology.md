# AI & Data Consulting — Methodology and Offer Architecture

*Working document — v0.2*
*Internal reference for delivery, source material for website and proposals*

---

## 0. Principles

Seven rules that make this an engagement rather than a report.

1. **The audit is a paid product, not pre-sales.** It has a price, a scope, a deliverable and an end date. It is useful even if the client never buys anything else. This is what separates a consultant from a vendor.
2. **One engine, two doors.** The client arrives through "we want to use AI/LLMs" or "we think our data is worth something". The fieldwork is 80% identical. Only the emphasis in Phase 3 differs.
3. **Everything is scored in euros.** No opportunity enters the deliverable without a value estimate, however rough. A range with stated assumptions beats a number with false precision, and both beat "significant potential gains".
4. **Feasibility is judged on data, not on models.** The model is almost never the constraint. Data availability, quality and access are.
5. **Display depth, deliver simplicity.** Clients must see that the full modern stack is available. They should almost never receive it. The recommendation is the simplest architecture that meets the business criterion, and the reasoning for that choice is itself part of the deliverable.
6. **Every engagement is designed to end.** Handover is planned from day one: documentation, training, and a client who could run the system without me. Continuing to operate it is then something they choose, not something they're stuck with. Dependency is easy to create accidentally and it corrodes the relationship the moment the client notices.
7. **The deliverable must survive without me.** It will be read by people I never met, months later. Self-contained, readable by a non-technical director, specific enough to act on.

---

## 1. Offer architecture

Four lines, not one ladder. Training and audit are both entry points; the other two are downstream of either.

```
        TRAINING  ────┐
                      ├──►  AUDIT  ──►  POC  ──►  IMPLEMENTATION  ──►  RUN
   direct enquiry  ───┘                                   │
                                                          └──►  ENABLEMENT
                                                              (training again)
```

| Line | Price | Duration | Role in the business |
|---|---|---|---|
| Training | €1,800–2,500/day | 1–3 days | Cash now, best acquisition channel, near-zero risk |
| Audit | €5,000–15,000 | 2–5 weeks | Qualification and positioning as advisor |
| POC | €18,000–35,000 | 4–8 weeks | Proof, and the real decision point |
| Implementation | €900–1,200/day | 2–6 months | Volume revenue |
| Run | €1,500–3,000/month | Ongoing | Revenue floor, and the path to a product |

The point of four lines is that a prospect who says no to one can say yes to another without the conversation ending.

---

## 2. Training line

The addition with the shortest path to revenue, and the one competitors treat as a core offer rather than a sideline.

### Catalogue

**A — GenAI for decision-makers.** One day, non-technical. What LLMs and agents can and cannot do, cost structures, security and AI Act obligations, how to identify opportunities internally, how to avoid the three standard ways these projects fail. Sold to management committees. Frequently converts into an audit, because by the afternoon the participants are naming their own use cases.

**B — Building with LLMs.** Two to three days, development teams. Prompt engineering beyond folklore, structured outputs, RAG architecture and its alternatives, agent orchestration patterns, evaluation, cost control, security. Minimum 60% hands-on — that is the benchmark the market now sets, and it is worth exceeding it.

**C — Data science fundamentals for industry.** Two to three days. Time series, anomaly detection, vision-based inspection, deployment and monitoring. Pitched at engineers who know their process and not the toolkit. This is directly transferable from existing master's-level teaching.

**D — Post-implementation enablement.** One to two days, built around the system just delivered. Sold as part of the implementation package rather than separately. It is also what makes handover credible when a client wants to own the system themselves.

### Funding — worth resolving early

In France, intra-company training is heavily subsidised through OPCOs, but only from a **Qualiopi-certified** provider. Without certification the client pays entirely from their own budget, which turns an easy sale into a hard one. Certification takes months and a real quality-management system.

The pragmatic route is to deliver through an already-certified partner — Simplon is certified, and the existing relationship there is the obvious place to test this. The partner invoices, takes a margin, the client draws on their OPCO allocation. Less revenue per day, far more days sold.

Spanish equivalent: **Fundae**, which works through registered providers on comparable logic. Worth checking whether a Gipuzkoa partner is easier to arrange than French certification.

### Why training is the best local acquisition channel

A workshop given free to a business association reaches people who are curious. A paid two-day course puts you inside a company for two days, with their engineers, looking at their actual systems, while they pay for the privilege. By day two you know their data landscape better than any audit questionnaire would reveal. The audit proposal writes itself, and it is no longer cold.

---

## 3. Audit — engagement shape

| | Standard | Extended |
|---|---|---|
| Duration | 2–3 weeks elapsed | 4–5 weeks |
| On-site | 2 days | 4–5 days |
| Interviews | 5–8 | 10–15 |
| Price | €5,000–8,000 | €12,000–15,000 |
| Target | SME, 50–300 staff | 300+, multi-site, or regulated |

Fixed price. Never a day rate at this stage — a day rate invites scope argument and frames the work as capacity rather than judgment.

**Timeline**

- **D0** — Kickoff (2h). Scope, stakeholder list, data access requests, definition of success for the sponsor.
- **D1–D3** — Desk phase. Document review, sector benchmark, interview guides.
- **D4–D6** — On-site. Interviews, process observation, data inspection.
- **D7–D10** — Analysis, scoring, valuation.
- **D11** — Draft sent 48h before restitution.
- **D12** — Restitution workshop, half-day, decision-makers present, mandatory.

The restitution is a working session, not a presentation. The client shortlists in the room. If the sponsor cannot commit to attending, the audit is not ready to start.

---

## 4. Phase 1 — Process and value mapping

Find where money is lost, time burned, or risk accumulated. Before any discussion of technology.

### Interview guide

Per function, 45–60 minutes. Talk to operators, not only managers — managers describe the process as designed, operators describe it as run.

**Operational reality**
- Walk me through a typical day. Where does the work actually wait?
- What do you do that feels repetitive or mechanical?
- Which task, if it disappeared tomorrow, would change your week most?
- What do you re-key from one system into another?
- What breaks most often, and what happens when it does?

**Decisions**
- What are the recurring decisions in your role? On what basis?
- When you get one wrong, what does it cost, and how do you find out?
- What would you want to know that you currently can't?
- Whose absence stops things? What do they know that isn't written down?

**Information flow**
- Where does the information you need come from? How does it arrive?
- What do you keep in a personal spreadsheet outside the official systems?
- What do you print?

**Volumes** — for every candidate process: occurrences per month, minutes per occurrence, people involved, error rate, cost of an error. Estimates and ranges are fine. This is the input to all valuation and the single most-skipped step.

### Outputs
- Process map with volume and cost annotations
- Pain inventory, raw and unfiltered
- Shadow-IT inventory — the personal spreadsheets and workarounds, which are the most reliable indicator of an unmet need
- Stakeholder map: who feels the pain, who owns the budget, who will resist

---

## 5. Phase 2 — Data and systems inventory

Establishes what is actually usable. This phase kills more opportunities than any other, which is its job.

### System inventory

Per system (ERP, CRM, MES, SCADA, historian, document store, email, spreadsheets):
- Vendor, version, hosting, administrator
- Export capability: API / database access / CSV / screen only
- Who owns access, and how long an access request takes in practice

### Data source assessment

| Dimension | What to establish |
|---|---|
| Volume | Rows / documents / images, and growth rate |
| History | How far back, and is it consistent? |
| Granularity | Per transaction, day, machine, batch? |
| Frequency | Real-time, hourly, daily, monthly, on request |
| Labelling | Are outcomes recorded? Are failures, defects, decisions traceable? |
| Quality | Missing rate, duplication, free-text pollution, unit consistency |
| Accessibility | Technical route to extract, and organisational permission |
| Sensitivity | Personal data, commercial confidentiality, contractual restriction |

### Data readiness score (0–5)

Applied per opportunity, not per company.

- **0** — Does not exist. Would require new instrumentation or capture.
- **1** — Exists but not recorded systematically (paper, verbal, individual habit).
- **2** — Recorded but not extractable without significant manual effort.
- **3** — Extractable, but quality or history insufficient as-is.
- **4** — Extractable and adequate; normal preparation work.
- **5** — Clean, accessible, historised, labelled. Ready immediately.

Anything at 0–1 is not a POC candidate. It becomes a "start collecting now" recommendation, which is a legitimate and often valuable output.

### Governance and security checkpoints

- Personal data present? Purpose, legal basis, retention. Refer to the DPO where one exists.
- Data leaving the premises? Cloud LLM APIs, external hosting, cross-border transfer. Establish the client's actual tolerance early — for some industrial and most financial clients this single question determines the whole architecture.
- Sector obligations: traceability (agri-food), part conformity and certification (aeronautics), regulatory reporting (finance).
- **EU AI Act classification** per opportunity: prohibited / high-risk / limited / minimal. HR, credit scoring, biometrics and safety-critical uses need care. Most industrial and back-office cases are minimal risk — stating that explicitly in writing removes an unspoken blocker that clients often carry without mentioning it.
- **Agent-specific security**, wherever an agent will have tool access or act on external input:
  - Prompt injection through documents, emails or web content the agent reads
  - Data isolation between clients, departments or privilege levels
  - Blast radius: what can the agent do wrong, and what is the worst case?
  - Human checkpoints on irreversible actions — payment, sending, deletion, commitment
  - **Agent identity.** Every agent gets its own credentials and its own permissions, never a shared service account and never a borrowed human login. An agent that acts under someone's identity is untraceable after the fact and impossible to revoke cleanly. Treat it as a named actor in the information system: who it is, what it may touch, who is accountable for it, and how it is switched off.
  - Audit logging of agent actions, which is also an AI Act obligation for some categories
- Ownership of models, prompts, fine-tunes and derived data. Settle it in the audit rather than later under pressure.

---

## 6. Phase 3 — Opportunity generation

Same fieldwork, two lenses. Run both regardless of which door the client came through — the cross-sell is often the real value of the audit.

### Lens A — Data science / predictive

- **Prediction** — Is there a recurring outcome known too late? Failure, churn, delay, defect, demand, absence.
- **Detection** — Is someone visually or manually inspecting things? Quality control, anomaly detection, monitoring, reconciliation.
- **Optimisation** — Is a schedule, route, mix, price or stock level set by habit?
- **Segmentation** — Are heterogeneous customers, products or machines treated identically?
- **Measurement** — Is a metric that drives decisions unmeasured or measured badly?

Industrial patterns worth checking every time: predictive maintenance on instrumented equipment, vision-based quality control, scrap and yield optimisation, energy consumption forecasting, demand planning.

### Lens B — LLM / agents / automation

- **Document flow** — What arrives as unstructured text and is manually transcribed, classified or routed? Invoices, orders, specifications, claims, CVs, tenders, contracts.
- **Knowledge access** — Where do people spend time *looking for* information? Technical documentation, procedures, past projects, contract terms.
- **Drafting** — What text is produced repeatedly from a template plus judgment? Quotes, reports, responses, summaries, tender answers.
- **Multi-system workflows** — What sequence spans several systems with a human as the transport layer between them?
- **Interaction** — Where is a human answering the same questions repeatedly?

**Autonomy ladder** — assign a target level to each agent opportunity. This manages expectations better than any other single device.

1. **Assist** — human works, AI suggests
2. **Draft** — AI produces, human validates every output
3. **Exception** — AI executes, human handles flagged cases only
4. **Autonomous** — AI executes, human audits afterwards by sampling

Almost everything worth doing starts at level 2. Promising level 4 on a first engagement is how these relationships end badly. State the level intended now and the level intended at twelve months; the gap is the roadmap.

### Cross-lens combinations

The strongest opportunities usually combine both: an agent reads and routes documents, feeding structured data to a predictive model whose output triggers an alert that another agent drafts a response to. These have the most defensible ROI and they justify the run retainer.

---

## 7. Phase 4 — Scoring and prioritisation

### Per-opportunity fiche

```
ID / Name
One-line description in the client's own vocabulary
Business problem addressed
Affected function and volumes (from Phase 1)
Approach — data science / LLM-agent / hybrid
Data sources required + readiness score per source
Estimated annual value (range + explicit assumptions)
Estimated build cost (POC / full implementation)
Estimated run cost — infrastructure, tokens or inference, maintenance
Time to first value
Autonomy level: now / +12 months
Risks — technical, organisational, regulatory, security
AI Act classification
Prerequisites and dependencies
Recommendation: POC now / prepare (specific action) / discard (reason)
```

### Scoring grid

Four axes, 1–5 each. Weighted composite for ranking; publish the individual scores so the client can reweight to their own priorities.

**Business value (×3)** — annual euro impact
1: <€10k · 2: €10–30k · 3: €30–100k · 4: €100–300k · 5: >€300k

**Data readiness (×2)** — the *worst* score among required sources, not the average. The weakest source gates the project.

**Implementation effort (×2, inverted)**
1: >6 months or new infrastructure · 2: 3–6 months · 3: 6–12 weeks · 4: 3–6 weeks · 5: <3 weeks

**Adoption risk (×2, inverted)** — organisational, not technical
1: threatens roles, no sponsor, contested · 2: significant change management · 3: neutral · 4: users have asked for it · 5: users are already improvising a manual version

Optional fifth axis for regulated or security-sensitive clients: **regulatory and security friction**.

### Unit economics for LLM opportunities

Any agent or LLM opportunity gets a cost line before it is recommended, because run cost can quietly exceed the value created.

- Cost per transaction: tokens in and out, model chosen, retrieval calls, retries
- Monthly cost at current volume, and at three times current volume
- Sensitivity to model choice — a frontier model against a smaller or open-weight one, and what the quality difference is actually worth here
- Levers available: prompt caching, batching, routing simple cases to a cheaper model, self-hosting above a volume threshold

A recommendation that proposes a frontier model everywhere is not a recommendation, it is a default. The reasoning about where cheap is good enough is a large part of what the client is paying for.

### Exit cost — assess it before entering

Borrowed from negotiation practice, and it belongs in every architecture decision: before committing the client to a provider, establish what leaving would cost. This is not a philosophical objection to cloud services. It is a number, and knowing it is what lets the client negotiate rather than accept.

Per major dependency — model provider, cloud, vector store, any SaaS component:

- What would migrating away cost, in weeks and in euros?
- Is the data portable in a usable format, or only as an export nobody can read?
- Is there a credible alternative today, including an open-weight or self-hosted one?
- What is the realistic probability this vendor changes its pricing, its terms, or disappears?

Two practical consequences worth designing in from the start: keep the model provider behind an abstraction so switching is a configuration change rather than a rewrite, and keep the client's data and prompts in their own systems rather than inside a vendor's platform.

Clients rarely ask for this and they notice it when it appears in the deliverable, because it is the part that is visibly not sales.

### Portfolio view

Value against effort, four quadrants, named plainly:

- **Do now** — high value, low effort. The POC comes from here.
- **Plan** — high value, high effort. Roadmap, needs sequencing.
- **Fill in** — low value, low effort. Good for internal confidence; good candidates for the client's own team.
- **Leave** — low value, high effort. Say so explicitly. Declining something the client was excited about is the most credible move in the whole document.

Plus a fifth category outside the grid: **prepare** — blocked only by data readiness 0–1, with the specific collection action that unblocks it. These become next year's engagements.

---

## 8. Deliverable structure

25–35 pages, in the client's language (FR/ES/EN), in their vocabulary.

1. **Executive summary, 2 pages.** Three recommended actions, total value at stake, recommended first step and its cost. Readable alone. Write it last.
2. **What we observed.** Process and data reality, stated factually. The client must recognise their own company here, including the uncomfortable parts.
3. **Opportunity portfolio.** Ranked table, value/effort chart, transparent scoring.
4. **Opportunity fiches.** One page each, ranked.
5. **Recommended POC.** Objective, business success criteria, scope boundaries, data required, timeline, cost, what the go/no-go decision looks like.
6. **12–18 month roadmap.** Sequenced, with dependencies, including the "prepare" items and any collection to start now.
7. **Prerequisites and governance.** Skills, infrastructure, data governance, AI Act positioning, security posture, ownership of models and data.
8. **Appendices.** Interviews, systems inventory, data inventory, full valuation assumptions.

Always included regardless of findings: **one thing the client can do themselves next week at zero cost.** The cheapest credibility available.

---

## 9. POC, implementation, run

### POC — €18,000–35,000, 4–8 weeks

Conditions agreed in writing at kickoff, before signature:

- Success criteria as a **business metric**. "Reduces manual invoice handling from 12 minutes to under 4", not "F1 above 0.85".
- Named data owner, access granted before D0 rather than promised.
- Named decision-maker who will attend the restitution.
- A **decision date** and an indicative implementation budget on paper.
- What happens on failure, stated explicitly. A documented no-go is a legitimate successful outcome and should be priced as one.

The main risk in this business model is a delighted client, no deployment and no revenue. Those five conditions are the defence. A client who refuses all five has told you something useful.

**Evaluation is a POC deliverable, not an afterthought.** Every LLM or agent POC hands over an evaluation harness: a golden dataset of representative cases with expected outputs, automated scoring — deterministic checks where possible, model-graded where not — and a baseline score to measure future changes against. Without it the client cannot tell whether a model update improved or degraded their system, and they will discover this the hard way. Being the consultant who built the harness is also what makes the run contract obvious rather than a negotiation.

### Implementation — €900–1,200/day, or fixed-price packages

Production build, integration, monitoring and alerting, documentation, user training, handover.

**Name the two exits at kickoff**, because they change the architecture and because leaving it vague is how dependency happens by accident:

- **Handover.** The client's team operates the system. This requires documentation written for someone who wasn't there, a technology stack their people can actually maintain, and training built into the project rather than bolted on at the end.
- **Operation.** I run it under a monthly retainer. The client can still trigger the handover later, and the handover package is prepared regardless.

Either way the client ends up able to leave. That is the point, and it is worth stating on the website: an engagement that cannot end is a dependency, not a service.

Deployment practices for anything LLM-based: staged rollout rather than a flip of the switch — a shadow period where the system runs alongside the humans without acting, then a limited cohort, then general use, with a rollback path at each stage.

### Run — €1,500–3,000/month

- Performance monitoring and drift detection
- Scheduled re-running of the evaluation harness, with alerting on regression
- **Reasoning observability** — for agent systems, logging the decision path rather than just inputs and outputs. When an agent does something unexpected, the question is always *why did it choose that*, and without traces there is no answer. Build it in from the first version; retrofitting is painful.
- Model version migration — deprecations arrive with little notice and break things quietly
- Prompt and retrieval maintenance as source documents and processes change
- Cost monitoring against the agreed budget, including caching effectiveness
- Quarterly review and a small incremental improvement allowance

Two reasons this matters beyond the revenue. Production LLM systems degrade in ways clients do not anticipate and cannot diagnose. And the run phase is where the same problem seen across five clients becomes a product.

---

## 10. Technical competence map

Not a delivery plan. This is what the website must demonstrate and what a technically literate buyer will probe. Depth on display, simplicity in delivery.

**Model selection and context.** Arbitrage across frontier and open-weight models — Claude, Gemini, GPT, Mistral, Llama, Qwen. Context window economics, prompt caching, structured outputs, system prompt design. Model Context Protocol for tool and data integration.

**Retrieval.** Chunking strategies and where they break, embedding choice, vector stores, hybrid dense/sparse retrieval, re-ranking, graph-based retrieval for relational corpora. Equally: knowing when retrieval is not the answer and a long context window or a plain database query is.

**Orchestration.** Agentic patterns — ReAct, plan-and-execute, reflection, multi-agent decomposition. LangChain, LangGraph, CrewAI and the direct-API alternative. A judgment worth stating publicly: most production systems do better with a constrained workflow and one or two tool calls than with a fully autonomous agent loop.

**Evaluation and reliability.** Golden datasets, deterministic assertions, model-graded evaluation, regression testing, human review sampling, monitoring in production.

**Cost engineering.** Token accounting, caching, batching, model routing by case difficulty, the self-hosting threshold and how to calculate it honestly.

**Security.** Prompt injection defence, data isolation, tool permissioning, output validation, audit logging, AI Act compliance.

**Deployment.** Cloud APIs, the managed platforms (Vertex AI, Bedrock, Azure OpenAI), self-hosted inference (vLLM, Ollama, llama.cpp), and on-premise for clients who cannot let data leave. **On-premise capability is a genuine differentiator locally** — industrial clients and anyone handling confidential design or process data ask this question early, and most consultancies answer it badly.

**Classical ML and signal**, which does not disappear because LLMs exist: time series, computer vision, anomaly detection, forecasting, and the MLOps around them.

---

## 11. What goes on the website, and what stays here

| Section | Public | Form |
|---|---|---|
| §0 Principles | Yes | Rewritten as the "how I work" page — this is the differentiator |
| §1 Offer architecture | Yes | The core diagram plus price ranges |
| §2 Training | Yes | Full catalogue, one page per course |
| §3 Audit shape | Yes | Timeline and deliverable list — publishing this sells it |
| §4–5 Interview guides, inventory | Partly | Condensed. Enough to show rigour, not a fill-in-yourself kit |
| §6 Two lenses | Yes | Reworked into "what this looks like in your business", by sector |
| §7 Scoring grid | Yes | Publishing the criteria is unusual and strongly credible |
| §8 Deliverable structure | Yes | With an anonymised sample extract once one exists |
| §9 POC conditions | Yes | Stating them publicly pre-qualifies buyers |
| §10 Competence map | Yes | A technical page, written flat, no adjectives |
| §11 This table, pricing strategy, partner arrangements | No | — |

Site shape: five to seven pages, three languages, one call to action throughout — book the audit, or book a training day. Resist anything larger; a big site is a way of avoiding prospects.

---

## 12. Positioning note

The comparable offer at scale is a well-resourced consultancy with a salaried GenAI expert: broad stack, strong training, large accounts, and a day rate to match. Competing on stack breadth against that is unwinnable and unnecessary.

**They have told us where the gap is.** The largest AI engineering firm in this market defines itself publicly as a builder rather than a strategy firm: consultancies define the strategy, they industrialise the systems. Their entry product is a free thirty-minute diagnostic that leads to an eight-week production project. That model works for a client who already knows what they want built. It does nothing for a 150-person manufacturer who suspects there is value somewhere in their operation and cannot name it.

That is the ground this practice occupies, and it is the reason the audit is a paid deliverable rather than a sales call. Worth saying so on the website in one line, because a prospect comparing a €5,000 diagnostic with a free one deserves to understand the difference: one produces a ranked, costed portfolio they own; the other produces a proposal.

Three things a large firm structurally cannot offer a 150-person manufacturer in Bayonne or Irun:

**The person who audits is the person who builds.** No handover from the pre-sales expert to a delivery team the client has never met.

**Fluency in the business, not only the technology.** Fifteen years in structured products and asset management means the ROI conversation happens in the client's language, with a CFO, without a translator. That is unusual among AI consultants and it is the thing that makes the value estimates in §7 credible rather than decorative.

**Both sides of the border, natively.** French and Spanish, existing links at ESTIA and Vicomtech, physical presence. A Bordeaux or Madrid consultancy flies in; that is a different relationship and clients know it.

The correct framing is therefore not "cheaper than SFEIR" but "a different animal": senior judgment, local presence, one person accountable end to end, and the discipline to recommend the boring solution when it is the right one.

---

## 13. Reusable assets

Ordered by leverage. Each engagement should improve at least one.

- Interview guides, per function and per sector
- Systems and data inventory template
- **Volume/cost capture sheet** — drives all valuation, build this next
- Scoring grid as a spreadsheet with exposed weighting
- Opportunity fiche template
- Deliverable template, FR/ES/EN
- **Opportunity pattern library** — accumulated anonymised fiches, sector-tagged. After five audits this is the fastest part of the work and the most convincing part of a sales conversation.
- Standard valuation assumptions: loaded hourly cost by role and country, error-cost heuristics, token and infrastructure baselines
- Evaluation harness template, reusable across agent projects
- Training materials and labs, per course, versioned
- Proposal and contract templates, including IP and model-ownership clauses

---

## 14. Open questions

- Publish the methodology in full or condensed? *Leaning to full. The map sells the guide and filters for clients who understand they need a person rather than a PDF.*
- Qualiopi: certify independently, or deliver through a certified partner? Resolve before building the training pages, since it determines how they are priced.
- Standard audit at €5k or €8k? Test both across the first three proposals and see which stall.
- Which vertical leads the case studies — still open.
- Fixed-price implementation packages per recurring pattern, once the pattern library exists.
- Whether the free 90-minute association workshop is still worth doing now that paid training is the better acquisition channel. Possibly as a loss-leader for clusters only.
