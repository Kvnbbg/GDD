# NUMERIA ONLINE — GDD Addendum v1.1

**Extends:** `NUMERIA Online — Game Design Document.pdf` (v1.0, September 2026)
**Status:** Pre-production / Concept
**Scope:** Two chapters absent from v1.0 — the terminal tier, and the commercial model.

> **This document does not replace v1.0.** It adds Chapters 14 and 15 and appends to the
> registers in §6.2, §8.2, §10.1 and §13. Where the two disagree, v1.0 wins and this
> document is wrong — say so rather than forking the design. A design with two sources of
> truth has none.

---

## Why these two chapters

v1.0 is complete on its own terms: it delivers the progression ladder (§6), the core loop
(§3), the gating rationale (§8), and a serious burnout risk assessment (§10). Two gaps
remain, and they are the two that block the move from concept to production:

1. **The ladder has no terminal rung.** Tier 9 (The Hilbert Expanse, Mythic) is the top of
   the power curve. A player who reaches it has nowhere to go but grind — the failure mode
   §10 spends ten pages preventing, arriving through the back door at endgame.
2. **§11 states a monetization *constraint*, not a *model*.** "Cosmetics only, no
   pay-to-win" is a boundary. It is not a business. A GDD that cannot be costed cannot be
   funded.

---

# 14. Tier Ω — The Zero Absolute

## 14.1 Design principle: the last tier adds a verb, not a number

Every tier from 0 to 9 answers the same question — *what is the value?* — and rewards the
player for answering it faster and more accurately. Tier Ω asks a different question:

> **Does a value exist at all?**

This is not a difficulty increase. It is a category change, and it is the reason Tier Ω can
be terminal without being a grind: there is no "Tier 11" because there is nothing left to
add once the player has learned that *some questions have no answer, and recognising that is
the skill.*

Tier Ω grants **no power increase.** Its rewards are social and cognitive (§14.6, §14.7).
This is deliberate — it decouples endgame from the power treadmill that §10.1 flags as
"Repetitive grind burnout."

## 14.2 The Discordant's final form — The Zero Divisor

v1.0 §2.3 establishes The Discordant as entities of *corrupted* mathematics. The Zero
Divisor corrupts nothing. It is worse: it **empties denominators**.

Where the Continuity Leviathan (Tier 8) bends how quantities change, the Zero Divisor
removes the thing you were dividing by. The equation stays perfectly well-formed. It simply
stops having a result.

In fiction: the Zero Divisor does not attack Numeria's equations. It attacks the *assumption*
that every equation resolves — the assumption on which every Dominion's aether depends.

## 14.3 The core inversion — refusal as a combat verb

In Tiers 0–9, casting a spell with a wrong answer is a weak hit. **In Tier Ω, casting a
spell whose denominator is null does not miss. It generates Infinity.**

Generated Infinity is not a failure state for the player alone:

- it deals uncapped resonance damage to **the player's own raid**, and
- it corrupts the arena tile permanently for the remainder of the encounter.

The correct play is therefore, sometimes, **not to cast.** Tier Ω introduces a dedicated
input:

| Verb | Input | Correct when | Reward |
| --- | --- | --- | --- |
| **RESOLVE** | numeric entry | a finite value exists | standard damage + combo |
| **INVOKE Ψ** | Ψ key + numeric entry | no value at the point, but a limit exists | high damage, no combo break |
| **REFUSE** | dedicated key | neither value nor limit exists | full damage, combo *preserved* |

**Refusing correctly is a maximum-value play, not a defensive one.** This matters: if refusal
merely avoided a penalty, players would treat it as failure. It is the strongest verb in the
game, and it is the only one that cannot be brute-forced by speed.

The pedagogy is real and rarely taught: *knowing that an operation has no result is
mathematical competence, not the absence of it.*

## 14.4 The Hidden-Null Value — the signature mechanic

The Zero Divisor never shows a zero. It shows a denominator that is **visibly non-zero** and
lets the player's own certainty destroy their raid.

Every Dominion has a **resonance unit** (v1.0 §2.1 establishes each Dominion's aether as
having its own frequency; this gives that frequency a unit). A denominator is displayed in
whatever unit the boss chooses — but the spell resolves in the *Dominion's* unit. The player
must judge the value **after conversion**, not as displayed.

Two ways a healthy-looking denominator becomes lethal:

| Trap | What the player sees | What resolves | Real skill taught |
| --- | --- | --- | --- |
| **Collapse** | `0.0004 psi` — clearly non-zero | underflows to null in the Dominion's unit | magnitude after unit conversion |
| **Overflow** | a large numerator, an ordinary denominator | the *ratio* exceeds representable range → Infinity | ratios, not operands, determine overflow |

> **Design note — this trap is not invented.** It is observed behaviour in the reference
> converter (`github.com/Kvnbbg/Division-by-Zero`). In that codebase, `ratio()` correctly
> refused a null denominator for months while `convert()` silently returned `Infinity` for
> inputs where *neither operand was extreme* — the target unit's SI factor alone was enough
> to overflow the result. A guard that reads only the input cannot catch it; only a guard on
> the **result** can.
>
> The mechanic therefore teaches a genuine engineering failure, not a puzzle-box
> contrivance. It is also why the Grimoire (§14.7) checks results rather than answers.

**Fairness constraint (non-negotiable):** the Dominion's resonance unit is *always* visible
in the HUD, and Ψ passively displays the order of magnitude after conversion. The player is
never asked to guess a hidden number — only to *look at the right one*. A hidden-null the
player could not have seen is a bug, not a mechanic.

## 14.5 Ψ — The Limit

Ψ is the Tier Ω companion, unlocked on entry. Ψ does not answer. Ψ **classifies**.

When a denominator approaches zero without reaching it, Ψ reveals whether the expression
tends to a limit. The player must then decide which of the three verbs applies — and *the
classification happens before the arithmetic.*

```
        DENOMINATOR APPROACHES ZERO
                    │
                    ▼
             Ψ CLASSIFIES
                    │
     ┌──────────────┼──────────────┐
     ▼              ▼              ▼
  FINITE      LIMIT EXISTS    PURE INFINITY
     │              │              │
     ▼              ▼              ▼
  RESOLVE       INVOKE Ψ        REFUSE
  (compute)   (state limit)   (do not cast)
```

This is the cognitive jump of the endgame, and it inverts the whole game's habit: for nine
tiers the player has been rewarded for computing *immediately*. Tier Ω punishes it. The
first thing a Tier Ω player must learn is to **stop**.

Ψ is also the accessibility valve. In Assist Mode (v1.0 §10.3), Ψ narrows the classification
to two options instead of three, and extends the pre-cast window — full Tier Ω progression
remains achievable, consistent with v1.0's rule that no power is locked behind speed.

## 14.6 The Pure Infinity Solution → Knowledge Sharing

Defeating the Zero Divisor — which is to say, correctly refusing it — yields **no gear.**

It unlocks **Knowledge Sharing**, and this is the intended terminal state of the game:

- A Tier Ω player may **co-sign** a lower-tier player's Mastery Proof (v1.0 §6.3).
- A co-signed Proof grants the mentee an additional attempt and a slightly lowered
  consistency threshold — never a skipped Proof. **Mastery is never transferred, only
  vouched for.**
- The mentor stakes Resonance on it. If the mentee later fails that discipline in a Grimoire
  regression check (§14.7), the mentor loses the staked Resonance. The mentee loses nothing.

The asymmetry is the whole design: **the person with power carries the risk.** This directly
answers two risks in v1.0 §10.1 — "Social toxicity / exclusion" and "Skill-ceiling
frustration" — by making strong players *structurally invested* in weak players succeeding,
rather than merely incentivised by a mentor bonus that they can farm and abandon.

It also gives the endgame a purpose that cannot be exhausted: the supply of people who need
teaching is not a finite resource that gets cleared like a raid tier.

**Guardrail:** co-signing is capped per season and is strictly opt-in on both sides. See the
risk entries in §14.9 — an obligation to mentor is a job, and jobs cause churn.

## 14.7 The Grimoire of Resolutions

The Grimoire is the player's persistent record of every **correct refusal**, every **limit
found**, and every **hidden-null caught**. It is written to only on success.

**The Grimoire is a regression test suite for the character.**

That is the literal design, not a metaphor:

| Test suite | Grimoire |
| --- | --- |
| a passing test records a behaviour worth preserving | a page records a resolution the player got right |
| the suite re-runs on a schedule | entries resurface via spaced retrieval (extends v1.0 §6.4) |
| a red test is information, not punishment | a failed entry marks the page "to review" — no loss |
| a fix is verified by the test going green | Ψ offers targeted remediation; the page re-greens |

Extending v1.0 §6.4: spaced retrieval already resurfaces mastered operations at low frequency
to prevent skill decay. The Grimoire makes that visible and gives it a fiction — the player
sees *which* competence is fading and can act on it, instead of being quietly re-drilled.

**The three rules that keep it from becoming anxiety:**

1. **A regression never removes gear, tier, or Resonance.** It marks a page. Nothing else.
   (v1.0 §10.1, "Math anxiety", severity High — a Grimoire that could demote a player would
   create precisely the fear the game is built to avoid.)
2. **The Grimoire is private by default.** Sharing a page is a deliberate act (§14.6).
3. **Remediation is offered, never forced,** and can be dismissed permanently per discipline.

**Shared pages.** A mentor may lend a Grimoire page: the mentee sees the *reasoning* recorded
for that resolution, not the answer. This is the mechanical form of the game's thesis — power
transfers as understanding or not at all.

## 14.8 Register additions

**To the Tier Table (v1.0 §6.2):**

| Tier | Discipline | Example combat challenge | Example puzzle / boss mechanic | Gear rarity unlocked | Dominion unlocked |
| --- | --- | --- | --- | --- | --- |
| **Ω** | Undefined Forms & Limits | Classify before computing; refuse when no value exists | Hidden-null detection; limit invocation | **None — social & cognitive rewards only** | The Zero Absolute |

**To the Zone Table (v1.0 §8.2):**

| Dominion | Math tier | World boss | Gameplay demand | Why lower tiers cannot enter |
| --- | --- | --- | --- | --- |
| **The Zero Absolute** | Ω | **The Zero Divisor** | Classification before computation; magnitude after unit conversion; correct refusal | The zone has no defined aether — it is the *absence* of resonance. A mind that assumes every expression resolves perceives the zone as fully solid ground and walks into a null. Only a mind that can hold "this has no value" as a *state* rather than an error can see the terrain at all. |

The gating rationale of v1.0 §8.3 — fiction and mechanics agreeing — holds exactly, and
completes: every prior Dominion required *acquiring* a discipline. The last one requires
*relinquishing an assumption.* That is why it is last, and why it cannot be reached by
grinding Tier 9.

**To Open Questions (v1.0 §13):**

6. Does the REFUSE verb read as *strong* in playtest, or as *giving up*? If the latter, the
   entire tier fails. This is the single highest-risk assumption in this addendum and must be
   prototyped before any Tier Ω content is authored.
7. What is the correct penalty for an *unjustified* refusal? Too low and refusal becomes the
   dominant default (see §14.9); too high and it reintroduces the anxiety §10 removes.
8. Is the mentor Resonance stake perceived as fair, or as punishment for helping?
9. Does Ψ's classification aid remove the challenge rather than scaffold it?

## 14.9 Risk register additions

Appends to v1.0 §10.1. Tier Ω introduces risks the earlier tiers do not have, because it is
the first tier where *inaction* is a play.

| Risk | Description | Severity | Mitigation |
| --- | --- | --- | --- |
| **Refusal-default degeneracy** | Refusing is safe and preserves combo, so players refuse everything and stop computing — the tier collapses into a coin-flip | **High** | Unjustified refusal costs combo and yields no damage; encounter composition is majority-resolvable; Ψ classification is legible enough that guessing is strictly worse than reading |
| **"Gotcha" perception of hidden-nulls** | Players feel tricked by a denominator that looked fine, read the mechanic as unfair, and disengage | **High** | Resonance unit always in HUD; Ψ shows post-conversion magnitude passively; first three hidden-nulls per player are explicitly telegraphed; never a value the player could not have inspected |
| **Mentorship as unpaid labour** | Co-signing becomes an expectation; strong players feel obliged, then quit | **Medium** | Hard seasonal cap; opt-in both sides; mentor rewards are cosmetic and social, never power — so declining costs nothing competitive |
| **Grimoire as surveillance / debt** | The record of fading competences reads as a backlog of failures | **Medium** | Success-only writes; regressions never remove anything; remediation dismissible per discipline; framed as "pages to revisit", never as decay |
| **Stake exploitation** | Mentors co-sign only near-certain mentees, so the players who most need help get none | **Medium** | Match on need, not on projected success; cap co-signs per mentee tier; stake scales *down* with mentee tier distance |
| **Terminal-tier emptiness** | Ω grants no power; players who measure progress in numbers perceive the endgame as "nothing to do" | **Medium** | Communicate the shift explicitly at Tier 9→Ω; make Grimoire and mentorship progression *visible* and cosmetically expressive; seasonal Ω encounters rotate mechanics, not stats |

---

# 15. Finance & Marketing

## 15.1 Why §11 is not yet a model

v1.0 §11 is correct and insufficient. It sets a boundary — *no power for sale* — and closes
with the sentence that makes the boundary non-negotiable: *"the entire game collapses if
power can be bought."*

That is true, and it has a consequence §11 does not draw: **monetization cannot be the
adjustment variable.** In most F2P MMOs, when revenue misses, the lever is a power-adjacent
convenience. Here that lever does not exist — pulling it destroys the product. So the model
has to work on cosmetics and licensing *alone*, and that must be proven on paper before
production, not discovered after launch.

## 15.2 What the constraint buys

The constraint is not only a cost. It produces two structural advantages that should be
priced into the plan:

- **Unusually low paid acquisition need.** The game has a story that non-players repeat
  ("my kid learned fractions from a raid boss"). Word-of-mouth is not a nice-to-have here;
  it is the primary channel, and the design earns it.
- **Institutional legitimacy.** A game that *measures demonstrated mastery* (§6.3 Mastery
  Proofs) has a defensible B2B value that a cosmetic MMO does not. This is the single
  largest revenue asymmetry available.

## 15.3 Revenue streams

| Stream | Mechanism | Hard constraint | Principal risk |
| --- | --- | --- | --- |
| **Cosmetics** | Direct-purchase skins, mounts, titles, emotes | Never power; never problem-solving aids | Low ARPU if the art direction under-delivers — cosmetics are the *whole* consumer business, so art is a revenue function, not a polish budget |
| **Seasonal pass** | Cosmetic track + Grimoire/Ω expressive rewards | No mechanical advantage; must not create daily-login obligation | Directly antagonises §10.7 (rest and caps) if the track rewards streaks |
| **Capped convenience** | Extra practice tokens | Cannot bypass a Mastery Proof; hard daily ceiling | Perception drift toward pay-to-progress; needs a published, stable cap |
| **Institutional licence** | Per-seat licence to schools / training bodies, with cohort dashboards | **The curriculum must never dictate combat design** | Contaminating the game with worksheet logic — the exact failure §10 exists to prevent |
| **IP & merch** | Long-tail, post-traction | — | Distraction before product-market fit |

**The institutional stream deserves an explicit firewall.** It is the most lucrative and the
most dangerous: an education customer will ask for curriculum alignment, per-pupil reporting,
and assessment-shaped content. Each request, granted, moves the game toward the worksheet.
Recommendation: institutional licensing consumes the *existing* Mastery Proof data and
adds **dashboards only** — never content requirements. If that is not commercially
sufficient, the correct answer is to drop the stream, not to bend the design.

## 15.4 Unit economics — the frame, not the numbers

**No figures are asserted here, because none have been measured.** Inventing plausible
benchmarks is how a plan becomes unfalsifiable. What follows is the set of quantities that
must be established, and the thresholds that determine viability.

Viability condition:

```
LTV  =  ARPPU × payer-conversion × retention-adjusted lifetime
        must exceed
CAC  =  blended paid + organic acquisition cost
```

with the specific sensitivities this design creates:

| Quantity | Why it behaves unusually here | Must be established by |
| --- | --- | --- |
| **Payer conversion** | No power purchase → conversion is driven purely by cosmetic desirability and identity expression | Cosmetic-desirability testing during closed beta |
| **Retention (D30/D90)** | Should be *higher* than genre norm: skill investment is non-transferable and the Grimoire creates a personal record players do not abandon lightly | Cohort measurement across at least one full Grimoire regression cycle |
| **Lifetime** | Extended by §14.6 mentorship — social obligation retains far longer than content cadence | Ω-cohort tracking; do not model before Ω exists |
| **CAC** | Expected below genre norm (§15.2), but *unproven*; the design's word-of-mouth thesis is an assumption | Paid/organic split measurement in soft launch |
| **Content cost per Dominion** | Modular content packs (v1.0 §12) — but each pack needs an *authored, validated problem set*, a cost line absent from a normal MMO zone | Pilot: build one Dominion end-to-end and measure |

**The cost line most likely to be underestimated** is problem-set authoring and validation.
A Dominion is art + boss + gear **+ a pedagogically sound, difficulty-calibrated,
anti-cheat-randomisable problem bank.** That last item has no analogue in conventional MMO
production budgets and should be costed explicitly before any content-cadence promise is
made publicly.

## 15.5 Positioning

The positioning decision determines the outcome more than any other marketing choice, and
there are two failure modes flanking one narrow correct answer:

| Positioning | Outcome |
| --- | --- |
| "Educational game" | Commercially fatal with core players. Ends up in the school-software category, competing on procurement, not on fun |
| "An MMO" (unqualified) | Competes head-on with WoW / FFXIV on content volume and production value. Unwinnable |
| **"A real MMO that happens to make you sharper"** | Sold on the combat fantasy; the learning is the *twist*, discovered and then evangelised by players |

The third is the only viable one, and it imposes marketing discipline: **the learning outcome
is never the headline.** It is the thing players find out and tell other people about. v1.0
§1.5 already commits to this internally ("the moment it feels like homework, the design has
failed") — §15.5 extends the same rule to every external communication.

## 15.6 Channels, and the one this design is built for

**Mental arithmetic under pressure is intrinsically spectatorial.** A viewer can play along
in their head, in real time, with no game knowledge — an advantage almost no MMO has.
Live-streaming and short-form video are therefore not one channel among several; they are the
channel the product is shaped for.

| Channel | Role | Fit |
| --- | --- | --- |
| **Creator / live-streaming** | Primary | The audience competes silently with the streamer. Uniquely high |
| **Short-form clips** | Primary discovery | See "the proof moment" below |
| **Community / guild seeding** | Retention, not acquisition | Mentorship (§14.6) makes guilds structurally sticky |
| **Institutional (B2B)** | Revenue, minimal acquisition value | Keep firewalled from consumer brand (§15.3) |
| **Paid UA** | Backstop only | Expensive against MMO incumbents; use to *test* messaging, not to scale |

**The proof moment.** The single most valuable marketing asset this design can produce is a
twenty-second clip in which a player, under a visible countdown, **refuses to cast** — and
saves the raid. It is counter-intuitive, needs no explanation, showcases a mechanic no
competitor has, and communicates the entire thesis without ever using the word "learning."
Prototype it early (see §14.8 Q6 — the same prototype answers both the design and the
marketing question).

## 15.7 Marketing risk register

| Risk | Description | Severity | Mitigation |
| --- | --- | --- | --- |
| **Edutainment classification** | Press and stores file the game under education; core players never see it | **High** | Combat-first assets only; store category and trailer must lead with the boss fight; no learning claims above the fold |
| **Audience collision** | Messaging that converts parents repels the core players who sustain the game | **High** | Separate the institutional/parent funnel entirely from consumer brand; different creative, different surfaces |
| **Engagement metrics vs. anti-burnout design** | Growth targets reward time-in-game; §10.7 caps it deliberately | **High** | See §15.8 — this is a governance problem, not a messaging one |
| **Over-promising the learning outcome** | Measurable-gain claims invite scrutiny the game cannot yet satisfy, and regulatory exposure in education markets | **Medium** | Claim nothing not established by cohort data; never advertise learning outcomes to consumers at all |
| **Skill-integrity perception break** | A single mis-priced convenience item reads as pay-to-win and permanently damages the core promise | **High** | Published, versioned monetization charter; any change reviewed under §15.8 |

## 15.8 The governance blind spot

**This is the organisational gap in v1.0, and it is not a documentation gap — it is an
unassigned decision.**

v1.0 distributes the pieces and never joins them:

- §10.6 gives live-ops the *monitoring* of burnout signals.
- §11 states the monetization *constraint*.
- §10.7 mandates daily caps and rested bonuses that **deliberately reduce time-in-game.**

Nobody owns the conflict. And the conflict is structural, not hypothetical: a commercial
function is measured on engagement and revenue; this design is built to *cap* engagement.
Those two pressures meet at the seasonal-pass track, the convenience cap, and the daily
objective cadence — three of the highest-revenue surfaces in the game.

Left unassigned, it resolves the way it always resolves: quietly, one small change at a time,
in the direction of revenue, until the anti-burnout design exists only in the document.

**Proposed resolution.** Give the *existing* body teeth rather than inventing a new one: the
"Mastery & Motivation" seasonal review already named in v1.0 §10.6 becomes the **decision
owner**, with a standing veto over any change touching caps, pass structure, or convenience
pricing — and a published charter so the veto is auditable rather than personal.

## 15.9 Stakeholders

Named so that the veto in §15.8 has someone to belong to. Roles, not individuals — v1.0
credits "Game Design Team" and no other function, which is itself the blind spot in miniature.

| Stakeholder | Owns | Decides | Consulted on | Must not decide |
| --- | --- | --- | --- | --- |
| **Game Design** | Core loop, tiers, gating, Tier Ω | Mechanics, difficulty bands, Mastery Proof thresholds | Monetization surfaces | Pricing |
| **Learning Design** | Problem banks, tier validity, Grimoire remediation | Pedagogical soundness; veto on curriculum contamination (§15.3) | Content cadence, institutional scope | Content volume commitments |
| **Live-ops** | Burnout monitoring (§10.6), seasonal tuning | Hotfix tuning within published bands | Pass structure | Cap changes (→ M&M review) |
| **Commercial** | Revenue streams, pricing, institutional licensing | Price points, cosmetic catalogue | Cap and cadence changes | Anything touching power, caps, or Proof thresholds |
| **Marketing** | Positioning (§15.5), channels, the proof moment | Creative, channel mix | Feature reveal timing | Learning-outcome claims (→ Learning Design) |
| **Accessibility** | Assist Mode as first-class path (§10.3), Ψ scaffolding | Veto on any change that locks progression behind speed | All tier and boss design | — |
| **Community** | Mentorship health (§14.6), toxicity signals | Reporting and conduct enforcement | Mentor incentives and caps | Mentor reward *power* |
| **M&M Review** | The §15.8 conflict | **Veto** on caps, pass structure, convenience pricing | — | Day-to-day tuning |

---

## Changelog

| Version | Date | Change |
| --- | --- | --- |
| 1.0 | Sept 2026 | Initial GDD (PDF) — §1–13 |
| 1.1 | Sept 2026 | Adds §14 (Tier Ω — The Zero Absolute) and §15 (Finance & Marketing); appends to §6.2, §8.2, §10.1, §13 |
