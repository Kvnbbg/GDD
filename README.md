# GDD — NUMERIA ONLINE

Game Design Document for **NUMERIA ONLINE**, an MMORPG where mental arithmetic is the
combat verb: you solve fast expressions under pressure to strike world bosses, and you prove
mastery of a mathematical discipline to unlock the epic gear and the zones beyond it.

> *Where calculus is the blade, and your mind is the weapon.*

## Documents

| Document | Version | Covers |
| --- | --- | --- |
| [`NUMERIA Online — Game Design Document.pdf`](./NUMERIA%20Online%20—%20Game%20Design%20Document.pdf) | 1.0 | §1–13 — high concept, lore, core loop, combat, tiers 0–9, gear, zone gating, MMO systems, burnout risk assessment, monetization summary, production notes |
| [`docs/NUMERIA-v1.1-addendum.md`](./docs/NUMERIA-v1.1-addendum.md) | 1.1 | §14 Tier Ω (The Zero Absolute) · §15 Finance & Marketing — plus additions to the tier, zone, risk and open-question registers |

**v1.0 is the source of truth.** The addendum extends it and never restates it. Where the
two disagree, v1.0 wins and the addendum is wrong.

## What v1.1 adds, and why

1. **A terminal tier that is not more power.** v1.0's ladder ends at Tier 9 (Mythic), which
   leaves the endgame with nowhere to go but grind — the exact failure its own §10 spends
   ten pages preventing. Tier Ω changes the verb instead of the number: some expressions
   have **no value**, and recognising that is the skill. Refusal becomes the strongest play
   in the game.
2. **A business model, not just a constraint.** v1.0 §11 says *no power for sale* — a
   boundary, not a business. §15 works out what has to be true for cosmetics and
   institutional licensing to carry the whole thing, names the cost line most likely to be
   underestimated (problem-set authoring), and refuses to invent benchmark figures nobody
   has measured.
3. **The unassigned decision.** §15.8 names the organisational gap: v1.0 gives live-ops the
   burnout *monitoring*, gives §11 the monetization *constraint*, and mandates caps that
   deliberately reduce time-in-game — but assigns nobody to arbitrate when revenue and
   anti-burnout pull against each other. Unassigned, that conflict resolves quietly toward
   revenue, one small change at a time.

## A note on format

v1.0 lives here as a **PDF**, which git cannot diff. There is no line-level history, no
review, no blame — a design change is indistinguishable from a re-export, and two people
editing it produce a conflict no tool can merge.

The addendum is Markdown for that reason. Converting v1.0 to Markdown would make the whole
document reviewable, and is the recommended next step — deliberately **not** done here,
because a hand-transcribed copy of a 14-page PDF is a second source of truth, and the fastest
way to make a design document lie is to have two of them.

## Related

The hidden-null mechanic in §14.4 is not invented. It is observed behaviour in
[`Kvnbbg/Division-by-Zero`](https://github.com/Kvnbbg/Division-by-Zero), where a converter
correctly refused a null denominator while silently returning `Infinity` for inputs in which
*neither operand was extreme* — the target unit's SI factor alone was enough to overflow the
result. The game teaches a real engineering trap.
