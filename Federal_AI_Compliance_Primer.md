# Federal AI Compliance Primer

*A plain-English reference for selling Mission Workforce Infrastructure into the federal government. How the government authorizes, buys, and runs software and AI, and where ManTech's offering plugs in.*

> Note: federal AI policy is moving fast. The frameworks below are stable; the specific OMB memos and executive orders change with administrations. Confirm the current versions before quoting them externally.

---

## The one idea to anchor on

A federal agency cannot legally run a new system on its network until a senior official signs a document accepting the risk. That signature is called an **Authority to Operate (ATO)**. Everything in federal compliance exists to get to, and keep, that signature.

So the real sale is not "our AI is good." The real sale is **"our AI will get through your authorization process and survive your oversight."** That is exactly why the brief leads with governance.

---

## Part 1 — How the government authorizes ANY system (RMF and the ATO)

This applies to all federal IT, AI or not. It is the backbone.

### FISMA
The **Federal Information Security Modernization Act** is the law that requires every federal system to be secured to a common standard. It points to NIST (the National Institute of Standards and Technology) for the actual rules.

### The Risk Management Framework (RMF) — NIST SP 800-37
The step-by-step process an agency runs to authorize a system. Seven steps:

1. **Prepare** — set roles, risk tolerance.
2. **Categorize** — how bad is it if this system's data is breached, altered, or goes down? Rated Low / Moderate / High (per FIPS 199) across Confidentiality, Integrity, Availability.
3. **Select** — pick the required security controls from the catalog (**NIST SP 800-53**, ~1,000 controls; the set scales with the Low/Moderate/High rating).
4. **Implement** — actually build the controls in.
5. **Assess** — an independent assessor tests whether the controls work.
6. **Authorize** — the **Authorizing Official (AO)**, a senior government executive, reviews the package and signs the **ATO** (or denies it, or grants a time-limited interim authority).
7. **Monitor** — Continuous Monitoring ("ConMon") forever after. An ATO is not permanent; it must be maintained.

### The authorization package (the paperwork the AO signs off on)
- **SSP** (System Security Plan) — what the system is and how each control is met.
- **SAR** (Security Assessment Report) — the assessor's findings.
- **POA&M** (Plan of Action and Milestones) — the list of known gaps and the plan to fix them.

**Why this matters for the pitch:** when the brief says "auditable, project-centric data persistence" and "every action, source, and decision path is logged and traceable," that is control evidence the AO needs. A Mission Assistant that logs everything makes the SSP/SAR easier to produce, which shortens time-to-ATO. That is a concrete selling point to a CISO/AO, not marketing.

---

## Part 2 — The AI overlay (what is added on top of RMF for AI systems)

AI does not replace RMF; it adds extra expectations on top.

### NIST AI Risk Management Framework (AI RMF 1.0, Jan 2023)
A voluntary framework with four functions. Memorize these four words; they are how AI governance people think:

- **Govern** — policies, accountability, roles, culture for managing AI risk.
- **Map** — understand the context: what is the AI for, who does it affect, what could go wrong.
- **Measure** — test and monitor it: accuracy, bias, drift, robustness.
- **Manage** — act on the risks: mitigate, escalate, decide whether to deploy.

There is also a **Generative AI Profile** (NIST AI 600-1, 2024) for LLM-specific risks (hallucination, data leakage, etc.).

**Mapping to the brief's four controls (this is the money slide for a CAIO):**
| The brief's control | NIST AI RMF function |
|---|---|
| Humans stay in command / accountability | **Govern** |
| It knows when to stop / understands its task scope | **Map** |
| It watches itself (drift, accuracy monitoring) | **Measure** |
| It escalates and routes judgment to humans | **Manage** |

### OMB memos (the binding policy for federal agencies)
OMB (Office of Management and Budget) tells agencies what they must do. The lineage:

- **EO 13960 (2020)** — first required agencies to publish **AI use case inventories**.
- **OMB M-24-10 (Mar 2024)** — created the **Chief AI Officer (CAIO)** role at each agency, agency AI governance boards, and **minimum practices for "safety-impacting" and "rights-impacting" AI** (testing, impact assessment, human oversight, monitoring).
- **OMB M-25-21 and M-25-22 (Apr 2025)** — replaced M-24-10 under the new administration. More pro-adoption/innovation in tone, but they **keep the CAIO, keep the AI use case inventories, and keep risk-management minimum practices for "high-impact AI."** M-25-22 specifically covers **AI acquisition**.

**What you need to know:** regardless of which memo is current, three things persist and the brief should always speak to them:
1. **A CAIO exists at the agency** and is a key stakeholder/approver.
2. **High-impact AI** must have documented risk management: pre-deployment testing, ongoing monitoring, and **human oversight**.
3. Each AI system becomes a **documented use case** in the agency's inventory (purpose, data, oversight, risk controls).

**Why this matters for the pitch:** "human-in-the-loop by design" is not a nice-to-have, it is literally a federal minimum practice for high-impact AI. The brief is pre-answering the CAIO's checklist. Saying "each deployed assistant is documented as a discrete use case ready for your inventory" tells the CAIO you will reduce their paperwork, not add to it.

---

## Part 3 — Cloud and data protection (where it runs and how data is guarded)

### FedRAMP (civilian cloud)
**Federal Risk and Authorization Management Program.** A standardized RMF specifically for cloud services. A cloud offering gets a FedRAMP authorization at Low / Moderate / High baseline, and agencies can then reuse it ("do once, use many"). If a Mission Assistant runs in a cloud, that cloud needs to be FedRAMP-authorized. (FedRAMP is being modernized under a "20x" initiative to speed this up.)

### DoD cloud (Defense)
DoD adds its own layer on top of FedRAMP via the **DISA Cloud Computing SRG**, using **Impact Levels (IL)**:
- **IL2** — public/non-critical data.
- **IL4** — Controlled Unclassified Information (CUI).
- **IL5** — higher-sensitivity CUI and unclassified National Security Systems.
- **IL6** — classified up to SECRET.

A DoD customer will ask "what IL are you authorized for?" the way a civilian agency asks "what FedRAMP level?"

### CUI and CMMC
- **CUI (Controlled Unclassified Information)** — sensitive-but-unclassified data, protected per **NIST SP 800-171**.
- **CMMC 2.0 (Cybersecurity Maturity Model Certification)** — defense contractors handling CUI must be certified at the required level. Phasing into contracts through 2025 onward.

### Classified and disconnected environments
Some missions run **air-gapped** (no internet) or in classified enclaves. This is why the brief's line "containerized for restricted and unrestricted environments, deployable cloud-connected or disconnected" is a real differentiator: many AI vendors are cloud-only and simply cannot play in IL5/IL6 or air-gapped spaces. ManTech's AI Sandbox and containerization are the proof points here.

---

## Part 4 — How ManTech's system maps to all of this (the talk track)

What ManTech already has, and what each piece answers:

| ManTech asset / claim | The compliance question it answers |
|---|---|
| Auditable, project-centric data persistence; full logging | Provides the **control evidence** for the SSP/SAR; shortens time-to-ATO |
| Human-in-the-loop, four controls | Meets the **high-impact AI minimum practices** (human oversight) and maps to **NIST AI RMF** |
| Containerized, restricted/unrestricted, disconnected | Lets it operate at **IL4/5/6** and in **air-gapped** enclaves where cloud-only vendors cannot |
| Runs on the Modern Data Platform (Oracle, zero-trust) | A **FedRAMP-authorized**, governed data foundation under the AI |
| 80% cleared workforce, 45% veterans | The **cleared operators** needed to build and run systems in secure spaces |
| Documented per-assistant use case | Drops straight into the agency's **AI use case inventory** for the CAIO |
| "Operate, not sell" | Supports **continuous monitoring (ConMon)** that an ATO requires forever |

### Where the honest gaps are (be ready for these)
- **"Design intent" vs. "authorized."** The brief says the assistants are *designed* to map to these frameworks. That is not the same as a completed ATO or a FedRAMP authorization for the specific assistant. The source note already hedges this; in conversation, be clear that authorization is established per system and environment.
- **Two deployed assistants, not twelve.** The roadmap is honest, but expect "show me it working in my environment," which is exactly what the 12-week pilot is for.
- **Acquisition path.** You chose to skip pricing, which is fine, but a CO (Contracting Officer) still has to buy it through a vehicle. OMB **M-25-22** is the AI acquisition guidance they will lean on. You do not need pricing in the brief, but be ready to name a contract vehicle when asked.

---

## Part 5 — Who actually signs, and in what order

The federal buying-and-authorizing cast, so you know who you are really selling to:

1. **Mission/Program Owner** — feels the pain, wants the capacity. Your champion. (The brief is written for them.)
2. **CAIO (Chief AI Officer)** — must bless it as responsible AI; owns the use-case inventory.
3. **CISO / ISSO** — owns security; shepherds the RMF package.
4. **Authorizing Official (AO)** — signs the **ATO**. The gate.
5. **Contracting Officer (CO)** — executes the actual purchase on a contract vehicle.

The pilot's "Weeks 1-4: Baseline and Authorization" phase exists to get steps 2-4 moving early, so the deal does not die at the AO's desk after the technology already proved itself.

---

## The 60-second version

- Nothing runs without an **ATO**, signed by an **AO**, earned through the **RMF** (NIST 800-37 / 800-53), maintained by **continuous monitoring**.
- AI adds the **NIST AI RMF** (Govern, Map, Measure, Manage), the **CAIO**, **AI use-case inventories**, and **human-oversight minimum practices** for high-impact AI (per the current OMB memo).
- Cloud adds **FedRAMP** (civilian) or **DoD Impact Levels** (defense); sensitive data adds **CUI / 800-171 / CMMC**; secret spaces add **classified / air-gapped** requirements.
- ManTech's edge: **auditable logging, human-in-the-loop, disconnected/containerized deployment, a cleared workforce, and an operate-not-sell model** — every one of which answers a specific question on the authorizer's checklist.
- The brief is engineered to pre-answer that checklist, which is how you shorten the path to the one signature that matters.
