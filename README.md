# Shelbydon-SAT – Official Code (November 25, 2025)

This is the exact propagator described in the paper  
*"The Shelbydon Lattice: A Mod-9 Algebraic Structure for Strong Constraint Propagation in SAT"*  
Cory Shelby, Project Poseidon Development Corporation

Reproduces:
- Perfect 50/50 on SHA-256 preimage (median 130 s with XOR)
- 3.2× faster than CryptoMiniSat
- 1.3–5.4× speedup on all benchmarks in the paper

Quick start:
```bash
cd kissat
patch -p1 < ../kissat-patch/shelbydon.diff
make -j
./kissat --shelbydon=1 instance.cnf
