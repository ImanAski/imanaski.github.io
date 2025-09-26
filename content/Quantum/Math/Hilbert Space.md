---
title: Hilbert Space
tags:
  - math
  - physics
  - quantum
draft:
---
A guide to Hilbert spaces in the context of quantum mechanics and Bra-Ket notation.

## Definition
- A **Hilbert space** is a complete, complex vector space equipped with an inner product, used to describe quantum states.
- It is the mathematical framework for kets `|ψ⟩` and bras `⟨ψ|`.

## Properties
- **Vector Space**: Supports addition and scalar multiplication of states.
  - Example: `|ψ⟩ + |φ⟩` and `a|ψ⟩` (where `a` is a complex number).
- **Inner Product**: Defines `⟨φ|ψ⟩`, enabling norms and angles between states.
- **Completeness**: Every Cauchy sequence of vectors converges to a vector in the space.
- **Basis**: Any state `|ψ⟩` can be expressed as `|ψ⟩ = Σ c_i |i⟩`, where `{|i⟩}` is an orthonormal basis.

## Types
- **Finite-Dimensional**: E.g., qubit systems (2D complex space, like `ℂ²` for a single qubit).
- **Infinite-Dimensional**: E.g., wavefunctions in continuous systems (like position or momentum states).
- **Tensor Product**: For composite systems, e.g., `H₁ ⊗ H₂` for two qubits.

## Applications
- **Quantum States**: Kets `|ψ⟩` live in a Hilbert space, representing possible states of a quantum system.
- **Operators**: Observables (e.g., position, momentum) are Hermitian operators on the Hilbert space.
- **Superposition**: States can be linear combinations of basis states in the Hilbert space.

## Example
- **Qubit Hilbert Space**: A single qubit lives in `ℂ²`, with basis `{|0⟩, |1⟩}`.
  - State: `|ψ⟩ = α|0⟩ + β|1⟩`, where `|α|² + |β|² = 1`.
- **Inner Product**: `⟨ψ|ψ⟩ = |α|² + |β|² = 1` for normalized states.
- **Basis**: `{|0⟩ = [1 0]^T, |1⟩ = [0 1]^T}` is an orthonormal basis for `ℂ²`.

## Notes
- Hilbert spaces generalize Euclidean spaces to complex and infinite dimensions.
- For more, see texts like *Quantum Mechanics* by Griffiths.