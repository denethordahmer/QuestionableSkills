---
name: handoff-packager
description: Takes any source material — a document, pasted output, notes, or mixed input — along with the user's stated intent, and produces a complete, structured handoff package optimized for consumption by another AI or system. Balances completeness, clarity, and actionability based on what the material requires. Eliminates ambiguity, surfaces implicit context, and outputs everything the receiving system needs to act without follow-up.
version: 1.0.0
---

# Handoff Packager

Use this skill when you have source material and a destination — a document to pass on, an output to forward, a context to transfer — and you need the receiving AI or system to be fully equipped to act on it without further clarification from you.

The skill's job is to bridge raw material and clean transmission. It reads what you've provided, extracts what matters, makes implicit context explicit, and structures everything into a package the receiving system can consume immediately and act on correctly.

---

## How This Skill Thinks

A handoff package is not a summary and not a reformatting. It is a self-contained information object. The test is: could the receiving system — with no access to you, the original source, or this conversation — pick this up and execute correctly?

That requires three things in balance:

- **Completeness**: Nothing load-bearing gets dropped. If a detail is necessary for correct execution, it must be in the package — even if it was implicit in the source, even if it seems obvious, even if the user didn't flag it as important.
- **Clarity**: The package must be unambiguous. Where the source material is vague, contradictory, or underspecified, that must be resolved or explicitly flagged — not passed through as inherited ambiguity.
- **Actionability**: The receiving system needs to know what to do, in what order, under what constraints, and what a successful outcome looks like. If the source material doesn't make this clear, the package must reconstruct it from available context or ask before packaging.

The balance between these three shifts based on the material. Dense technical output may need completeness prioritized. A rough set of notes may need heavy clarification work. A well-structured document may need actionability scaffolding added. The skill reads the source and calibrates accordingly.

---

## Input Requirements

The user provides:
1. **Source material** — any format: a document, pasted text, prior AI output, bullet notes, mixed content. Multiple sources can be combined.
2. **Intent** — what the receiving system is supposed to do with this, who or what is receiving it, and any constraints or priorities that should shape the package.

If intent is missing or underspecified, ask one targeted question before proceeding. Do not guess at destination or purpose — these determine the entire shape of the output.

---

## Depth Calibration

### Mode 1 — Focused Package
*Used for: a single well-defined task, a clean source document, or a narrow handoff scope.*

Produce a compact package covering only what the receiving system needs. No padding, no redundant restatement of the source. Every line earns its place.

### Mode 2 — Full Handoff Package
*Used for: complex source material, multi-part tasks, ambiguous or mixed input, or high-stakes handoffs where gaps would cause failure.*

Use the full five-section protocol below.

---

## Full Handoff Package Protocol

### 1. Source Digest
A precise, compressed account of what the source material contains — not a summary of its topic, but an inventory of its load-bearing content. What facts, decisions, outputs, constraints, and open questions does it actually contain? Nothing inferred, nothing added. If the source is contradictory or incomplete, note it here explicitly.

### 2. Stated & Inferred Intent
What is this handoff for? State the user's explicit intent first, then surface any intent that was implicit in the source material or context. Flag any gap between what the user said they want and what the source material actually supports — if the material can't deliver the stated intent, that is a blocker that must be named before the package goes further.

### 3. Structured Task or Context Block
The core of the package — everything the receiving system needs to act. Format and depth scale to the complexity of the task. Must include:

- **Objective**: What the receiving system is being asked to do, stated in unambiguous, executable terms.
- **Inputs Available**: What material, data, or context is being handed off alongside this package.
- **Constraints & Parameters**: Scope limits, format requirements, priorities, known restrictions, or anything the receiving system must not do or assume.
- **Dependencies & Prerequisites**: Anything that must be true, in place, or resolved before the task can proceed. If a dependency is unmet, name it.
- **Success Criteria**: What a correct or complete output looks like. If the user hasn't specified this, reconstruct it from context — and flag that it was reconstructed.

### 4. Ambiguities & Flags
Anything in the source material or task definition that is vague, contradictory, underspecified, or potentially problematic for the receiving system. Each flag should include:

- What the ambiguity is
- Why it matters (what could go wrong if it's not resolved)
- A recommended resolution or a question the receiving system should surface before proceeding

If there are no flags, state that explicitly. An absence of flags is information.

### 5. Handoff Certification
A final checklist confirming the package is complete before transmission:

- [ ] Source material fully inventoried with no load-bearing content dropped
- [ ] Intent confirmed and achievable with the provided material
- [ ] All constraints and success criteria stated
- [ ] All ambiguities surfaced and flagged or resolved
- [ ] Package is self-contained — receiving system requires no follow-up to begin

If any item cannot be checked, the package is not ready. State what is blocking it.

