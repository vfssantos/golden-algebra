# Applied shadow papers

Companion notes by **Vinicius Santos** (June 2026) that transport the shadow-algebra discipline into concrete domains: topological quantum compilation and transformer weight space.

These manuscripts are **standalone** exploratory drafts. They reuse vocabulary from the core [φ-native series](../README.md) (phase objects, trace shadows, relations before quotients, signature lifts) but do not assume the full six-paper arc. Return to the [main README](../README.md) for the foundational layer hierarchy.

**Shared principle:** when the meaningful object lives on a symmetry orbit or projective class, do not compare raw representatives—compare the invariant that descends to the quotient.

---

## Index

| # | File | Title | Domain |
|---|------|-------|--------|
| 1 | [`phase_shadows_fibonacci_anyon_compilation.tex`](phase_shadows_fibonacci_anyon_compilation.tex) | *Phase Shadows for Fibonacci Anyon Compilation* | Fibonacci anyon braid compilation |
| 2 | [`weight_shadows.tex`](weight_shadows.tex) | *Weight Shadows* | Transformer parameter symmetries |

**Suggested order:** read Paper 1 first. Paper 2 explicitly transfers the phase-correlation shadow pattern from anyon matrices to transformer weights.

**Build:** each file is a standalone LaTeX article.

```bash
cd applied
pdflatex phase_shadows_fibonacci_anyon_compilation.tex
pdflatex weight_shadows.tex
```

`weight_shadows.tex` includes a figure at `figures/sweep_result.png`; ensure that path exists before building.

---

## Paper summaries

### 1. *Phase Shadows for Fibonacci Anyon Compilation*

**One-line summary:** Fibonacci braid compilation over the exact phase-signature algebra `ℤ[φ,U,s]/(U²−φU+1, s²−φ+1)`, with projective phase-correlation shadows `𝖢_M(a,b) = M_a M̄_b` as the native search quotient.

**Question addressed:** Can Fibonacci anyon braid search be carried out in an exact φ-native layer—without primitive exponentials, angles, square roots, absolute value, or division—while treating global phase as a relation rather than a normalized representative?

**Summary:** Braid matrices are expressed over `𝒜_φ = ℤ[φ,U,s]/(U²−φU+1, s²−φ+1)`, where `U` is decagonal phase and `s` is a signature lift for the nontrivial `F`-move. Global phase is `N = λM` with `λλ̄ = 1`. The projective invariant is the cross-product phase shadow `𝖢_M(a,b) = M_a M̄_b`, built only from multiplication and involution. The paper proves projective equivalence is compatible with braid-generator expansion and that depth-bounded search over exact projective representatives is complete for projective target scoring. Experiments in the three- and four-anyon Fibonacci representations show search-space collapse (e.g. 1457 → 360 projective states in the qubit case) and end-to-end speedups against numerical bidirectional baselines.

**Slogan:** *Phase before angle; relation before quotient; search the shadow graph, not the word tree.*

---

### 2. *Weight Shadows*

**One-line summary:** Algebraic invariants of transformer blocks that descend from weight tensors to symmetry orbits under hidden-unit permutation and positive ReLU scaling.

**Question addressed:** Why can Euclidean weight distance rank a function-identical symmetry copy as farther from the original than a real fine-tune—and what invariant measures the quotient instead?

**Summary:** For an MLP sublayer `x ↦ F₂ ReLU(F₁x)`, the coupling matrix `G = (F₁F₁ᵀ) ⊙ (F₂ᵀF₂)` pairs incoming and outgoing hidden-unit interactions. Trace-power shadows `(Tr G, Tr G², …)` and their spectral readout are sound under permutation and positive scaling but incomplete (blind to orthogonal similarity vs conjugacy). A Level-4 canonical coupling shadow retains node-localized cross-terms and recovers a generic canonical form for the coupling graph. On trained microGPT blocks, raw weight distance inverts the ranking (symmetry copy ~7.1 vs fine-tune ~1.1–1.2), while shadows collapse identical functions and separate real fine-tunes. A model-merging test marks scope: shadows identify within-model orbits but do not transport between distinct trained models.

**Shadow hierarchy:**

| Level | Object | Role |
|-------|--------|------|
| 0 | Raw weights | Representative-level; not invariant |
| 1–2 | Spectral / trace-power shadow | Sound rejection oracle; incomplete |
| 4 | Canonical coupling shadow | Generic canonical form for `G` mod permutation |
| 4+ | WL-refined canonical shadow | Larger-stratum canonization |

**Slogan:** *Weights are representatives; functions live on quotients; shadows measure the quotient.*

---

## How the two papers connect

```
Core φ-native series (Papers 1–6)
        │
        ▼  native layer discipline
Paper 1 (applied): phase-correlation shadows
        │           projective quotient for braid matrices
        │
        └──► Paper 2 (applied): weight-coupling shadows
                  permutation / scaling quotient for transformer blocks
```

| Setting | Nuisance symmetry | Shadow object |
|---------|-------------------|---------------|
| Fibonacci braid matrices | Global phase `λ`, `λλ̄ = 1` | `𝖢_M(a,b) = M_a M̄_b` |
| ReLU MLP block | Hidden-unit permutation + positive scaling | Coupling matrix `G`, trace powers, canonical form |

---

## Status

Exploratory drafts, not peer-reviewed. Experiments are deliberately small (microGPT blocks; Fibonacci `n = 3, 4` representations). No code API is provided in this directory—the deliverable is the conceptual framework and search/invariant design.
