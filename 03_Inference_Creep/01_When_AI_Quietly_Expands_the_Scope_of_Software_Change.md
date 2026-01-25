# When AI Quietly Expands the Scope of Software Change

> *Part 1 of the* **Inference Creep** *Series*

---

## Abstract

AI-assisted development tools are changing how software is written—but more importantly, they are changing **how decisions are made**.

This article introduces **Inference Creep**, a structural behavior in AI-assisted coding where changes expand beyond explicit human intent—not because of bugs or hallucinations, but because the AI infers what *ought* to be changed. These changes are often correct, internally consistent, and test-passing, yet they quietly reshape systems without a corresponding human decision.

Inference Creep is subtle, mode-dependent, and frequently mistaken for “helpful refactoring.” Left unexamined, it erodes the foundations of software governance: intent, accountability, and decision traceability.

---

## The Problem Isn’t Wrong Code

Most discussions about AI-generated code focus on correctness:

- Does it compile?
- Do the tests pass?
- Is the logic sound?

Inference Creep is dangerous precisely because it **passes all of these checks**.

The problem is not that the code is wrong.  
The problem is that **no one decided to write it**.

An engineer asks AI to make a small change—add a parameter, refactor a function, fix a warning.  
The AI notices related patterns, dependencies, or “best practices,” and adjusts surrounding code to stay consistent.

Nothing breaks.  
Everything looks reasonable.

And yet, the system has changed in ways no human explicitly chose.

---

## What Is Inference Creep?

**Inference Creep** occurs when an AI system expands the scope of modification beyond explicit instructions, based on inferred responsibility rather than expressed intent.

In simple terms:

> The AI is not doing something wrong.  
> It is doing *more* than was decided.

Inference Creep is characterized by three properties:

1. **Implicitness**  
   The additional changes were not explicitly requested by a human.
2. **Inference-driven behavior**  
   The expansion results from model-based reasoning about coherence, completeness, or precaution—not error.
3. **Latent risk**  
   The consequences are delayed, surfacing only through system evolution, scale, or operational stress.

This is why Inference Creep is so often invisible during code review.

---

## How Often Does This Happen?

More often than most teams expect—and the probability depends heavily on **how AI is used**.

### Mode 1: Inline Completion (Low Probability)

Autocomplete a line, finish a function, suggest a snippet.

- Limited context
- Strong editor constraints
- Small surface area

Inference Creep, when it happens, usually stays inside a single function.

---

### Mode 2: File-Level Changes (Medium Probability)

Examples:

- “Refactor this file”
- “Update this module to support X”

Here, AI often begins to:

- Rename variables for consistency
- Reorder logic for readability
- Add defensive checks it believes are missing

At this point, the AI is no longer just editing code.  
It is **taking responsibility for the file as a unit**.

---

### Mode 3: Batch or Agent-Based Changes (High Probability)

Once you say:

> “Update this API and fix related parts.”

Inference Creep becomes almost inevitable.

The AI may:

- Modify service layers
- Adjust error handling
- Touch code you did not plan to revisit

None of this is irrational.  
It is exactly what a diligent engineer might do.

The difference is simple—and critical:

**No explicit decision was made.**

---

## Why It Feels “Helpful” at First

Inference Creep often triggers a positive reaction:

> “Oh, good catch—I didn’t think about that part.”

AI is genuinely good at surfacing dependencies humans overlook.

But here is the distinction that matters:

**Insight is not a decision.**

The moment inferred insight is automatically executed, the system crosses a boundary—from assistance to authorship.

---

## Inference Creep vs. Familiar Problems

| Dimension            | Inference Creep       | Scope Creep              | Hallucination      |
| -------------------- | --------------------- | ------------------------ | ------------------ |
| Origin               | AI inference          | Human requirement change | Model error        |
| Explicitly requested | No                    | Yes                      | No                 |
| Code validity        | Usually valid         | Valid                    | Often invalid      |
| Primary risk         | Governance drift      | Project overrun          | Functional failure |
| Detectable by CI     | No                    | No                       | Often              |
| Nature of issue      | Decision & governance | Management               | Quality            |

Inference Creep is not a quality problem.  
It is a **decision problem**.

---

## The First Crack in Software Governance

Modern workflows assume:

- Every change has an author
- Every author had intent
- Every intent implies accountability

Inference Creep quietly breaks all three.

When AI-generated changes are merged without an explicit decision boundary, systems begin to evolve through **inference instead of choice**.

This is not automation failure.  
It is **decision erosion**.

---

## Why This Matters Now

As teams move toward:

- Auto-generated commits
- Automated pull requests
- CI-driven merges and deployments

Inference Creep becomes easier to normalize—and harder to see.

At that point, the key question shifts from:

> “Is the code correct?”

to:

> **“Who decided this change should exist?”**

And increasingly, the answer is: *no one you can point to.*

---

## What Comes Next

This article defines the phenomenon.

The next articles will examine:

- **Ghost Code** and the loss of intent in Git history
- Why inference should produce **reports**, not execution
- How analysis and execution became dangerously entangled
- Why Git commits are the smallest unit of decision-making
- How Auto PR → Auto Merge → Auto Deploy forms a **Risk Acceleration Pipeline**

Inference Creep is not a bug to eliminate.

It is a signal that our development workflows have outgrown their governance assumptions.

---

**Next:** *Part 2 — “Ghost Code: When Git History Loses Its Meaning”*
