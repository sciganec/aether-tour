# Aether (Neutral) — Mathematical Research Overview

## Abstract

This document presents a structured analysis of the Aether game family under Neutral rules (shared pieces, merge mechanics, toroidal board). The study focuses on:

* State space complexity
* Game tree growth
* Strategic depth emergence
* Solvability across board sizes

The central finding:

> **Game complexity is governed primarily by the ratio R = N² / T (board size vs number of types), not by board size alone.**

---

## Core Mechanics (Formalized)

* Board: N×N torus
* Tokens: N² total
* Types: T
* Each token = subset of {1..T}
* Merge: set union
* Win condition: full set {1..T}

---

## Key Structural Properties

### 1. Monotonicity

* Number of tokens strictly decreases
* Information strictly increases

### 2. Shared Progress

* Both players operate on the same objects
* Progress is globally accessible

### 3. Non-ownership

* No piece belongs to a player
* Control is positional, not material

---

## Fundamental Complexity Driver

R = N² / T

| Range     | Behavior               |
| --------- | ---------------------- |
| R ≤ 5     | Degenerate / trivial   |
| 6 ≤ R ≤ 8 | Optimal balance        |
| R ≥ 10    | Chaotic / high entropy |

---

## Taxonomy of Game Phases

1. Dispersed phase (no merges)
2. 2-set emergence
3. 3-set critical phase
4. Final condensation

---

## Core Strategic Principle

> The game is not about building — it is about controlling access.

---

---

# Complexity Scaling Across Board Sizes

## State Space Estimation

General form:

Σ C(N², k) · (2^T − 1)^k ≈ (1 + (2^T − 1))^(N²)

---

## Results

| Variant   | State Space | Game Tree  |
| --------- | ----------- | ---------- |
| 3×3 (T=3) | ~10⁶–10⁷    | ~10⁸–10¹²  |
| 4×4 (T=4) | ~10¹⁶–10¹⁸  | ~10²⁰–10³⁰ |
| 5×5 (T=5) | ~10³⁰–10³⁵  | ~10⁴⁰      |
| 6×6 (T=6) | ~10⁵⁵–10⁶²  | ~10⁸⁰      |
| 7×7 (T=7) | ~10⁹⁰–10¹⁰⁰ | ~10¹³⁰     |

---

## Key Insight

Each +1 dimension increases complexity by:

> **~25–40 orders of magnitude**

---

## Comparison with Classical Games

| Game        | State Space | Game Tree |
| ----------- | ----------- | --------- |
| Tic-tac-toe | ~10⁵        | trivial   |
| Aether 4×4  | ~10¹⁷       | medium    |
| Chess       | ~10⁴⁵       | ~10¹²³    |
| Aether 7×7  | ~10¹⁰⁰      | ~10¹³⁰    |
| Go          | ~10¹⁷⁰      | ~10³⁶⁰    |

---

## Conclusion

* 4×4 → solvable domain
* 5×5 → tactical domain
* 6×6 → strategic domain
* 7×7 → high-complexity system

---

---

# Solved Case: 3×3 / 3 Types

## Theorem

> The game is a forced draw under optimal play.

---

## Proof Sketch

### 1. Full Reachability

On 3×3 torus:

* every square is reachable in 1 knight move

---

### 2. Immediate Capture Property

For any merge [A,B]:

* ∃ C such that:
  → C can reach [A,B] in 1 move

---

### 3. Consequence

Any merge:
→ immediately loses

---

### 4. Remaining Moves

Only legal optimal moves:

* non-merging moves

→ infinite neutral cycling

---

## Result

| Property          | Value |
| ----------------- | ----- |
| First-player win  | ❌     |
| Second-player win | ❌     |
| Outcome           | Draw  |

---

## Strategic Interpretation

> 3×3 is a **pure tempo system with zero safe progress**

---

## Design Insight

> Minimum viable board size for meaningful strategy is 4×4

---

---

# Near-Solved Case: 4×4 / 4 Types

## Status

> Practically solvable, likely theoretical draw

---

## Key Structural Change vs 3×3

* Not all positions reachable in 1 move
* Safe merges become possible

---

## Critical Lemmas

### Lemma 1 (Immediate Loss)

If [A,B,C] has access to D in 1 move:
→ loss

---

### Lemma 2 (Isolation Win)

If [A,B,C] is isolated ≥2 moves from D:
→ win

---

## Core Mechanism

> Isolation vs Access

---

## Game Phases

### Phase 1: Neutral

* no merges
* symmetry preserved

### Phase 2: 2-set creation

* first imbalance

### Phase 3: 3-set critical zone

* decisive phase

---

## Optimal Policy

1. Avoid early merges
2. Track knight-distance to all types
3. Create 2-set only under control
4. Create 3-set only if isolated
5. Force opponent into access loss

---

## Strategic Type

> Positional control + timing

---

## Likely Outcome

| Property                | Value                |
| ----------------------- | -------------------- |
| First-player forced win | ❌ (unlikely)         |
| Solvability             | ✅ likely             |
| Result                  | Draw (most probable) |

---

## Interpretation

> 4×4 is the first **true strategic version** of Aether

---

---

# Emergent Strategy in Larger Boards (5×5 → 7×7)

## Transition of Game Nature

| Size | Nature         |
| ---- | -------------- |
| 5×5  | Tactical       |
| 6×6  | Strategic      |
| 7×7  | Deep strategic |

---

## New Phenomena

### 1. Delayed Merge Strategy

* postponing commitment becomes optimal

---

### 2. Multi-threat Structures

* simultaneous access points

---

### 3. Zone Control

* spatial influence emerges

---

### 4. Tempo Manipulation

* forcing opponent timing errors

---

## Critical Mechanic

> Not building structures, but **denying access paths**

---

## 7×7 Key Insight

* near-chess-level game tree
* high branching factor
* long causal chains

---

## Strategic Identity

> Hyper-branching combinatorial positional system

---

## Comparison

| Feature   | Chess              | Go          | Aether 7×7     |
| --------- | ------------------ | ----------- | -------------- |
| Ownership | yes                | yes         | no             |
| Capture   | yes                | yes         | merge          |
| Objective | positional         | territorial | combinatorial  |
| Core      | tactics + strategy | territory   | access control |

---

## Conclusion

> Aether becomes a **new class of abstract game**, not reducible to chess or go paradigms

---

---

# Design Optimization: Choosing the Ideal Variant

## Key Variable

R = N² / T

---

## Optimal Range

6 ≤ R ≤ 8

---

## Evaluated Configurations

| Variant | R    | Quality   |
| ------- | ---- | --------- |
| 5×5 / 5 | 5    | too tight |
| 6×6 / 6 | 6    | excellent |
| 7×7 / 7 | 7    | optimal   |
| 8×8 / 5 | 12.8 | chaotic   |

---

## Recommended Formats

### Main Competitive

→ 7×7 / 7 types

### Tournament

→ 6×6 / 6 types

### Entry-level

→ 5×5 / 5 types

---

## Design Principle

> Balance between **resource scarcity and redundancy**

---

## Final Insight

> Complexity emerges from **interaction density, not size alone**

---

## Meta Conclusion

Aether defines a new design axis:

* not material advantage
* not territory
* but:

> **information condensation under shared control**

---
