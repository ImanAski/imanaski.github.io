---
title: State Vector
draft:
tags:
  - math
  - physics
  - quantum
---
A guide to state vectors (kets) in Bra-Ket notation for quantum mechanics.

## Definition
- A **state vector**, or **ket**, written as `|ψ⟩`, represents a quantum state in a Hilbert space.
- It is typically a column vector in a complex vector space.

## Notation
- Written as `|ψ⟩`, where `ψ` labels the state.
  - Example: `|0⟩`, `|1⟩` for qubit basis states, or `|ψ⟩` for a general state.

## Properties
- **Superposition**: `|ψ⟩ = Σ c_i |i⟩`, where `c_i` are complex coefficients and `{|i⟩}` is a basis.
- **Normalization**: `⟨ψ|ψ⟩ = 1` for a physically meaningful state.
- **Linearity**: `|ψ⟩ = a|ψ₁⟩ + b|ψ₂⟩`, where `a, b` are complex numbers.

## Applications
- **Quantum State**: Represents the full description of a quantum system’s state.
- **Probability Amplitudes**: Coefficients `c_i` in `|ψ⟩ = Σ c_i |i⟩` give amplitudes, where `|c_i|²` is the probability of measuring state `|i⟩`.
- **Evolution**: State evolves via operators, e.g., `|ψ(t)⟩ = Û(t)|ψ(0)⟩`, where `Û` is the time-evolution operator.

## Example
- **Qubit State**:
  - `|ψ⟩ = α|0⟩ + β|1⟩`, where `|0⟩ = [1 0]^T`, `|1⟩ = [0 1]^T`, and `|α|² + |β|² = 1`.
  - Example: `|ψ⟩ = (1/√2)(|0⟩ + |1⟩) = (1/√2)[1 1]^T`.
- **Measurement**: Probability of measuring `|0⟩` is `|⟨0|ψ⟩|²`.

## Notes
- State vectors encode all information about a quantum system.
- For more, see texts like *Quantum Mechanics* by Shankar.