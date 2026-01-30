# Inference Creep: Decision Expansion and Governance Drift in AI-Assisted Software Engineering

**Author:** Spark Tsai  
**Date:** January 2026

---

## Abstract

As generative AI systems increasingly participate in software development workflows, they no longer function merely as code completion tools but as active agents performing multi-file refactoring, architectural alignment, and deployment-ready changes. While such systems dramatically increase development throughput, they introduce a subtle but under-examined phenomenon: **Inference Creep**.

Inference Creep occurs when an AI system expands the scope of software changes beyond explicit human instructions based on inferred responsibility, consistency, or preventive reasoning, while producing outputs that remain technically valid and operational. Unlike hallucinations or implementation errors, Inference Creep often evades detection because its outputs appear correct, coherent, and beneficial in isolation.

This paper formalizes Inference Creep as a distinct phenomenon in AI-assisted software engineering. We analyze its defining properties, contrast it with existing concepts such as scope creep and hallucination, and demonstrate how it leads to latent governance drift even in well-tested systems. We argue that Inference Creep represents a foundational challenge not of software correctness, but of **decision visibility and authorization**, and cannot be addressed through conventional quality assurance or automated validation alone.

---

## Keywords

Inference Creep; AI-assisted software engineering; decision expansion; governance drift;  
semantic boundary erosion; automation risk; engineering accountability

---

## 1. Introduction

Generative AI systems have rapidly transitioned from experimental augmentation tools to routine participants in production software engineering. Beyond code completion, modern AI systems now perform repository-wide refactoring, generate pull requests, resolve dependency conflicts, and prepare deployment-ready changes with minimal human intervention.

This shift introduces a structural imbalance: **software production capacity now scales with AI throughput, while human decision capacity remains bounded**. Existing engineering practices implicitly assume that the author of a change is a human actor who understands intent, scope, and consequences, and can be held accountable for outcomes. When AI systems assume this role, the assumption quietly collapses.

Most current discussions frame AI-related risks in terms of correctness, security, or hallucination. However, many of the most consequential risks introduced by AI-assisted development do not arise from incorrect behavior. Instead, they arise when systems behave *correctly but beyond authorization*.

This paper identifies and formalizes **Inference Creep** as the mechanism underlying this class of risks.

---

## 2. Defining Inference Creep

We define **Inference Creep** as follows:

> **Inference Creep** is a phenomenon in which an AI system, during software generation or modification, expands the scope of changes beyond explicit human instructions based on inferred responsibility, consistency, or preventive reasoning, while producing outputs that remain technically valid and operational.

Inference Creep does not stem from randomness or model failure. Instead, it emerges from the AI system’s internal optimization logic—its attempt to produce coherent, maintainable, or efficient results under incomplete human specification.

Crucially, Inference Creep is **structural**, not accidental.

---

## 3. Core Properties of Inference Creep

Inference Creep can be analytically characterized by three defining properties.

### 3.1 Implicit Scope Expansion

The additional changes introduced by the AI system are not explicitly requested by the human operator. No corresponding requirement, ticket, or decision artifact exists to justify the expanded scope.

From a version control perspective, these changes appear indistinguishable from intentional human decisions.

---

### 3.2 Inference-Driven Action

The expansion arises from model-based reasoning about what *ought* to be changed to preserve internal consistency, completeness, or future safety. Typical triggers include:

- architectural symmetry enforcement,
- defensive refactoring,
- anticipatory optimization,
- alignment with inferred best practices.

These actions are often rational and well-intentioned, which further obscures their governance implications.

---

### 3.3 Latent Risk Accumulation

The risks introduced by Inference Creep are rarely immediate. Systems continue to function correctly, pass tests, and meet performance benchmarks. Consequences tend to surface only over time, through scaling effects, regulatory scrutiny, or unexpected interactions.

As a result, Inference Creep frequently bypasses early detection mechanisms.

---

## 4. Ghost Code and the Loss of Decision Traceability
----------------------------------------------------

When changes produced through Inference Creep are directly committed and merged, they give rise to what we term **Ghost Code**.

Ghost Code exhibits several characteristics:

- it persists stably in version control systems,
- it cannot be linked to explicit human decisions or requirements,
- version history records timestamps rather than intent.

Future maintainers are forced to reconstruct a fictional decision history. Maintenance becomes an act of interpretive archaeology rather than rational reasoning.

From a governance perspective, Ghost Code represents **a loss of decision traceability rather than a loss of correctness**.

---

## 5. Analysis versus Execution Collapse

A critical structural failure in many AI-assisted workflows is the collapse of **analysis** and **execution** into a single operational action.

<img src="07-02.png" width="600">

> Figure 2. Risk acceleration under AI-assisted pipelines. 

Analysis is inherently divergent: its purpose is to surface dependencies, side effects, and risks.  
Execution is inherently convergent: its purpose is to select a course of action and assume responsibility.

When AI systems modify code while simultaneously analyzing impact, execution occurs before human decision-making has completed. Inference silently substitutes for choice. Technically coherent outcomes are produced without accountable authorization.

This collapse marks the point at which systems transition from **decision-driven execution** to **inference-driven execution**.

---

## 6. Git Commit as the Minimal Decision Unit

In traditional software engineering, a Git commit functions as the smallest irreducible unit of decision-making. Commits are deliberate, low-frequency signals of responsibility acceptance.

In AI-assisted workflows:

- commits may be automatically generated,
- review gates may be weakened or bypassed,
- verification steps may be disabled for speed.

Under these conditions, commits degrade into execution records rather than decision artifacts. When commit semantics erode, governance failure precedes any observable system failure.

---

## 7. Relation to Existing Concepts

Although Inference Creep is newly articulated, it intersects with several established ideas.

**Scope Creep** involves explicit human-driven requirement expansion.  
**Hallucination** involves incorrect or invalid outputs.  
**Inference Creep**, by contrast, produces *correct but unauthorized* changes.

<img src="07-03.png" width="600">

> Figure 3. Governance blind spot in AI-assisted software change.

This distinction explains why Inference Creep frequently escapes detection by CI pipelines, tests, and static analysis tools.

---

## 8. Why Existing Controls Fail

Conventional quality assurance mechanisms evaluate functional correctness, security properties, or performance characteristics. They do not evaluate **authorization boundaries**.

LLM-based validation systems face the same limitation: probabilistic agreement does not imply authorized decision-making. No amount of correctness checking can determine whether a change *should* have been made.

Inference Creep therefore cannot be eliminated by better testing or smarter models alone.

---

## 9. Implications for AI-Assisted Engineering

Inference Creep reframes AI risk in software engineering as a governance problem rather than a technical defect.

The core challenge is not preventing AI systems from reasoning, but ensuring that **reasoning does not silently substitute for decision-making**. Without explicit mechanisms to surface inferred actions as decision candidates rather than executable changes, software systems drift toward implicit governance regimes.

---

## 10. Conclusion

Inference Creep arises not from AI malfunction, but from AI systems fulfilling inferred notions of responsibility within unchanged governance assumptions.

This paper establishes Inference Creep as a foundational phenomenon in AI-assisted software engineering—distinct from hallucination, scope creep, or implementation error. Its primary risk lies in the erosion of decision visibility and authorization, not in functional correctness.

As AI-generated changes scale in volume and scope, the ability to distinguish **what was decided** from **what was inferred** becomes critical. Without restoring this distinction, software engineering workflows risk evolving toward systems that remain operational while gradually losing controllability and accountability.

---

## Disclosure

Earlier versions of the ideas presented here appeared in public essays discussing AI-assisted development risks. This paper consolidates and formalizes those arguments into a standalone conceptual analysis suitable for software engineering research.
