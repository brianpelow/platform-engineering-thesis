# The Arithmetic of Shared Infrastructure

**Brian Pelow &middot; July 2026**

*A companion to [THESIS.md](./THESIS.md). The thesis argues that platform engineering is the prerequisite for AI in regulated industries. This document contains the arithmetic that changed my mind about how to argue it.*

---

## The number I did not expect

I built a tool to assess regulatory impact. It takes a piece of supervisory guidance, determines which systems it binds, diffs required controls against declared controls, and produces a sequenced remediation plan with effort estimates.

I did not build it to prove the platform thesis. I built it because the tracker I run tells me a regulation changed, and the obvious next question is *so what, and what do we have to build*.

The first complete run against a seven-system reference inventory returned **213 engineer-weeks**.

That number was wrong, and the reason it was wrong is the thesis.

---

## What the tool was doing

The assessment identified that four systems needed a decision record layer. It estimated six weeks for that control. It then charged six weeks to each of the four systems.

Twenty-four engineer-weeks to build the same thing four times.

No competent engineering organization would do this. You build the decision record layer once, as platform infrastructure, and systems onboard onto it. The first system carries the build. Every system after that carries integration.

I corrected the model: controls satisfied by shared infrastructure are priced once, with a one-week onboarding cost for each subsequent system. The criticality ordering determines which system funds the build.

Same document. Same seven systems. Same taxonomy. Same obligations.

**213 engineer-weeks became 122.**

---

## Why this is the thesis rather than a rounding error

A forty-three percent reduction from a single modeling correction is not a tuning artifact. It is the difference between two mental models of how governance work gets done, expressed as a number.

The per-system model says: each system must satisfy each obligation, so each system must build each control.

The platform model says: obligations bind systems, but controls live in infrastructure. A system does not build a decision record layer. It *uses* one.

Both models produce a defensible-looking spreadsheet. Only one of them describes how the work is actually done. And the gap between them is not marginal &mdash; it is nearly half the estimate.

---

## The strategic claim this unlocks

I have watched institutions conclude that comprehensive AI governance is unaffordable. The reasoning is always some version of: we have N systems, each needs M controls, the math does not work, so we will do the minimum and accept the risk.

**That conclusion is frequently an arithmetic error rather than a budget reality.**

If you price governance per system, the cost scales linearly with your AI footprint, and every new model makes the problem worse. Governance looks like a tax that grows without bound. Rational executives decline to pay it.

If you price governance as platform infrastructure, the cost is front-loaded and then flattens. The fourth system costs a fraction of the first. The tenth is nearly free. Governance becomes a fixed investment that makes AI deployment *cheaper* at the margin rather than more expensive.

Same obligations. Same regulator. Opposite strategic conclusion.

This is why I argue platform first, and it is a better argument than the one I was making before, because it is quantitative rather than architectural. I was previously arguing that platforms are the right structure. I am now arguing that the absence of a platform makes governance look unaffordable when it is not &mdash; and that the institutions declining to invest are frequently responding to a number their own modeling produced incorrectly.

---

## The distribution matters as much as the total

Here is the per-system breakdown after the correction, against the same guidance:

| System | Criticality | Gaps | Engineer-weeks |
|--------|-------------|------|----------------|
| Credit decisioning API | Consequential | 13 | 44 |
| Fraud detection service | Consequential | 13 | 30 |
| Collections prioritizer | Supporting | 15 | 32 |
| Vendor KYC integration | Consequential | 11 | 16 |

The credit decisioning system carries forty-four weeks. The vendor integration carries sixteen &mdash; despite having a comparable number of gaps.

The difference is that the credit system funded the shared build. Everything downstream inherits it.

That spread is the platform argument made visible. Not asserted in prose, not drawn on a slide. It is what the tool reports when you model the work the way the work is actually done.

It also produces a sequencing recommendation that falls out of the arithmetic rather than out of judgment: **build the shared controls against your highest-consequence system first.** Not because that system deserves priority attention, though it does, but because that is where the platform investment lands most efficiently. Every subsequent system draws down a cost that has already been paid.

---

## What this does not prove

The estimates are taxonomy defaults, not estimates for a specific codebase. Six weeks for a decision record layer is a reasonable planning figure and a poor commitment. A real estimate requires knowing the systems.

The reference inventory is generic. Seven systems with declared controls, constructed to exercise the tool. A real institution has more systems, messier declarations, and disagreements about which controls actually exist.

The onboarding figure &mdash; one week per subsequent system &mdash; is the number I am least confident in. Onboarding a well-structured service onto a decision record layer might take days. Onboarding a system with no clean inference boundary could take a month.

None of that changes the shape of the result. Whether shared pricing saves forty-three percent or twenty-five percent or sixty, per-system pricing overstates the cost of governance, and it overstates it in the direction that causes institutions to decline the investment.

---

## The uncomfortable part

I built the tool. I wrote the thesis it happens to support. The first version of the tool contained exactly the error the thesis warns against.

I want to be precise about what that means, because it cuts both ways.

It is mild evidence for the thesis: if someone who has spent a year arguing that shared infrastructure is the unlock still instinctively priced controls per system, the per-system mental model is more deeply held than I assumed. It is the default. It requires active correction even in someone actively arguing against it.

It is also a caution about the tool. Deterministic output is only as good as the model behind it, and the model was wrong for the first several runs. It produced a confident, well-formatted, entirely credible 213-week estimate. Nothing in the output signalled that the number was inflated. I found it by reading the per-system breakdown and noticing that four systems were each building the same thing.

The correction is documented as [ADR 0003](https://github.com/brianpelow/regulatory-change-impact-agent/blob/main/docs/adr/0003-shared-controls-priced-once.md) in that repository, along with two other modeling errors the same exercise surfaced.

That is the honest version of this document: the arithmetic supports the thesis, and I only have the arithmetic because I made the mistake the thesis exists to prevent.

---

## What to do with this

If you are building a governance investment case, price the controls, not the systems. Identify which controls are platform infrastructure, cost them once, and add a realistic onboarding figure per consuming system. Then compare that total to whatever your current per-system estimate says.

If the two numbers differ by anything like the margin above, the strategic conversation you are about to have is a different conversation than the one you were preparing for.

---

*The tool is at [regulatory-change-impact-agent](https://github.com/brianpelow/regulatory-change-impact-agent). Scope detection, obligation extraction, impact mapping, gap analysis, and sequencing are deterministic &mdash; the same document and inventory always produce the same assessment. The reference inventory and sample documents are generic and illustrative; the samples are synthetic composites, not reproductions of agency text.*

*Brian Pelow is an engineering leader specializing in platform engineering, agentic systems, and regulated industry transformation. This document reflects his personal views. All referenced portfolio work is available at github.com/brianpelow.*