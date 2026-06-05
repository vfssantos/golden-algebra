# Golden Shadow Algebra

Exploratory research manuscripts by **Vinicius Santos** (June 2026).

This repository develops a **φ-native shadow algebra**: a layered mathematical framework in which familiar operations (addition, division, trigonometry, roots, calculus, finite Fourier analysis) are not taken as scalar primitives but are relocated to typed layers—trace projections, relations, factor extractions, phase orbits, spread lifts, divisibility-based factor projections, and phase-valued spectra.

The program is motivated by a question parallel to Odrzywołek's **EML** construction ([arXiv:2603.21852](https://arxiv.org/abs/2603.21852)): if elementary functions can be generated from the leaf `1` and `eml(x,y) = e^x − log y`, what algebraic universe is naturally generated from the **golden ratio** φ as the distinguished leaf?

---

## Index

| # | File | Title | Layer focus |
|---|------|-------|-------------|
| 1 | [`01_golden_shadow_algebra.tex`](01_golden_shadow_algebra.tex) | *A Golden Shadow Algebra* | Scalar + trace (foundation) |
| 2 | [`02_quotients_without_division_phi_native.tex`](02_quotients_without_division_phi_native.tex) | *Quotients Without Division* | Rate + factor |
| 3 | [`03_shadow_trigonometry_phi_native.tex`](03_shadow_trigonometry_phi_native.tex) | *Shadow Trigonometry* | Phase |
| 4 | [`04_signatures_before_roots_phi_native.tex`](04_signatures_before_roots_phi_native.tex) | *Signatures Before Roots* | Signature / spread lift |
| 5 | [`05_factors_before_quotients_phi_calculus.tex`](05_factors_before_quotients_phi_calculus.tex) | *Factors Before Quotients* | Factor / calculus |
| 6 | [`06_phase_before_frequencies_golden_decagonal_fourier.tex`](06_phase_before_frequencies_golden_decagonal_fourier.tex) | *Phase Before Frequencies* | Phase + rate (decagonal Fourier) |

**Read in order.** Each later manuscript assumes the vocabulary and layers of the earlier ones.

**Build:** each file is a standalone LaTeX article.

```bash
pdflatex 01_golden_shadow_algebra.tex
pdflatex 02_quotients_without_division_phi_native.tex
pdflatex 03_shadow_trigonometry_phi_native.tex
pdflatex 04_signatures_before_roots_phi_native.tex
pdflatex 05_factors_before_quotients_phi_calculus.tex
pdflatex 06_phase_before_frequencies_golden_decagonal_fourier.tex
```

---

## Applied papers

The [`applied/`](applied/) directory holds companion notes that apply the shadow framework outside the core φ-native series:

| File | Title |
|------|-------|
| [`applied/weight_shadows.tex`](applied/weight_shadows.tex) | *Weight Shadows* — quotienting transformer parameter space by native symmetries |
| [`applied/phase_shadows_fibonacci_anyon_compilation.tex`](applied/phase_shadows_fibonacci_anyon_compilation.tex) | *Phase Shadows for Fibonacci Anyon Compilation* — phase-ring compilation for topological circuits |

These are standalone drafts; they reuse core vocabulary where it fits but do not assume the full six-paper arc. See [`applied/README.md`](applied/README.md) for summaries and build notes.

---

## For LLM / agent consumers

### What this framework is for

Use this framework when you need to:

- **Translate** a classical arithmetic or analytic expression into the correct *layer* (scalar, trace, rate, factor, phase, signature).
- **Decide** whether an operation belongs in the visible scalar grammar or requires a shadow lift.
- **Avoid** treating addition, division, trig, radicals, or derivatives as interchangeable scalar primitives.
- **Reason** about φ-native algebra: exact constants in ℤ[φ], density without division, conjugate-pair arithmetic, golden phase torsion, discriminant signatures, golden difference calculus, decagonal phase-valued Fourier transform.

This is **not** a computational library. There is no code API. The deliverable is a **conceptual hierarchy** and a set of **replacement rules** for classical notation.

### Core methodological rule

> **Do not force a familiar operation into the wrong layer.**

| Classical habit | Shadow-native discipline |
|-----------------|--------------------------|
| Write `x + y` as a scalar term | Addition is `Tr⟨x \| y⟩` (trace layer) |
| Write `x / φ` | Use unit action `B(φ, x) = (φ−1)x` (scalar layer) |
| Write `u / v` as a function | Use relation `Quot(u,v;q) ⟺ u = qv`, or factor projection |
| Start from `sin θ`, `cos θ`, `π` | Start from phase `U` with `U^σ = U⁻¹`, projections `T(U)`, `S(U)` |
| Write `√(S² − 4P)` as primitive | Spread lift: find `D` with `D² = S² − 4P` (signature layer) |
| Write `(f(x+h)−f(x))/h` or `df/dx` as primitive | Golden difference Δ_φ f = f(x)−f(φ⁻¹x); derivative ∂_φ f via `Δ_φ f = (∂_φ f) Δ_φ x` (factor layer) |
| Write DFT with `e^{2πikm/N}` as scalar spectrum | Phase object U with U²−φU+1=0; spectrum in phase ring; inverse uses rate `/10` (Paper 6) |

### Native hierarchy (use this to route queries)

```
Scalar  →  Trace  →  Rate  →  Factor  →  Phase  →  Signature
```

| Layer | Role | Native mechanism | When an agent should use it |
|-------|------|------------------|----------------------------|
| **Scalar** | constants, multiplication, predecessor, unit contraction | `B(x,y) = xy − y`, leaf φ, constants ℤ[φ] | Polynomial expressions, golden contraction, anything provably in the scalar fragment |
| **Trace** | addition | pair `⟨x \| y⟩`, projection `Tr⟨x \| y⟩ = x + y` | Any genuine mixed addition of independent variables |
| **Rate** | fixed-denominator division, averaging | rate class `[x:n]`, diagonal trace section `Tr_n(Δ_n(q)) = nq` | `x/n`, half of a trace, rationalization without variable poles |
| **Factor** | derivative-like quotients, calculus | `Fact_d(h)`: unique `g` with `h = gd`; golden derivative on polynomials | Slopes, `Δ_φ f = (∂_φ f) Δ_φ x`, q-Leibniz, chain factorization (Paper 5) |
| **Phase** | trigonometry, finite Fourier | norm-one unit `U`, `T(U) = U + U⁻¹`, `S(U) = U − U⁻¹`; phase ring `R_φ = ℤ[φ][U]/(U²−φU+1)` | Periodicity, cyclotomic phase, decagonal DFT (Paper 6); spectrum not generally in ℤ[φ] |
| **Signature** | roots, embeddings | spread lift `D² = Tr² − 4 Nm`; real sign of Δ selects geometry | Quadratics, discriminants, `√5`, imaginary unit as elliptic spread |

### Shared notation (glossary)

| Symbol | Definition | Layer |
|--------|------------|-------|
| φ | `(1 + √5) / 2` — distinguished leaf | scalar |
| ψ | `(1 − √5) / 2 = 1 − φ` — Galois conjugate | trace / pair |
| **B**(x,y) | `xy − y = y(x − 1)` — sole scalar binary primitive | scalar |
| ⟨x \| y⟩ | conjugate pair (shadow term) | trace |
| Tr | `x + y` on pairs | trace |
| Nm | `xy` on pairs (derived) | trace |
| Sp | `x − y` on pairs (derived, anti-invariant) | trace / signature |
| σ | slot-swap / Galois conjugation involution | all typed layers |
| ℤ[φ] | `{a + bφ : a,b ∈ ℤ}` — exact scalar constants | scalar |
| C_φ(x) | `B(φ,x) = (φ−1)x = x/φ` — golden contraction | scalar (unit action) |
| q | `φ⁻¹ = φ − 1` | scalar / factor |
| [n]_φ | `1 + q + … + q^(n−1) = φ² − φ^(2−n)` — golden weight | factor |
| [n]_φ! | `[1]_φ [2]_φ … [n]_φ` — golden factorial | factor / rate |
| ∂_φ f | golden derivative: `Δ_φ f = (∂_φ f) Δ_φ x` | factor |
| Δ_φ f | `f(x) − f(φ⁻¹x)` — golden difference | factor |
| E_φ(x) | `Σ x^n / [n]_φ!` — golden exponential (radius φ²) | factor / analytic |
| U | phase object: unit with `U^σ = U⁻¹`, `Nm(U) = 1`; decagonal case `U = ζ₁₀`, `U + U⁻¹ = φ` | phase |
| R_φ | `ℤ[φ][U]/(U² − φU + 1)` — golden phase ring; elements `A + BU`, reduction `U² = φU − 1` | phase |
| f̂_m | `Σ_{k=0}^9 f_k U^{km}` — decagonal Fourier coefficient (phase-valued) | phase |
| T(U), S(U) | `U + U⁻¹`, `U − U⁻¹` (unnormalized) | phase |
| Δ | `S² − 4P = Sp²` — discriminant / spread square | signature |

### Classical → shadow translation (quick reference)

| Classical | Shadow-native |
|-----------|---------------|
| `x + y` | `Tr⟨x \| y⟩` |
| `xy` | `B(x+1, y)` or `mul(x,y)` |
| `x / φ` | `C_φ(x) = B(φ, x)` |
| `x / n` (fixed n) | rate `[x:n]` or solve `Tr_n(Δ_n(q)) = x` |
| `u / v` | relation `u = qv` |
| `Δf / Δx` | `Fact_{Δx}(Δf)`; for golden calculus: `∂_φ f` with `Δ_φ f = (∂_φ f) Δ_φ x` |
| `df/dx`, `(f(x+h)−f(x))/h` | fixed-scale golden difference + factor projection (not a limit) |
| `e^x` | `E_φ(x) = Σ x^n/[n]_φ!` — radius φ², **not entire** |
| `∫ x^n dx` | rate object `[x^(n+1) : [n+1]_φ]`; needs localization for n ≥ 2 |
| `1/x` | local ℤ[φ]-polynomial approximation on `[a,b]`, `0 < a` |
| `2 cos θ` | `T(U) = U + U⁻¹` |
| `2i sin θ` | `S(U) = U − U⁻¹` |
| `arccos(t/2)` | phase lift `U² − tU + 1 = 0` |
| `√(S² − 4P)` | spread lift: `D² = S² − 4P` |
| `2 cos(π/5) = φ` | **reversed:** φ is visible trace; hidden `U` has `U + U⁻¹ = φ`, order 10 |
| DFT on ℤ/10ℤ | `f̂_m = Σ f_k U^{km}` with `U² − φU + 1 = 0`; signals in `ℤ[φ]¹⁰`, spectrum in `R_φ` |
| IDFT / inverse DFT | `f_k = [Σ_m f̂_m U^{-km} : 10]` (rate layer; `1/10 ∉ ℤ[φ]`) |
| Convolution theorem | `widehat{f*g}_m = f̂_m ĝ_m` in `R_φ`; golden twist in phase-ring multiplication |
| Real-signal DFT symmetry | `2` scalar modes (`m=0,5`) + `4` phase-conjugate pairs → 10 DOF |

### Agent routing checklist

When given an expression or problem:

1. **Identify the operation class** (addition, unit scale, fixed average, variable reciprocal, trig, root, derivative, integral, finite Fourier).
2. **Check scalar definability** (Paper 1): mixed affine forms `ax + by + c` with `a,b ≠ 0` are **never** scalar-definable from **B** alone.
3. **Pick the lowest sufficient layer** from the hierarchy above.
4. **For φ-specific geometry**, distinguish the two golden anchors (Paper 4):
   - Phase trace `(S,P) = (φ, 1)` → Δ = φ − 3 < 0 → **circular / pentagonal** (`U¹⁰ = 1`).
   - Scalar pair `⟨φ \| ψ⟩` → `(S,P) = (1, −1)` → Δ = 5 > 0 → **hyperbolic / √5 spread**.
5. **Separate signature from square-class**: real sign of Δ selects embedding geometry; algebraic square-class decides if spread already lives in the current ring/field.
6. **For calculus** (Paper 5): displacement is contraction `x ↦ φ⁻¹x`, not `x + h`. Derivative is divisibility/factor projection. Weights `[n]_φ → φ²` (bounded at chosen real place). Chain rule is two-stage; clean form only for inner maps `g(x) = cx`. Integration needs rate layer except at weights `[1]_φ`, `[2]_φ`.
7. **For finite Fourier** (Paper 6): use decagonal phase `U` with `ζ₁₀ + ζ₁₀⁻¹ = φ` (not n=5, whose trace is φ⁻¹). Forward spectrum lives in `R_φ`, not ℤ[φ]. Orthogonality and convolution theorem are standard for ℤ/10ℤ; golden content is phase-ring placement and `U² = φU − 1` in spectral products. Inverse requires rate `/10`.

### Status and scope

- **Status:** exploratory drafts, not peer-reviewed.
- **Scope:** exact finite-depth algebra, typed completions, polynomial golden calculus, decagonal phase-valued DFT, and conceptual reordering of classical operations. Continuous phase, full analytic categories, fast FFT over `R_φ`, and deformation to ordinary calculus (`q → 1`) are flagged as future work.
- **Not claimed:** replacement for EML universality; global polynomial substitute for `1/x`; complete categorical formalization.

---

## Manuscript summaries

### 1. `01_golden_shadow_algebra.tex` — *A Golden Shadow Algebra*

**One-line summary:** From leaf φ and operation **B** alone, the scalar grammar generates multiplication and predecessor structure but **provably not addition**; addition completes the system only via conjugate pairs and trace projection.

**Question addressed:** What algebraic universe is generated if the distinguished leaf is φ instead of the rational unit 1 (as in EML)?

**Summary:** The paper rejects φ-analytic operators that bake φ into their definition. The clean scalar primitive is **B**(x,y) = y(x−1), interpreted as “scale y by the predecessor of x.” With leaf φ, this generates 1, 0, negation, predecessor, successor, multiplication, and golden contraction `C_φ(x) = x/φ`. Scalar addition is absent not by search failure but by a degree/minimality proof. The scalar fragment is characterized exactly as the multiplicative, constant-shift closure of one-variable polynomials over ℤ[φ]. Exact constants are countable; under one real embedding ℤ[φ] is dense in ℝ (discrete under Minkowski). The two-sorted **golden shadow algebra** adjoins pairs ⟨x \| y⟩ and primitive trace Tr to recover ring operations. Norm and spread are derived macros; the golden pair Φ = ⟨φ \| ψ⟩ recovers Tr = 1, Nm = −1, Sp = √5. The architecture extends to other quadratic units (silver, Gaussian templates).

**Main results:**

| Result | Statement |
|--------|-----------|
| Basic scalar constructions | From **B** and φ: definable 1, 0, φ⁻¹, ψ, −x, x±1, xy |
| Scalar non-additivity (Thm) | No scalar term denotes `ax + by + c` with `a,b ∈ K×`; in particular not `x ± y` |
| Shifted cores (Cor) | Same obstruction for `B_k(f,g) = g(f − k)` |
| Scalar characterization (Thm) | Definable polynomials = multiplicative + constant-shift closure of R[x], R[y]; constants exactly ℤ[φ] |
| Dense golden constants (Prop) | Closure of ℤ[φ] in chosen real embedding = ℝ |
| Irreducibility obstruction (Prop) | If every shift P − c is irreducible in both variables, P not scalar-definable |
| Separable sums (Cor) | `x^m + y`, `x + y^m`, `x² + y²` not scalar-definable over ℤ[φ] |
| Incompleteness / completion (Thm) | Scalar layer lacks mixed addition; pairs + Tr define 0, 1, −x, x+y, x−y, xy |
| Golden projections (Prop) | Tr(Φ)=1, Nm(Φ)=−1, Sp(Φ)=√5 |
| Quadratic-unit template (Prop) | Shifted cores B_k extend to other quadratic units with same trace/norm pattern |

**Slogan:** *Multiplication in the scalar core; addition as trace from a conjugate shadow.*

---

### 2. `02_quotients_without_division_phi_native.tex` — *Quotients Without Division*

**One-line summary:** Once ℤ[φ] gives real density without division, classical division decomposes into distinct roles—unit action, rate localization, relations, approximation, factor projection, normalization—each handled in its own layer.

**Question addressed:** If density no longer requires division, what remains of division?

**Summary:** Division is treated as an overloaded bundle, not one primitive. Division by φ is scalar-native unit action `C_φ(x) = B(φ,x)`. Exact rationals like 1/2 are not in ℤ[φ] but are approximable. Fixed `x/n` is a rate class or averaging problem (diagonal trace sections), not a variable reciprocal. Variable reciprocals become local polynomial approximation problems on compact intervals away from zero. Algebraic quotients become relations `u = qv`. Derivative quotients become **factor projections** from divisibility in a polynomial ring. The central worked example: golden difference Δ_φ f(x) = f(x) − f(qx) factors as (∂_φ f)·Δ_φ x for f ∈ ℤ[φ][x], yielding q-integer coefficients [n]_φ without introducing a quotient operator. Formal overlap with Jackson q-calculus at q = φ⁻¹ is noted but secondary to the architectural point.

**Main results:**

| Result | Statement |
|--------|-----------|
| Golden contraction (Prop) | `C_φ(x) = B(φ,x) = (φ−1)x = x/φ` — scalar polynomial, not reciprocal |
| Rate / averaging (Prop) | Rates `[x:n]` ↔ localization; `Avg_n` ↔ section of multiplication by n |
| Rational approximation (Prop) | Every real r approximable by c ∈ ℤ[φ] |
| Reciprocal approximation (Prop) | On `[a,b]` with 0 < a, ∃ P ∈ ℤ[φ][x] uniformly approximating 1/x |
| Quotient relation (Def) | `Quot(u,v;q) ⟺ u = qv` |
| Factor projection (Def) | `Fact_d(h) = g` when h = gd uniquely (injective ×d) |
| Golden factor derivative (Thm) | ∀ f ∈ ℤ[φ][x], ∃ unique ∂_φ f with Δ_φ f = (∂_φ f) Δ_φ x |
| Monomial rule (Cor) | ∂_φ x^n = [n]_φ x^(n−1) |
| Twisted product rule (Prop) | ∂_φ(fg) = (∂_φ f)g + f(qx)(∂_φ g) |

**Slogan:** *Division is not one operation—it splits into roles.*

---

### 3. `03_shadow_trigonometry_phi_native.tex` — *Shadow Trigonometry*

**One-line summary:** Trigonometry begins with norm-one phase objects and unnormalized trace/spread projections; angles, normalized sin/cos, and π are later coordinatizations.

**Question addressed:** What remains of trigonometry if we do not start from angles, normalized sine/cosine, or division-based tangent?

**Summary:** The primitive object is a phase unit U with involution U^σ = U⁻¹ and Nm(U) = 1. Native projections are T(U) = U + U⁻¹ and S(U) = U − U⁻¹. Classical cos/sin appear only after choosing a complex embedding and dividing by 2 and 2i (rate/averaging layer). Trace orbits T_n satisfy Chebyshev-type recurrences; multiplication of phases yields shadow addition formulas. Inverse cosine is replaced by the **phase lift** relation U² − tU + 1 = 0. The **golden circular bridge**: if U + U⁻¹ = φ, then U satisfies the 10th cyclotomic polynomial, U⁵ = −1, U¹⁰ = 1 (exact order 10 in an integral domain). This reverses 2 cos(π/5) = φ: φ is the visible scalar shadow of hidden pentagonal phase. Tangent is a relation, not division. π is deferred to analytic completion.

**Main results:**

| Result | Statement |
|--------|-----------|
| Phase object (Def) | Unit U with U^σ = U⁻¹ ⟺ Nm(U) = 1 |
| Fixed / anti-fixed (Prop) | T(U)^σ = T(U); S(U)^σ = −S(U) |
| Chord norm (Prop) | Nm(U − 1) = 2 − T(U) |
| Trace recurrence (Prop) | T_{n+1} = T_1 T_n − T_{n−1}, T_0 = 2 |
| Shadow addition formulas (Prop) | T_m T_n = T_{m+n} + T_{m−n}; analogous for S |
| Phase lift (Def) | Adjoin U with U + U⁻¹ = t ⟺ U² − tU + 1 = 0 |
| Golden pentagonal phase (Thm) | If U + U⁻¹ = φ in an integral domain, then U¹⁰ = 1, order 10 |
| Spread-square (Prop) | S(U)² = T(U)² − 4 (link to signature layer) |

**Slogan:** *Phase first, trace second, angle later.*

---

### 4. `04_signatures_before_roots_phi_native.tex` — *Signatures Before Roots*

**One-line summary:** Square roots are not primitive scalar functions; they are spread lifts from visible trace and norm data, with real signature (sign of Δ) and algebraic square-class selecting geometry and extensions.

**Question addressed:** What if a square root is not a primitive function but the shadow of a missing spread component?

**Summary:** For a quadratic pair ⟨r₁ \| r₂⟩ with S = Tr, P = Nm, the spread D = r₁ − r₂ satisfies **Sp² = Tr² − 4 Nm** (classical discriminant identity, reinterpreted as shadow hierarchy). A **spread lift** finds D with D² = S² − 4P. Real sign of Δ classifies lifts as circular (Δ < 0), null (Δ = 0), or hyperbolic (Δ > 0). Algebraic square-class in K×/(K×)² decides whether D already lives in K or requires an extension. Recovering slot coordinates uses fixed averaging by 2 (rate layer). The golden ratio's **double life**: as phase trace (φ, 1) → Δ = φ − 3 < 0 → pentagonal circle; as scalar pair ⟨φ \| ψ⟩ → (1, −1) → Δ = 5 → hyperbolic geometry with Sp = √5. Norm forms come in signatures: golden scalar norm a² + ab − b² is indefinite (Fibonacci hyperbola); Gaussian norm a² + b² is positive-definite (Pythagoras as length lift). Fibonacci integers appear as coordinates of units ±φ^k on the unit hyperbola.

**Main results:**

| Result | Statement |
|--------|-----------|
| Spread–discriminant (Prop) | Sp(R)² = Tr(R)² − 4 Nm(R) |
| Spread lift (Def) | Lift relation: D² = S² − 4P |
| Skew unit as elliptic spread (Prop) | For (S,P)=(0,1), i = D/2 satisfies i² = −1, i^σ = −i |
| Two golden anchors | Phase (φ,1): Δ < 0 circular; pair ⟨φ\|ψ⟩: Δ = 5 > 0 hyperbolic |
| Length lift (Def) | c² = Nm(z) in positive-definite norm layers |
| Fibonacci hyperbola (Thm) | Integral points on a² + ab − b² = ±1 are coordinates of ±φ^k |

**Slogan:** *Signature first, spread second, root later.* — *The radical is a shadow asking to be lifted.*

---

### 5. `05_factors_before_quotients_phi_calculus.tex` — *Factors Before Quotients*

**One-line summary:** Calculus begins with divisibility, not division: the golden derivative is a factor projection along fixed contraction scale φ⁻¹, yielding bounded weights, a non-entire exponential, and integration obstructions solved by rate localization.

**Question addressed:** What remains of calculus if differentiation is not introduced as a quotient (and limit), but as factor extraction from a golden difference?

**Summary:** Paper 2 previewed the golden factor derivative as a worked example; this paper develops full polynomial golden calculus. Displacement comes from native unit action C_φ(x) = φ⁻¹x (scalar layer). Golden difference Δ_φ f(x) = f(x) − f(φ⁻¹x) is divisible by Δ_φ x = x − φ⁻¹x for f ∈ ℤ[φ][x]; golden derivative ∂_φ f is the unique factor in the divisibility relation Δ_φ f = (∂_φ f) Δ_φ x—not a pointwise quotient (avoiding 0/0 at the fixed point x = 0). Formally this is Jackson q-calculus at q = φ⁻¹, but the φ-native route and golden specialization matter: weights collapse to [n]_φ = φ² − φ^(2−n), bounded and converging to φ² at the chosen real embedding (unbounded under the conjugate embedding). Product rule is twisted q-Leibniz with contraction twist f(x) ↦ f(φ⁻¹x). Chain rule is two-stage factorization via polynomial divided differences; ordinary chain rule holds only for inner maps g(x) = cx. Golden exponential E_φ(x) = Σ x^n/[n]_φ! has radius φ² = φ + 1—not entire. Integration of x^n requires rate localization at [n+1]_φ; only [1]_φ and [2]_φ are units in ℤ[φ]. Fixed scale (self-similar), not infinitesimal limit.

**Main results:**

| Result | Statement |
|--------|-----------|
| Golden derivative (Thm) | ∀ f ∈ ℤ[φ][x], ∃ unique ∂_φ f with f(x) − f(φ⁻¹x) = (∂_φ f)(x)(x − φ⁻¹x) |
| Monomial rule (Prop) | ∂_φ x^n = [n]_φ x^(n−1) |
| Weight collapse (Prop) | [n]_φ = φ² − φ^(2−n); increasing to φ² at chosen real embedding |
| Twisted product rule (Prop) | ∂_φ(fg) = (∂_φ f)g + f(φ⁻¹x)(∂_φ g) |
| Chain factorization (Prop) | ∂_φ(f∘g) = Diff_f(g(x), g(φ⁻¹x)) · (∂_φ g)(x) |
| Clean chain rule (Prop) | g(φ⁻¹x) = φ⁻¹ g(x) iff g(x) = cx for some c ∈ ℤ[φ] |
| Golden exponential radius (Thm) | E_φ(x) = Σ x^n/[n]_φ! has radius of convergence φ²; not entire |
| Weight units (Prop) | [n]_φ is a unit in ℤ[φ] iff n = 1 or n = 2 |
| Integration | Antiderivative of x^n is rate `[x^(n+1) : [n+1]_φ]`; needs localization for n ≥ 2 |

**Slogan:** *Calculus begins not with division, but with divisibility.* — *The derivative is a factor shadow.*

---

### 6. `06_phase_before_frequencies_golden_decagonal_fourier.tex` — *Phase Before Frequencies*

**One-line summary:** The ℤ/10ℤ DFT is not new; its golden placement uses decagonal phase U with trace φ, a phase-valued spectrum in R_φ = ℤ[φ][U]/(U²−φU+1), rate-native inversion by 10, and 2+4 spectral conjugation decomposition.

**Question addressed:** How does finite Fourier analysis sit in the shadow layer architecture—and what is genuinely golden versus standard cyclic group theory?

**Summary:** Orthogonality, inversion, and the convolution theorem for N=10 are classical (ℤ/10ℤ character theory). The golden-specific input is the cyclotomic coincidence Q(ζ₁₀)⁺ = Q(√5) = Q(φ) and especially ζ₁₀ + ζ₁₀⁻¹ = φ (decagonal, not pentagonal: ζ₅ + ζ₅⁻¹ = φ⁻¹). With U = ζ₁₀, the phase lift U² − φU + 1 = 0 defines the rank-two **golden phase ring** R_φ. Signals f ∈ ℤ[φ]¹⁰ are ten-slot tuples; forward transform f̂_m = Σ f_k U^{km} ∈ R_φ (phase-valued, not generally scalar). Reduction rule U² = φU − 1 governs spectral multiplication—the golden twist. Inverse reconstruction f_k = (1/10)Σ_m f̂_m U^{-km} requires fixed denominator 10 → **rate layer** (1/10 ∉ ℤ[φ]). Convolution diagonalizes pointwise in R_φ with ordinary theorem statement. Phase involution σ(U) = U⁻¹ = φ − U gives σ(f̂_m) = f̂_{10−m}; spectrum decomposes as **2 scalar modes** (m=0,5) + **4 phase-conjugate pairs** (1,9),(2,8),(3,7),(4,6). Trace/spread of spectral components give unnormalized cos/sin shadows; division by 2 is rate-layer. Connects Paper 3's decagonal clock (U¹⁰=1) to finite harmonic analysis.

**Main results:**

| Result | Statement |
|--------|-----------|
| Golden cyclotomic layers (Prop) | Q(ζ_n)⁺ = Q(√5) iff n = 5 or 10; only n=10 has primitive phase trace φ |
| Phase ring (Def) | R_φ = ℤ[φ][U]/(U²−φU+1); normal form A+BU; σ(U) = φ−U |
| Phase-ring multiplication (Prop) | (A+BU)(C+DU) = (AC−BD) + (AD+BC+φBD)U |
| Decagonal Fourier transform (Def) | f̂_m = Σ_{k=0}^9 f_k U^{km} for f ∈ ℤ[φ]¹⁰ |
| Phase orthogonality (Prop) | Σ_k U^{kj} = 10 if j≡0 (mod 10), else 0 |
| Inverse transform | f_k = [Σ_m f̂_m U^{-km} : 10] (rate-native) |
| Convolution theorem (Thm) | widehat{f*g}_m = f̂_m ĝ_m in R_φ |
| Spectral conjugation (Thm) | σ(f̂_m) = f̂_{10−m}; 2 scalar + 4 conjugate pairs = 10 DOF |
| Matrix form | F^σ F = 10I; F⁻¹ = [F^σ : 10] in rate layer |

**Slogan:** *Phase before frequencies.* — *Convolution is ordinary; phase multiplication carries the golden twist.*

---

## Program arc (how the six papers connect)

```
EML (leaf 1 + eml)
        │
        ▼  "what if leaf = φ?"
Paper 1: scalar B-grammar + trace completion
        │
        ├──► Paper 2: division splits into roles
        │         │
        │         └──► factor projection (preview)
        │
        ├──► Paper 3: phase orbits, golden circular bridge
        │         │
        │         └──► Paper 6: decagonal Fourier (phase-valued spectrum)
        │
        ├──► Paper 4: spread lifts, discriminant signatures
        │
        └──► Paper 5: golden difference calculus
                  (full factor layer; integrates Papers 1–2, rate layer)
```

Each step applies the same move to a different classical operation:

| Step | Classical primitive | Shadow relocation |
|------|----------------------|-------------------|
| 1 | Addition | Trace projection from pairs |
| 2 | Division | Unit action, rates, relations, factor projection |
| 3 | Trigonometry | Phase objects, trace/spread projections |
| 4 | Roots / radicals | Spread lifts from (Tr, Nm) |
| 5 | Calculus / derivative | Golden difference + factor projection; fixed contraction scale |
| 6 | Finite Fourier / DFT | Decagonal phase U; spectrum in R_φ; inverse via rate /10 |

---

## Related work

- A. Odrzywołek, *All elementary functions from a single binary operator*, [arXiv:2603.21852](https://arxiv.org/abs/2603.21852) (2026)
- K. Conrad, [Trace and Norm](https://kconrad.math.uconn.edu/blurbs/galoistheory/tracenorm.pdf) (expository notes)
- F. H. Jackson, q-calculus (formal overlap at q = φ⁻¹ in Papers 2 and 5)
- V. Kac & P. Cheung, *Quantum Calculus* (q-calculus references in Paper 5)
- L. C. Washington, *Introduction to Cyclotomic Fields* (phase / cyclotomic material in Papers 3–4, 6)
- A. Terras, *Fourier Analysis on Finite Groups and Applications* (Paper 6)
- J.-P. Serre, *Linear Representations of Finite Groups* (Paper 6)

---

## Citation

If referencing the series:

```bibtex
@misc{santos2026goldenshadow,
  author       = {Vinicius Santos},
  title        = {Golden Shadow Algebra: A $\varphi$-Native Manuscript Series},
  year         = {2026},
  note         = {Exploratory drafts},
  howpublished = {\url{https://github.com/vfssantos/golden-algebra}}
}
```

Individual papers can be cited by filename and title as listed in the index above.
