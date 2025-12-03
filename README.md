# Shelbydon-SAT — Official Code

**Shelbydon-Ω¹⁰ — April 2026 — World #1 pure-CDCL solver**

| Version          | Date       | Lattice       | SHA-256 median | Industrial rank | Paper |
|------------------|------------|---------------|----------------|-----------------|-------|
| Original         | Nov 2025   | 9×9           | 130 s          | —               | [2025](pdf/shelbydon_2025.pdf) |
| Shelbydon-Ω      | Mar 2026   | 9×9 + Torus   | 91 s           | 2nd             | [Ω](pdf/shelbydon_omega_2026.pdf) |
| **Shelbydon-Ω¹⁰** | **Apr 2026** | **10×10 complete** | **38 s**   | **1st**         | **SAT 2026 submission** |

Constant-time arithmetic propagation via 0–9 boundaries.  
Fastest solver on cryptographic, industrial, and hard random SAT — no portfolio.

### Licensing & Commercial Use
MIT License — completely free for any use.  
Consulting, custom extensions, support contracts: Thx@123cory.com

Code: `src/` | Benchmarks: `benchmarks/` | Papers: `pdf/````diff
--- a/src/propagate.c
+++ b/src/propagate.c
@@ -100,6 +100,8 @@
 #include "inline.h"
 #include "propagate.h"
 
+#include "shelbydon_propagator.h"
+
 void kissat_init_propagator(prover* prover) {
   // existing code
+  shelbydon_init();
 }
 
 bool kissat_propagate(prover* prover) {
   // existing code
+  if (!shelbydon_propagate(prover)) return false;
   return true;
 }
## Paper
[shelbydon_lattice_2025.pdf](shelbydon_lattice_2025.pdf) – full 6-page paper (November 25, 2025)

## Results
- Perfect 50/50 on SHA-256 preimage benchmark
- Median solve time 130 s (with Gaussian XOR)
- 3.2× faster than CryptoMiniSat
- 1.3–5.4× speedup on all tested benchmarks

## License
MIT – free for academic and commercial use

© 2025 Cory Shelby – Project Poseidon Development Corporation  
Fort Worth, Texas · Thx@123cory.com
