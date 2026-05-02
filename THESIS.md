# Platform First: Why the AI Winners in Regulated Industries Will Be Built on Standard Engineering

**Brian Pelow · May 2026**

---

## The Wrong Question

Every board meeting in regulated financial services and manufacturing has the same agenda item now: *What is our AI strategy?*

It is the wrong question.

Not because AI is unimportant — it is the most significant shift in engineering productivity in a generation. But because the question presupposes that AI strategy is separable from engineering strategy. In regulated industries, it is not. The organizations asking "what is our AI strategy?" are about to learn an expensive lesson that the data has already made clear: AI fails in regulated environments at the governance and data layer, not the model layer. And the governance and data layer is, and has always been, platform engineering.

The right question is: *Is our platform ready to make AI deployable?*

Most are not. And the gap between organizations that understand this and those that do not will define the competitive landscape in regulated industries through the end of this decade.

---

## What the Data Actually Says

The numbers are striking in their consistency. Only 28% of AI initiatives in infrastructure and operations fully meet ROI expectations. In banking specifically, just 32% of institutions report revenue growth from AI investment, and only 36% report meaningful cost reduction — despite billions deployed. Half of the institutions that underperformed cited governance and compliance barriers as the primary constraint. Not model quality. Not data science talent. Not compute costs. Governance.

This is not a technology problem. It is an architecture problem. Organizations attempted to deploy AI on top of infrastructure that was never designed to support it: narrative-based compliance controls that cannot be evaluated programmatically, change management processes that require human review cycles measured in days, deployment pipelines with no automated policy enforcement, and audit trails assembled by hand after the fact.

AI systems — particularly agentic systems — cannot operate in this environment. An agent executing a deployment at 2:00 AM cannot pause while a compliance officer reads a PDF of SOX controls and decides whether the change is permissible. The controls have to be code. The enforcement has to be automatic. The audit trail has to be generated, not assembled.

This is not a new insight. It is the logical endpoint of a decade of platform engineering thinking — applied now, with urgency, because the cost of not doing it has become visible.

---

## The Cost of Staying Still

Before making the case for what to build, it is worth quantifying what the current state actually costs — because this is not a theoretical risk. It is a current operating expense that most organizations have simply accepted as normal.

Manual compliance operations in a mid-sized regulated financial institution typically consume 15 to 20 percent of total engineering capacity. Change advisory board processes add two to five days of lead time to every production deployment. SOX audit preparation consumes four to eight weeks of engineering and operations time per year. When a compliance control fails — a missed evidence artifact, an undocumented change, a configuration drift — the remediation cost ranges from tens of thousands of dollars for a minor finding to tens of millions for a material weakness.

More importantly, these costs compound in the AI era. Every AI use case deployed on top of manually-governed infrastructure inherits the full cost of that governance. A deployment pipeline that takes five days to clear a human CAB review cannot support an agentic SDLC operating at the speed of software. The cost of inaction is not static — it grows proportionally with every AI initiative the organization attempts to run through infrastructure that was not designed for it. Organizations that delay this investment are not saving money. They are deferring a cost that will be larger, and more urgent, when they finally face it.

---

## The Commoditization Argument

There is a second force compressing the timeline. AI inference costs are declining approximately 10x annually — faster than PC compute during the microprocessor era. The model itself is commoditizing. GPT-4 level capability is available today for a fraction of what it cost eighteen months ago. Open-weight models running on commodity hardware are closing the gap with frontier models for the majority of enterprise use cases.

What this means is that model access is not a durable competitive advantage. Every organization will have access to capable models. The durable advantage is the organizational capability to deploy those models responsibly, govern their outputs, audit their decisions, and maintain regulatory standing while doing so.

That capability does not come from the model vendor. It comes from the engineering organization. Specifically, it comes from the platform engineering organization that has built the infrastructure to make AI deployable in the first place.

The organizations currently racing to deploy AI on top of fragile, manually-governed infrastructure are building a liability, not an advantage. When the model costs converge — and they will — the differentiator will be who can actually run AI in production in a regulated environment without creating audit findings, compliance violations, or operational failures.

---

## Machine-Readable Controls: The Prerequisite Nobody Is Talking About

The most underappreciated transformation in regulated engineering right now is not AI itself. It is the rewriting of narrative-based compliance controls into machine-readable formats.

Most compliance programs in financial services and manufacturing today are built on documents. SOX ITGC controls live in Word files. Change management procedures live in policy manuals. PCI-DSS requirements are mapped in spreadsheets. These documents are authoritative but they are not executable. A human reads them, interprets them, and makes a judgment. That judgment is recorded somewhere, usually in another document.

This model breaks completely in an agentic environment. It also breaks — more slowly, but just as certainly — in any environment where the pace of change exceeds the capacity of human reviewers to keep up.

Machine-readable controls solve this. When a SOX ITGC change management requirement is expressed as an OPA policy, it can be evaluated in milliseconds at the point of pipeline execution. When a PCI-DSS requirement is expressed as a structured rule, it can be continuously monitored rather than spot-checked at audit time. When compliance evidence is generated automatically by the deployment pipeline rather than assembled by hand, the cost of an audit drops by an order of magnitude and the quality of evidence improves simultaneously.

This is not theoretical. The technology exists today. Open Policy Agent, policy-as-code frameworks, and structured compliance libraries are production-ready. The CLARITY Act and GENIUS Act in the United States have already mandated in-ledger rule enforcement for digital assets — regulators are ahead of most engineering organizations on this curve, and their direction of travel is unambiguous.

One important caveat deserves honest acknowledgment. Machine-readable controls are an architectural solution, not a legal one. When an encoded policy misinterprets a regulatory requirement and an institution relies on it in good faith, the question of liability — whether it falls on the engineer who wrote the policy, the institution that deployed it, or the regulator whose narrative control was ambiguous — is not yet settled. Cross-jurisdictional complexity compounds this: a European institution operating simultaneously under EBA guidelines, DORA requirements, and ECB supervisory expectations faces a compliance surface that cannot be fully harmonized in a single policy engine today.

These constraints argue for a deliberate sequencing strategy. Encode the controls with the clearest, least ambiguous regulatory language first — change management gate criteria, image build standards, and deployment environment requirements are good starting points because their pass/fail criteria are well-defined. Document every interpretive choice made during encoding as a formal Architecture Decision Record, treating the encoding process itself as an auditable artifact. When presenting encoded controls to a supervisory authority, lead with the evidence trail the system generates automatically — regulators respond well to complete, consistent, machine-generated audit packages — and have human-readable rationale available for every policy decision. Build human review checkpoints at the boundaries of regulatory ambiguity rather than eliminating human judgment entirely. The direction is right. The timeline requires humility and the implementation requires discipline.

The question is not whether machine-readable controls will become standard. It is whether your organization will make the transition proactively or reactively — and whether the audit finding that forces the reactive version will be a minor observation or a material weakness.

---

## The Agentic SDLC Is Not Optional

The McKinsey framing is useful here: a single engineer managing twenty to thirty agents to deliver an outcome. Not a future state — a near-term operational reality in the organizations investing seriously in engineering productivity.

An agentic software development lifecycle changes every assumption about how engineering work gets done. Agents write code, generate tests, open pull requests, scan for vulnerabilities, and propose deployments. The engineer's role shifts from execution to orchestration and judgment. The throughput of a single engineer — measured in features shipped, incidents resolved, technical debt addressed — expands dramatically.

But this only works if the guardrails are automated. In a regulated industry, an agent that can propose a deployment cannot be trusted to self-certify compliance. The compliance check cannot be a human review step inserted between the agent and production — that eliminates the productivity gain entirely. The compliance check has to be a machine, evaluating machine-readable rules, generating machine-readable evidence, at pipeline speed.

This is why the agentic SDLC and machine-readable controls are not two separate ideas. They are the same idea from different angles. You cannot have one without the other in a regulated environment. An agentic SDLC built on narrative controls is an audit finding waiting to happen. Machine-readable controls without agentic automation are infrastructure underutilized. Together, they are the architecture of a regulated engineering organization that can actually move.

The infrastructure required to support this at scale is worth naming explicitly. An agentic SDLC in a regulated environment requires a service registry that knows what is deployed and where, a policy engine designed for sub-second evaluation at pipeline throughput rather than human-scale review cycles, an observability stack that monitors agent behavior with the same rigor applied to production services, and an audit trail generation layer that is a first-class output of every pipeline run rather than an afterthought. Agent observability is the hardest of these to build — the question of how a regulated institution detects in real time that an agent has exceeded its compliance boundaries, and what the automated response should be, remains an active engineering frontier. Organizations building in this space should plan for human escalation paths while agent observability tooling matures. This is not a reason to delay the other three components. It is a reason to build them in the right order.

---

## The Practical Path

None of this requires a multi-year transformation program before value is realized. The pattern is the same as any technical debt reduction: start with the controls that gate your highest-risk deployments, encode them first, and build out from there.

**Start at the deployment gate.** The change advisory board process is the highest-friction, highest-value target. Automating CAB package generation, risk scoring, and deployment approval from pipeline signals eliminates the manual bottleneck that most regulated engineering organizations cite as their primary delivery constraint — reducing time-to-production by days and eliminating the majority of manual CAB preparation cost in the first year.

**Encode controls at the policy layer, not the application layer.** OPA and similar policy engines allow compliance rules to be expressed once and enforced everywhere — across deployment pipelines, API gateways, and eventually agent execution environments. This is the architectural investment that makes everything else composable.

**Build the audit trail into the pipeline.** Every deployment decision, every policy evaluation, every compliance check should produce structured evidence automatically. The goal is an audit where the evidence package is generated by the system, not assembled by the team — reducing audit preparation from weeks to hours.

**Treat the platform as the AI governance layer.** The service registry that tracks what is deployed and where. The policy engine that enforces what is permitted. The observability stack that monitors what is happening. These are not separate from AI governance — they are AI governance in a platform engineering organization. Build them once, apply them everywhere.

---

## The Compounding Advantage

The organizations that make this investment early do not simply reduce their compliance costs. They build a structural advantage that compounds with every subsequent AI initiative.

Each AI use case deployed on top of a mature governance platform inherits the full investment in that platform at zero marginal cost. The policy engine that governs one deployment pipeline governs the next one automatically. The audit trail infrastructure that produces evidence for one compliance framework extends to the next framework without rebuilding. The service registry that knows one service's ownership, dependencies, and SLOs knows the next one the moment it is onboarded.

This is the competitive dynamic that early movers in platform engineering will realize — not as a theoretical future state, but as an observable operational reality within the planning horizon of any current technology investment. The engineering organization that has built machine-readable governance infrastructure in 2026 will deploy its tenth agentic use case in 2028 at a fraction of the cost and risk of a competitor attempting to deploy its first.

It is worth being explicit about what the other side of this looks like. The regulated institution that defers this investment through 2027 and 2028 will not simply be slower — it will be structurally unable to operate at the pace its AI-enabled competitors set. Every AI use case will require a manual governance review that its competitors complete automatically. Every audit will consume engineering capacity that its competitors redirect to product delivery. Every compliance incident will trigger a remediation process that its competitors prevent by design. The gap does not close on its own. It widens, because the organizations that invested early are compounding their advantage while the laggards are still building the foundation. By 2028, the cost of catching up will be materially higher than the cost of starting today — not because the technology will be more expensive, but because the organizational transformation required will be more urgent, more disruptive, and less forgiving of the shortcuts that are still available now.

Standard automation does not disappear in the AI era. It becomes the foundation that makes the AI era possible. The pipeline is not legacy — it is the prerequisite. The change management process is not bureaucracy — it is the control surface that makes autonomous systems trustworthy.

Platform first. Then AI. In that order. Always.

---

*Brian Pelow is an engineering leader specializing in platform engineering, agentic systems, and regulated industry transformation. This thesis reflects his personal views developed through work in financial services and manufacturing. All referenced portfolio work is available at github.com/brianpelow.*