# Large Feature Circle

*A reusable transmutation circle for features that span multiple days or multiple stakeholders.*

Derived from **Transmutation 001 — Large Feature Workflow ≠ Small Feature Workflow**.

---

## Use this when

* The feature will take more than a day or two.
* Design, Backend, QA, Product, or Analytics are involved.
* There are multiple implementation phases or dependencies.

---

## Phase 0

Freeze prerequisites as much as possible before writing code.

* Read the entire design, not just the happy path.
* List ambiguous interactions and get clarifications early.
* Review backend contracts if they're available.
* Identify analytics events before implementation.

Some things will still change. The goal is to reduce avoidable uncertainty before coding.

---

## Phase 1

Break the feature into implementation units.

Each unit should be something that can be completed, tested, and reviewed independently.

Examples

* Static UI for one section.
* Analytics integration.
* CMS integration.
* Backend integration.
* Responsive fixes.
* Self QA pass.

Avoid keeping implementation state in memory.

---

## Phase 2

Externalize working memory.

Track only three states.

| State       | Meaning                                  |
| ----------- | ---------------------------------------- |
| **Done**    | Implemented and verified.                |
| **Waiting** | Blocked by clarification or dependency.  |
| **Next**    | The next implementation unit to work on. |

If it isn't written down, assume it will be forgotten after a context switch.

---

## Phase 3

Self QA before QA.

Check every implementation unit before moving to the next one.

* Desktop.
* Mobile.
* Empty states.
* Loading states.
* Error states.
* Long text and overflow.
* Analytics events.
* Responsive layout.

QA should find new bugs, not predictable ones.
