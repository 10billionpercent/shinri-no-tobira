# Transmutation 001

## Large Feature Workflow ≠ Small Feature Workflow

*Discovered September 28, 2026*

---

## Origin

**Project** Bond Directory

The first large frontend feature I worked on that spanned Design, Backend, Analytics, CMS, QA, SEO, and Product.

It was also the first feature that stayed in active development long enough for context switches, changing requirements, and multiple review rounds to become part of the implementation itself.

---

## Price Paid

* Multiple rounds of QA for issues that should have been caught during development.
* Repeated back-and-forth with Design and Product after implementation had already started.
* Expensive context switching after a multi-day break and parallel work on another feature.
* Rework caused by implementation details living in memory instead of an external system.

---

## Observation

I approached this feature exactly the way I approached smaller features.

The overall implementation plan existed, but each phase became "I'll remember what still needs to happen."

That workflow had worked well for smaller features.

It did not scale.

---

## Root Cause

The problem was not the implementation plan.

The problem was how I executed it.

I relied on working memory to keep track of implementation progress, pending design clarifications, backend assumptions, analytics requirements, edge cases, and self QA.

As the feature grew and more people became involved, working memory became the bottleneck.

Context switches made it worse. Returning after several days away from the feature meant reconstructing implementation state from memory instead of reading it from somewhere reliable.

---

## Truth Obtained

Large features need an execution layer between planning and coding.

A feature plan answers **what** gets built.

An execution layer answers **what is done, what is blocked, what changed, and what still needs verification**.

Those are different problems.

---

## Equivalent Exchange

### Before writing code

Freeze prerequisites as much as possible.

* Review the design completely instead of discovering questions during implementation.
* Clarify ambiguous interactions with Product early.
* Review backend contracts before integration whenever they're available.

Some requirements will still change. The goal is to reduce avoidable uncertainty before implementation begins.

### During implementation

Break each phase into implementation units instead of keeping progress in memory.

Track

* **Done** — completed and verified.
* **Waiting** — blocked by clarification or dependency.
* **Next** — the immediate implementation unit after the current one.

Implementation state should live outside my head.

### Before QA

Run structured self QA after completing each implementation unit instead of only at the end of the feature.

Fresh QA is much better at finding simple issues than an overloaded brain.

The goal is to give QA new bugs to discover, not the ones I could have found myself.

---

## Validation

The next large feature answers one question.

**Did this workflow reduce context-switch overhead and prevent the same class of QA bugs?**

If yes, this transmutation is complete.

If not, the workflow changes again.

---

> *Never trust working memory to manage a large feature. Externalize implementation state before it externalizes bugs.*
