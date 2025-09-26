---
title: Inner Product
tags:
  - math
  - physics
  - quantum
draft:
---
A guide to the inner product in Bra-Ket (Dirac) notation, used in quantum mechanics.

## Definition
- The **inner product** `⟨φ|ψ⟩` is a complex number representing the overlap between two quantum states `|ψ⟩` and `|φ⟩` in a Hilbert space.
- It is the "dot product" for complex vector spaces, computed as the conjugate transpose of `|φ⟩` applied to `|ψ⟩`.

## Notation
- Written as `⟨φ|ψ⟩`, where:
  - `|ψ⟩` is a ket (state vector, column vector).
  - `⟨φ|` is a bra (dual vector, row vector conjugate of `|φ⟩`).

## Properties
- **Conjugate Symmetry**: `⟨φ|ψ⟩ = ⟨ψ|φ⟩*` (complex conjugate).
- **Linearity**: `⟨φ|aψ₁ + bψ₂⟩ = a⟨φ|ψ₁⟩ + b⟨φ|ψ₂⟩`, where `a, b` are complex numbers.
- **Positive Definiteness**: `⟨ψ|ψ⟩ ≥ 0`, and `⟨ψ|ψ⟩ = 0` only if `|ψ⟩ = 0`.
- **Normalization**: If `⟨ψ|ψ⟩ = 1`, the state `|ψ⟩` is normalized.

## Applications
- **Probability**: The probability of finding state `|ψ⟩` in basis state `|i⟩` is `|⟨i|ψ⟩|²`.
- **Orthogonality**: States `|ψ⟩` and `|φ⟩` are orthogonal if `⟨φ|ψ⟩ = 0`.
- **Expectation Value**: For an operator `Â`, the expectation value is `⟨Â⟩ = ⟨ψ|Â|ψ⟩`.

## Example
- For qubit states `|ψ⟩ = [a b]^T` and `|φ⟩ = [c d]^T`:
  - `⟨φ| = [c* d*]`, `|ψ⟩ = [a b]^T`.
  - Inner product: `⟨φ|ψ⟩ = c*a + d*b`.
  - If `|ψ⟩ = |0⟩ = [1 0]^T` and `|φ⟩ = |1⟩ = [0 1]^T`, then `⟨1|0⟩ = 0` (orthogonal).

## Notes
- The inner product is central to quantum mechanics for computing amplitudes and probabilities.
- For deeper study, see texts like Sakurai’s *Modern Quantum Mechanics*.