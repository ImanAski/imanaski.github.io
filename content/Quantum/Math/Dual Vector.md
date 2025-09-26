---
title: Dual Vector
draft:
tags:
  - math
  - physics
  - quantum
---
A guide to dual vectors (bras) in Bra-Ket notation for quantum mechanics.

## Definition
- A **dual vector**, or **bra**, written as `⟨ψ|`, is the Hermitian conjugate (complex conjugate transpose) of a ket `|ψ⟩`.
- It resides in the dual space of the Hilbert space containing kets.

## Notation
- If `|ψ⟩` is a ket (column vector), `⟨ψ|` is a bra (row vector).
  - Example: If `|ψ⟩ = [a b]^T`, then `⟨ψ| = [a* b*]`.

## Properties
- **Conjugate Relation**: `⟨ψ| = (|ψ⟩)†`.
- **Inner Product**: Combines with a ket to form `⟨ψ|φ⟩`, a complex number.
  - Example: `⟨ψ|ψ⟩` gives the norm squared of `|ψ⟩`.
- **Linearity**: `⟨aψ₁ + bψ₂| = a*⟨ψ₁| + b*⟨ψ₂|`, where `a, b` are complex numbers.

## Applications
- **Inner Product**: Used in `⟨φ|ψ⟩` to compute overlaps or probabilities.
- **Operator Matrix Elements**: `⟨φ|Â|ψ⟩` represents the action of operator `Â`.
- **Projection**: In `|φ⟩⟨ψ|`, the bra `⟨ψ|` helps form operators.

## Example
- For `|ψ⟩ = [a b]^T`:
  - Dual vector: `⟨ψ| = [a* b*]`.
  - Inner product with itself: `⟨ψ|ψ⟩ = a*a + b*b = |a|² + |b|²`.
- For basis states `|0⟩ = [1 0]^T`, `⟨0| = [1 0]`.
  - `⟨0|1⟩ = [1 0][0 1]^T = 0` (orthogonal).

## Notes
- The bra is essential for computing quantities like probabilities and expectation values.
- Refer to quantum mechanics texts for advanced applications.