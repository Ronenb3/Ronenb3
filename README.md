# I build systems that detect the gap between what is believed and what is true.

Every institution in the world — governments, corporations, media companies — has infrastructure for modeling what people believe. None of that infrastructure runs for the individual. I'm trying to change that.

I'm 19. I'm a freshman. I've been building this architecture since before I had words for what it was.

---

## The Work

Three tools are public. They're part of a larger system — 16 interconnected components built around one idea.

**[doubt](https://github.com/Ronenb3/doubt)** — Claim verification engine with epistemic self-awareness. Give it any assertion. It searches 118 data sources, runs Bayesian inference across the evidence, attacks its own conclusions with adversarial counter-hypotheses, and refuses to return a verdict until the investigation has been earned. Zero API keys required.

```bash
$ node bin/doubt.js investigate "Tesla full self-driving is safe for public roads"
# → 864 evidence items gathered. 737 filtered. 110 survived.
# → Confidence: 54.5% | Attack survival: 15.4%
# → INSUFFICIENT — adversarial gate blocked.
```

**[MindMirror](https://github.com/Ronenb3/MindMirror)** — Automated psychoanalysis of your own writing. Ingests a personal journal or note vault, extracts a belief graph using dual-layer analysis (explicit patterns + implicit signal scoring), tracks how beliefs shift over time, detects the ideas the mind keeps returning to, and surfaces the questions that have no answer anywhere in the writing. Runs locally. No API calls.

```
DOMAIN SHIFT: self-capability → epistemic/certainty
CERTAINTY COLLAPSE: -94% net certainty | negation density +424%
RETURNING IDEA (4mo gap, sim: 0.962): "My life is a system of systems." → "my life is a system."
BLIND SPOT: "what do i even really want out of life." — no answer anywhere in 80 documents
```

**[Epistemic-Cascade](https://github.com/Ronenb3/Epistemic-Cascade)** — Maps how false beliefs propagate through dependent claim networks. Identifies the keystone claim — the one where falsification collapses the entire structure. Every argument has a load-bearing belief. This finds it.

```bash
$ node src/cli.js "Social media causes depression in teenagers"
# → 9 claims extracted, dependency graph built
# → KEYSTONE: "confounding variables adequately controlled" (collapse impact: 0.71)
# → Falsify this one claim → root confidence drops from 50.4% → 18.2%
```

---

## The Method

**Epistemic surgery.** Not surveillance. Surgery.

1. Find the keystone — one load-bearing claim holds the structure
2. Verify the keystone — don't spread across all claims
3. Score fragility (0–1) — how many independent sources need to fail before confidence collapses?
4. Minimum intervention — falsify the one that makes 19 others moot

This applies to OSINT, personal writing, academic arguments, and strategic decisions equally.

---

## The Deeper Question

Why does any of this exist?

Most fact-checking tools treat evidence as additive: more evidence = more confidence. That's fundamentally wrong. doubt blocks conclusions until they survive structured attempts to destroy them. MindMirror doesn't ask what you think — it asks what your writing reveals that you don't consciously know you think. Epistemic-Cascade doesn't refute the whole argument — it finds the one claim that makes everything else fall.

The same question runs through all of it: *what separates what is believed from what is true, and how do you measure the gap precisely?*

---

## Stack

Python · Node.js (ESM) · LanceDB · sentence-transformers · spaCy · Bayesian inference · NetworkX

Everything runs locally. Local-first is a values statement built into the infrastructure.

---

## On AI Use

I use Claude as a coding collaborator. The architecture, the ideas, the intellectual direction — mine. The implementation — written with AI assistance under my direction.

I think this is worth being direct about. Every engineer I respect uses AI for implementation now. The question that actually matters is whether the person directing it understands what they're building and why. I do. I can explain every design decision in these systems, every tradeoff, every place where the approach is novel.

The other thing worth saying: building tools that analyze AI outputs, verify AI claims, and detect epistemic drift in AI-generated content — while using AI to build them — is not a contradiction. It's the point.

---

*Building in public. These three tools are the beginning.*
