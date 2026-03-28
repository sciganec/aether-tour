# AETHER (NEUTRAL) — OFFICIAL RULEBOOK

## 1. General Overview

Aether is an abstract strategy game defined by:

* Shared pieces (no ownership)
* Merge mechanics (set union)
* Toroidal board topology
* Instant win condition via full-type aggregation

---

## 2. Equipment

### 2.1 Board

* Square grid: N×N
* Topology: **torus**

  * Left edge connects to right
  * Top connects to bottom

---

### 2.2 Tokens

* Total: N² tokens
* Types: T
* Each type appears exactly N² / T times (balanced setup)

---

### 2.3 Token Structure

Each token represents a **set of types**:

* Initial tokens: singletons `{A}`, `{B}`, …
* After merges: unions (e.g. `{A,B,C}`)

---

## 3. Initial Setup

Each cell contains exactly one token.

Assignment rule:
Type = (row + column) mod T

---

## 4. Turn Structure

Players alternate turns.

On a turn:

1. Select any token
2. Move it using a **knight move**
3. Resolve landing:

---

## 5. Movement

Knight move:

* 2 in one direction + 1 perpendicular
* Toroidal wrapping applies

Each token always has 8 legal destinations.

---

## 6. Merge Rule

If landing cell is occupied:

* Tokens merge:
  New token = union of both sets

Example:
`{A,B}` + `{B,C}` → `{A,B,C}`

---

## 7. Empty Move

If landing cell is empty:

* Token simply moves

---

## 8. Win Condition

A player wins instantly if a token becomes:

> `{all T types}`

Game ends immediately.

---

## 9. Draw Rule

Optional (tournament):

* If 50 moves occur without a merge → draw

---

## 10. Game Properties

* No stalemate possible
* No hidden information
* Perfect information deterministic game

---

## 11. Core Identity

> Aether is a **shared-resource combinatorial race with positional control**

---

---

# AETHER — THEORY GUIDE (CORE PRINCIPLES)

## 1. Fundamental Insight

> You are not building pieces — you are controlling access.

---

## 2. Three Strategic Axes

### 2.1 Access

Can a required type reach your structure?

---

### 2.2 Isolation

Can you prevent access for ≥1 move?

---

### 2.3 Tempo

Who performs the final merge?

---

## 3. Structural Units

| Structure | Meaning            |
| --------- | ------------------ |
| 1-set     | raw resource       |
| 2-set     | unstable structure |
| 3-set     | critical mass      |
| T-set     | victory            |

---

## 4. Critical Rule

> Any structure that can be completed by opponent next turn is losing.

---

## 5. Golden Principles

1. Never create a structure your opponent can complete
2. Distance (knight metric) is everything
3. Delay commitment until safe
4. Force opponent to commit first
5. Control the final merge

---

## 6. Common Mistakes

❌ Early merge
❌ Ignoring distances
❌ Greedy completion
❌ Local thinking on a torus

---

## 7. Strategic Identity

> Aether is a game of **threat geometry and timing**, not material advantage

---

---

# AETHER — OPENING THEORY

## 1. Opening Goal

* Maintain symmetry
* Avoid early merges
* Map type distances

---

## 2. Opening Types

### 2.1 Passive Opening (Optimal)

* Non-merging moves
* Create empty cells
* Preserve flexibility

✔ safest

---

### 2.2 Aggressive Opening

* Early merge

⚠ only correct if:

* resulting structure is isolated

---

## 3. Opening Rule

> First player should NOT be the first to create a vulnerable 2-set

---

## 4. Symmetry Principle

If position is symmetric:
→ optimal play preserves draw potential

---

## 5. Opening Objective

* Force opponent into:

  * unsafe merge
  * or positional concession

---

## 6. Early Game Checklist

* Distance to all types
* Escape routes
* Opponent threats

---

## 7. Opening Evaluation

| Move Type        | Value   |
| ---------------- | ------- |
| Safe move        | neutral |
| Unsafe merge     | losing  |
| Controlled merge | strong  |

---

---

# AETHER — MIDGAME THEORY

## 1. Transition

Midgame begins with first stable 2-set.

---

## 2. Core Battle

> Control of type access

---

## 3. Key Patterns

### 3.1 Safe 2-set

* no completion threat

---

### 3.2 Contested 2-set

* both players can reach

→ volatile

---

### 3.3 Trap Formation

* forcing opponent into completion exposure

---

## 4. Strategic Tools

### 4.1 Distance Counting

* knight metric on torus

---

### 4.2 Multi-threat Creation

* two possible completions

---

### 4.3 Denial

* block or delay key types

---

## 5. Midgame Objectives

1. Build controlled structure
2. Deny opponent access
3. Maintain tempo advantage

---

## 6. Critical Transition

From 2-set → 3-set:

> must be done ONLY under isolation

---

## 7. Midgame Identity

> Dynamic positional struggle with combinatorial threats

---

---

# AETHER — ENDGAME THEORY

## 1. Definition

Endgame begins when a 3-set (or T−1 set) appears.

---

## 2. Core Principle

> The game reduces to access to the final type

---

## 3. Winning Condition

If:

* you have [A,B,C]
* opponent cannot reach D in 1 move

→ forced win

---

## 4. Losing Condition

If:

* opponent can reach your structure

→ immediate loss

---

## 5. Endgame Types

### 5.1 Open Endgame

* multiple access paths
  → unstable

---

### 5.2 Closed Endgame

* isolated structure
  → winning

---

## 6. Tempo Battles

* one move decides outcome
* zugzwang-like positions exist

---

## 7. Endgame Technique

1. Count distances
2. Remove opponent access
3. Force commitment
4. Execute final merge

---

## 8. Endgame Identity

> Pure race between isolation and reachability

---

---

# AETHER — VARIANT BALANCE & OFFICIAL FORMATS

## 1. Core Parameter

R = N² / T

---

## 2. Balance Spectrum

| R   | Effect  |
| --- | ------- |
| ≤5  | trivial |
| 6–8 | optimal |
| ≥10 | chaotic |

---

## 3. Official Formats

### 🥇 Standard Competitive

7×7 / 7 types
→ maximum strategic depth

---

### 🥈 Tournament

6×6 / 6 types
→ balanced and accessible

---

### 🥉 Entry Level

5×5 / 5 types
→ fast and tactical

---

## 4. Solved / Near-Solved

| Variant | Status        |
| ------- | ------------- |
| 3×3     | solved (draw) |
| 4×4     | near-solved   |
| 5×5+    | unsolved      |

---

## 5. Design Identity

Aether is defined by:

* shared control
* merge mechanics
* spatial access logic

---

## 6. Final Definition

> Aether is a **combinatorial access-control strategy game on a toroidal graph**

---

