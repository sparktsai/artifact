# Inference Creep Series — Index

> How AI-Assisted Development Quietly Breaks Decision-Making in Software Engineering
> *(Toward Decision Behavior Governance)*

---

## Why This Series Exists

AI tools didn’t just make us write code faster.  
They quietly changed **who decides**, **when decisions are made**, and **who ends up responsible**.

This series is not about “AI bugs,” prompt tricks, or productivity hacks.  
It is about a deeper problem:

> **When AI generates, reviews, and deploys changes, decisions start happening without anyone actually deciding.**

Each article in this series isolates one layer of that problem—starting from developer intuition, moving through workflow design, and ending at system-level governance.

---

## The Six Articles, One Logical Arc

This is a **progressive series**.  
Each article builds on the previous one.

---

### **Part 1 — The Feeling Something Is Off**
> **AI Is Writing Code Faster Than Ever — and It’s Killing Software Maintainability**

**Core question:**  
Why do AI-generated changes feel “reasonable” yet impossible to explain later?

**What it introduces:**

- The *Causality Gap* in AI-authored code
- Why maintainability collapses without obvious failures
- The first hint that speed is not the real problem

This article establishes the emotional and experiential ground truth shared by many senior engineers.

---

### **Part 2 — Naming the Invisible Artifact**
> **Ghost Code: When Code Exists Without a Decision**

**Core question:**  
What happens when code has no explainable reason for existing?

**What it introduces:**

- **Ghost Code** as a new form of technical debt
- Why `git blame` stops being useful
- How AI-authored history erases intent

This article reframes maintainability as a **decision traceability problem**, not a documentation problem.

---

### **Part 3 — Reframing the “AI Thought Too Much” Problem**
> **Inference Creep Is Not a Bug — It’s a Signal**

**Core question:**  
What if AI “overthinking” is actually valuable—just misused?

**What it introduces:**

- **Inference Creep** as a phenomenon, not an error
- Why inference should produce *reports*, not *changes*
- The separation of *discovery* from *decision*

This article is the turning point of the series:  
from anxiety → to structured understanding.

---

### **Part 4 — Drawing the Line That Quietly Disappeared**
> **Analysis Ends Here. Execution Starts There.**

**Core question:**  
Where exactly should AI stop—and humans take over?

**What it introduces:**

- Analysis as *divergent*, execution as *convergent*
- Why modern AI tools collapse this boundary
- The moment where “Wait…” should exist—but doesn’t

This article reframes the problem as a **workflow boundary failure**, not a tooling issue.

---

### **Part 5 — The Smallest Unit of Responsibility**
> **A Git Commit Is Not a Technical Action**

**Core question:**  
When did `git commit` stop meaning “I decided this”?

**What it introduces:**

- Commits as the **minimal unit of decision**
- `--no-verify` and auto-approve as responsibility bypasses
- **Diff Fatigue** and why reviewers become rubber stamps

This article grounds governance in daily engineering reality—not policy documents.

---

### **Part 6 — When Automation Becomes a Risk Multiplier**
> **The Risk Acceleration Pipeline**

**Core question:**  
What happens when nobody decides—but everything ships?

**What it introduces:**

- Auto PR → Auto Merge → Auto Deploy as a single pipeline
- **Decision Vacancy** as a system condition
- Why silence becomes consent
- Why on-call engineers inherit decisions they never made

This article elevates the discussion from tooling to **engineering governance**.

---

## The Hidden Throughline

Across all six articles, one pattern repeats:

> AI did not remove responsibility.  
> It **relocated it to the worst possible place**—after deployment.

The real failure is not automation.  
It is **automation without explicit decision design**.

---

## Where This Series Leads

This series intentionally stops **before** proposing full solutions.

Its purpose is to:

- name the failure modes,
- expose the broken assumptions,
- create shared language.

The formal research work that follows introduces:

- **Decision Behavior Governance (DBG)**
- structured decision audits
- roles such as **Code Adjudicator**

Those ideas build on this foundation—but this series stands on its own as the **problem map**.

---

## How to Read This Series

- If you are a **developer**:  
  Read Part 3 → 4 → 5 first.
- If you are a **tech lead or architect**:  
  Read Part 4 → 6.
- If you are in **engineering management or governance**:  
  Read Part 2 → 6.

---

## Final Thought

We didn’t lose control because AI is powerful.  
We lost control because **decisions became implicit**.

Before we talk about controlling AI,  
we need to relearn how to **design decisions**.
