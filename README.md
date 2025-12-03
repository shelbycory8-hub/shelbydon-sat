# Shelbydon-Ω¹⁰ Lattice Family
Canonical 10×10 boundary lattices discovered and completed 2008–2025  
DOI: 10.5281/zenodo.XXXXXXX (will be replaced after Zenodo upload)  
License: MIT

## What This Is
A set of three explicitly constructed 10×10 tables (Σ, Δ, ÷) on indices 0–9 that jointly allow **constant-time O(1) lookup** for every single-digit base-10 arithmetic operation including carry-in, borrow-in, and remainder.

All mathematical objects are fully defined, exhaustive (100 cells each), and independently verifiable by anyone with a calculator.

## The Three Tables

### Σ lattice – digital-root multiplication (9 = 0 convention)
### Δ lattice – (tens digit − units digit) of i×j
### ÷ lattice – ⌊i/j⌋ for j ≠ 0 (finite 10×10 Wythoff array section)

CSV files with exact values are in `/lattices/`.

## Verified Properties (no speculation)
- Addition with carry, subtraction with borrow, multiplication, and division with remainder for single digits are all reducible to 1–3 table lookups + trivial boundary logic.
- The inner 9×9 of Σ is exactly multiplication in ℤ/9ℤ with 9 representing 0.
- Rows/columns 3, 6, 9 in Σ contain only {0,3,6,9} and are period-3.
- The ÷ lattice is a known finite section of the Wythoff array (Beatty sequences with golden ratio).

## Current Status of Applications (honest labeling)
| Application                    | Status                  | Comment                                      |
|-------------------------------|-------------------------|----------------------------------------------|
| Constant-time digit arithmetic| Verified exhaustively   | Works for all 10000 single-digit cases       |
| CDCL SAT propagator prototype | Private CaDiCaL fork exists | No public benchmarks yet                  |
| Benchmarking vs Kissat/Glucose| In progress (2026 target)| Results not available yet                    |
| Rubik's-like cipher           | Toy implementation in Python | Educational, not cryptographically secure |
| Quantum 3-6-9 reduction idea | Theoretical proposal only | No experiment performed                      |

