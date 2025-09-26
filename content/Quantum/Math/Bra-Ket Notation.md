---
title: Bra-Ket Notation
draft:
tags:
  - math
  - physics
  - quantum
---
A concise guide to Dirac (Bra-Ket) notation used in quantum mechanics.

## 1. Basic Definitions
- **Ket**: A vector representing a quantum state, written as `|ψ⟩`.
  - Example: `|ψ⟩` is a state vector in a Hilbert space.
- **Bra**: The dual vector (conjugate transpose) of a ket, written as `⟨ψ|`.
  - Example: If `|ψ⟩` is a column vector, `⟨ψ|` is its row vector conjugate.
- **[[Hilbert Space]]**: The complex-valued vector space where kets and bras reside.

## 2. Key Notations
- **[[State Vector]]**: `|ψ⟩ = Σ c_i |i⟩`, where `c_i` are complex coefficients and `|i⟩` are basis states.
- **[[Dual Vector]]**: `⟨ψ| = (|ψ⟩)†`, the Hermitian conjugate of `|ψ⟩`.
- **[[Inner Product]]**: `⟨φ|ψ⟩` yields a complex number, the overlap between states `|ψ⟩` and `|φ⟩`.
  - Properties:
    - `⟨φ|ψ⟩ = ⟨ψ|φ⟩*` (complex conjugate).
    - `⟨ψ|ψ⟩ ≥ 0`, equals zero if `|ψ⟩ = 0`.
- **[[Outer Product]]**: `|ψ⟩⟨φ|` represents an operator projecting onto `|ψ⟩`.
  - Example: `|i⟩⟨i|` is a projection operator onto basis state `|i⟩`.

## 3. Operators
- **Operator on a Ket**: `Â|ψ⟩` applies operator `Â` to state `|ψ⟩`, producing a new ket.
- **Expectation Value**: `⟨Â⟩ = ⟨ψ|Â|ψ⟩`, the average value of observable `Â` in state `|ψ⟩`.
- **Adjoint Operator**: `⟨φ|Â|ψ⟩ = ⟨ψ|Â†|φ⟩*`, where `Â†` is the Hermitian conjugate of `Â`.
- **Hermitian Operator**: `Â = Â†`, represents observables (e.g., position, momentum, energy).

## 4. Basis and Completeness
- **Orthonormal Basis**: Basis states `|i⟩` satisfy:
  - Orthogonality: `⟨i|j⟩ = δ_ij` (Kronecker delta, 1 if `i=j`, 0 otherwise).
  - Normalization: `⟨i|i⟩ = 1`.
- **Completeness Relation**: `Σ |i⟩⟨i| = Î`, where `Î` is the identity operator.
  - Allows: `|ψ⟩ = Σ |i⟩⟨i|ψ⟩`.

## 5. Common Operations
- **Probability**: Probability of finding `|ψ⟩` in basis state `|i⟩` is `|⟨i|ψ⟩|²`.
- **Superposition**: A state can be `|ψ⟩ = c_1|1⟩ + c_2|2⟩ + ...`, where `c_i` are complex amplitudes.
- **Tensor Product**: For composite systems, states combine as `|ψ⟩ ⊗ |φ⟩`, written as `|ψ⟩|φ⟩` or `|ψ,φ⟩`.

## 6. Examples
- **Qubit States**:
  - `|0⟩ = [1 0]^T`, `|1⟩ = [0 1]^T`.
  - Superposition: `|ψ⟩ = α|0⟩ + β|1⟩`, where `|α|² + |β|² = 1`.
- **Inner Product Example**:
  - If `|ψ⟩ = [a b]^T`, then `⟨ψ| = [a* b*]`.
  - `⟨ψ|ψ⟩ = |a|² + |b|²`.
- **Operator Example**:
  - Pauli operator `σ_x = [[0 1], [1 0]]`.
  - Action: `σ_x|0⟩ = |1⟩`, `σ_x|1⟩ = |0⟩`.

## 7. Useful Identities
- `⟨φ|Â|ψ⟩ = ⟨φ|(Â|ψ⟩) = (⟨φ|Â)|ψ⟩`.
- `(Â|ψ⟩)† = ⟨ψ|Â†`.
- Projection: `|ψ⟩⟨ψ|ψ⟩ = |ψ⟩`, if `⟨ψ|ψ⟩ = 1`.

---

For deeper study, refer to quantum mechanics texts like *Modern Quantum Mechanics* by Sakurai.