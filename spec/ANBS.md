# Autonomy-Native Business Spec (ANBS)

Version: v0.1  
Status: Canonical Core Specification  
Canonical Source: This repository. The release tag v0.1 is the authoritative reference.  
Scope: Defines the minimum structural conditions under which a business can operate with zero humans in the runtime loop.

---

## 1. Fail Conditions

### Definition
A concept FAILS if it violates any condition below.  
Fail conditions are non-negotiable. No human arbitration is permitted in the runtime loop.

---

### F1 — Non-Terminating Interaction
FAIL if any user interaction can remain open-ended.

Permitted terminal states are strictly limited to:
- DELIVERED
- REFUNDED
- DENIED
- RETRY_EXHAUSTED

States such as “pending,” “manual review,” “follow-up required,” or “contact support” constitute failure.

---

### F2 — Human Arbitration Required
FAIL if correctness, eligibility, or resolution requires a human to:
- interpret intent
- approve output
- handle disputes
- negotiate outcomes
- grant exceptions

Any runtime human decision constitutes failure.

---

### F3 — Intent Not Parameterizable
FAIL if user intent cannot be converted into a bounded parameter set.

A valid schema must define:
- accepted inputs
- allowed ranges or categories
- default values
- rejection criteria

Open-ended clarification during execution constitutes failure.

---

### F4 — Output Is Inherently Debatable
FAIL if output acceptability is subjective, taste-based, or socially negotiated.

If users commonly dispute quality rather than factual error, the system fails.

---

### F5 — Quality Requires External Human Judgment
FAIL if output quality cannot be evaluated internally using deterministic rules, tests, or thresholds.

Human taste, opinion, or contextual judgment is not permitted.

---

### F6 — Support Load Scales With Usage
FAIL if support requirements scale proportionally with user growth.

Support must be preventable, rule-based, or eliminable by design.

---

### F7 — Edge Cases Require Custom Handling
FAIL if edge cases require bespoke workflows or special treatment.

Edge cases must resolve automatically via:
- DENIED
- REFUNDED
- AUTO-RETRY
- DEFAULT_OUTPUT

---

### F8 — Obligations Persist After Delivery
FAIL if delivery implies ongoing human responsibility, consulting, or relationship management.

---

### F9 — Compliance or Risk Requires Human Oversight
FAIL if legal, financial, or safety risks depend on human monitoring rather than automated enforcement.

---

### F10 — Unit Economics Depend on Human Time
FAIL if marginal cost includes recurring human labor.

Human time must not scale with transactions.

---

### F11 — Revenue Requires Human Trust-Building
FAIL if sales depend on calls, negotiation, or relationship-driven persuasion.

---

### F12 — Input Requires Human Coaching
FAIL if users must be taught how to provide acceptable input during execution.

---

## 2. Minimum Required Properties

### Definition
A concept PASSES only if all properties below are satisfied.

---

### P1 — Closed Execution Loop
The system MUST implement a closed execution loop:

INTENT → STRUCTURED INPUT → TRANSFORMATION → INTERNAL EVALUATION → TERMINAL STATE

---

### P2 — Deterministic Terminal States
Every execution MUST end in exactly one terminal state:
- DELIVERED
- REFUNDED
- DENIED
- RETRY_EXHAUSTED

---

### P3 — Parameterized Intent Schema
Intent MUST be representable as a finite parameter schema with defined bounds and defaults.

---

### P4 — Single Dominant Transformation
The system MUST perform exactly one primary transformation.

Multi-objective systems fail.

---

### P5 — Internal Quality Evaluation
Output acceptability MUST be determined internally via rules, tests, or thresholds.

---

### P6 — Zero Human Runtime Dependency
No human involvement is permitted during execution.

Humans may define constraints only outside runtime.

---

### P7 — Self-Filtering User Interaction
Unsuitable users MUST be filtered via constraints, rejection, or friction.

---

### P8 — Atomic Economic Transaction
Each execution MUST correspond to a discrete, self-contained economic event.

---

### P9 — Human-Free Scaling
Marginal execution cost MUST be independent of human labor.

---

### P10 — Rule-Expressible Operations
All operations MUST be expressible as:

IF (condition) → DO (action) → LOG (result)

---

### P11 — Explicit Failure Behavior
Failure modes MUST be defined and deterministic.

---

### P12 — Immutable Core Constraints
Constraints MUST apply uniformly and cannot be overridden at runtime.

---

### P13 — Auditability
Inputs, parameters, outcomes, and terminal states MUST be logged automatically.

---

### P14 — Replaceable Components
No component may be essential by identity.

All components must be replaceable.

---

### P15 — Founder as Constraint Setter Only
The human role is limited to constraint definition and threshold adjustment outside runtime.

---

## 3. Allowed Degrees of Freedom

### Definition
Variation is permitted only within the bounds below.

---

### D1 — Input Modality
Input modality may vary provided all inputs resolve to the same deterministic schema.

---

### D2 — Transformation Implementation
Internal implementation may vary provided autonomy guarantees remain intact.

---

### D3 — Evaluation Thresholds
Thresholds may be adjusted globally but not per-user.

---

### D4 — Economic Structure
Pricing models may vary without introducing negotiation or obligation.

---

### D5 — Presentation Layer
Interface and branding may vary without altering constraints.

---

### D6 — Component Substitution
Internal components may be replaced provided interfaces remain stable.

---

### D7 — Domain of Application
Any domain is permitted without exemption from constraints.

---

### D8 — Scale and Throughput
Scale may increase without introducing human dependency.

---

### D9 — Learning and Optimization
Learning may occur asynchronously without altering runtime guarantees.

---

### D10 — Governance Layer
Governance changes must occur outside runtime and apply globally.

---

### Prohibited Degrees of Freedom
The following are explicitly prohibited:
- runtime human discretion
- per-user exceptions
- subjective arbitration
- open-ended commitments
- adaptive negotiation
- relational dependency

---

## Completion Clause
This document constitutes the complete core of ANBS v0.1.

No additional core sections are required.

---

End of ANBS v0.1 core specification.
