---
title: Outer Product
draft: false
tags:
  - math
  - physics
  - quantum
---
A guide to the outer product in Bra-Ket notation for quantum mechanics.

## Definition
- The **outer product** `|ψ⟩⟨φ|` is an operator (matrix) formed by combining a ket `|ψ⟩` and a bra `⟨φ|`.
- It maps a state `|χ⟩` to a new state proportional to `|ψ⟩`: `|ψ⟩⟨φ|χ⟩ = ⟨φ|χ⟩|ψ⟩`.

## Notation
- Written as `|ψ⟩⟨φ|`, where:
  - `|ψ⟩` is a ket (column vector).
  - `⟨φ|` is a bra (row vector, conjugate transpose of `|φ⟩`).

## Properties
- **Not Commutative**: `|ψ⟩⟨φ| ≠ |φ⟩⟨ψ|` (different operators).
- **Projection Operator**: If `|ψ⟩ = |φ⟩` and `⟨ψ|ψ⟩ = 1`, then `|ψ⟩⟨ψ|` is a projection operator onto `|ψ⟩`.
  - Example: `|ψ⟩⟨ψ|ψ⟩ = |ψ⟩` for a normalized state.
- **Completeness**: For an orthonormal basis `{|i⟩}`, `Σ |i⟩⟨i| = Î` (identity operator).

## Applications
- **Projection**: `|i⟩⟨i|` projects any state onto basis state `|i⟩`.
- **Operators**: Many quantum operators (e.g., density matrices) are built using outer products.
- **State Manipulation**: Used to construct operators for quantum gates or measurements.

## Example
- For qubit states `|0⟩ = [1 0]^T` and `|1⟩ = [0 1]^T`:
  - Outer product: `|0⟩⟨1| = [1 0]^T [0 1] = [[0 1], [0 0]]`.
  - Action: `|0⟩⟨1| |1⟩ = |0⟩⟨1|1⟩ = |0⟩`, since `⟨1|1⟩ = 1`.
- Projection: `|0⟩⟨0| = [[1 0], [0 0]]`, projects onto `|0⟩`.

## Notes
- Outer products are key to constructing operators in quantum mechanics.
- Refer to quantum mechanics texts for advanced applications.