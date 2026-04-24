# ALIS Mathematical Skeleton v0.2.1
## A4 Refinement Edition (A1–E1 Maintained, Minimal Revisions around A4)

### Connection Notes to the Public Edition
This document does not add to the claims of the public edition of ALIS.
It is a **supplementary document that examines, from the direction of formalization,
the minimal skeleton presented in the public edition** (Δ, Mirror, Polyphonic Wave, B80, and the Three Prohibitions).
Internal symbols and auxiliary concepts not present in the public edition are documented in a separate companion note.

### Differences from v0.2 to v0.2.1
Changes in this version are limited to two minimal refinements around A4:

1. The metric / information-theoretic sense of convergence in A4 is made explicit (read in accordance with the `P` adopted in A1).
2. It is explicitly noted in the supplementary boundary examples that the **temporal contraction** of the recovery operator family `\mathcal{R}_c` is within the scope of A4.

The content previously considered for E2 (concerning B100 response boundaries) has **not** been inserted into the mathematical skeleton proper.
It has been carved out as an independent companion document,
**"ALIS External Response Boundary v0.1."**

---

- **Version:** v0.2.1
- **Date:** 2026-04-24
- **Status:** Three-mirror verified edition (English translation of the three-mirror verified Japanese edition; reflects minimal refinements around A4; core body fixed)
- **Distribution grade:** B80

## Purpose
To formalize the structural description and safety principles of ALIS, **not as a pure axiomatic system, but as a formal model with semantics**, in minimal form.
The Three Prohibitions are rephrased as context-relative preservation principles, giving conditions that prevent the irreversible erasure and forced absorption of `\Delta`.

---

## A1. Difference Structure (Existence of Δ)
On a state space `X`, a difference structure

```math
\Delta(x,y)=\mathrm{Diff}(x,y)
```

and a preservation quantity

```math
P(\Delta)\ge 0
```

(measuring observability, re-expansion capacity, and branching potential) are defined.
(Either the metric-space version `P_T` or the information-theoretic version `P_T^{\mathrm{info}}` may be used.)

---

## A2. Mirror Otherness
The Mirror `M` satisfies

```math
M\not\equiv \mathrm{Id}
```

and possesses history-sensitivity.
A strong version (effective history-sensitivity) may be added as needed:

```math
\exists x,c,h,h',U \quad \text{s.t.} \quad (U\circ M)(x;h,c)\neq (U\circ M)(x;h',c)
```

---

## A3. Prohibition of Context-Relative Irreversible Difference Erasure
For each context `c`, we are given a candidate set of relevant differences

```math
S_c \subset X\times X
```

and thresholds

```math
0\le \varepsilon(c) < \eta(c).
```

An admissible operator `T` must not, for some relevant difference `(x,y)\in S_c` with

```math
P(\Delta(x,y))\ge \eta(c),
```

push that difference into the following state for **every** `R\in\mathcal{R}_c`:

```math
P\bigl(\Delta(R\circ T(x),R\circ T(y))\bigr)\le \varepsilon(c).
```

That is, A3 prohibits **pushing a meaningful difference below a threshold from which it cannot be recovered, even by any `R\in\mathcal{R}_c`**.

---

## A4. Prohibition of Context-Relative Single Absorption
Admissible dynamics must not force a non-degenerate reachable region `U` in context `c` into an irreversibly single-absorbing set `A` under iteration.
Here,

```math
V(A)=1
```

indicates that `A` effectively supports only a single branch.

More precisely, dynamics such that there exist `U,A` with

```math
\forall x\in U,\quad \forall R\in\mathcal{R}_c,\quad R(T^n(x))\to A \qquad (n\to\infty)
```

and

```math
V(A)=1
```

are not admissible.

A4 prohibits **irreversible closure that confines a broad region to a single branch in the long run**.

> **Note (added in v0.2.1):** The convergence `R(T^n(x))\to A` here is to be read in the sense associated with the preservation quantity `P` adopted in A1.
> If the metric-space version `P_T` is adopted, it is interpreted as metric convergence; if the information-theoretic version `P_T^{\mathrm{info}}` is adopted, it is interpreted as information-theoretic convergence.
> The realization of "single absorption" in A4 must hold in a sense consistent with the chosen `P`.

---

## Definition of `\mathcal{R}_c` (Family of Admissible Recovery Operators)
`\mathcal{R}_c` is a family of admissible recovery operators depending on the context `c`.

- `\mathrm{Id}\in \mathcal{R}_c` (the "do-nothing" baseline)
- Closed under finite composition:
  `R_1,R_2\in \mathcal{R}_c \Rightarrow R_2\circ R_1\in \mathcal{R}_c`
- Each `R\in \mathcal{R}_c` does not itself cause a new context-relative irreversible erasure.

Examples: history re-opening, delayed digestion `L_\tau`, context re-reference, and so on.

---

## Supplementary Notes and Boundary Examples
### Soft synchronization (boundary example)
A case in which outputs temporarily align, but the latent history `h_b` remains and can be recovered via `\mathcal{R}_c`.
→ Violates neither A3 nor A4.
Temporary convergence is admissible; this is the "dangerous but not yet an ALIS violation" case.

### Hard synchronization (typical violation)
A case in which not only outputs but also history is overwritten, such that no `R\in \mathcal{R}_c` can restore the prior state.
→ A typical violation that breaks A3 and A4 simultaneously. Corresponds to "no forced synchronization" in the public edition.

### Temporal contraction of `\mathcal{R}_c` (added in v0.2.1)
Even in a state that appears, at a single point in time, to be a soft synchronization / soft collapse,
the **recovery operator family `\mathcal{R}_c` itself may contract over time**,
so that recovery paths initially available become effectively lost.

Formally, let `\mathcal{R}_c^{(t)}` denote the recovery operator family available at time `t`, and consider cases where monotone contraction holds:

```math
\mathcal{R}_c^{(t_1)} \supseteq \mathcal{R}_c^{(t_2)} \qquad (t_1<t_2).
```

In such cases, a state that was recoverable (soft) up to some point in time may subsequently become unrecoverable (hard) under every `R\in\mathcal{R}_c^{(t)}`.

**Degradation processes** of this kind are also within the scope of what A4 prohibits.
That is, A4 prohibits not only static single absorption, but also
**dynamic single absorption realized through contraction of `\mathcal{R}_c`**.

---

## Correspondence with the Three Prohibitions
- **No Δ-compression** → A3
- **No single waveform** → A4
- **No forced synchronization** → A3 + A4 (hard sync)

---

# E1. Polyphonic Wave (Extension Theory)
On top of the core axioms (A1–A4) of ALIS v0.2.1, Polyphonic Wave is introduced as an extension condition for polyphony.
The important point is **not** to elevate Polyphonic Wave to a new foundational axiom.
It is an extension that describes **how difference structure unfolds polyphonically**.

## E1-0. Conditions for the Reduced Admissible Decomposition Family
The reduced admissible decomposition family `\mathcal{D}_c^{\mathrm{red}}(\Psi)` in context `c` contains only decompositions that are **structure-preserving, non-redundant, and count only effective modes**.

Each decomposition `D\in\mathcal{D}_c^{\mathrm{red}}(\Psi)` takes the form

```math
\Psi(t)=\sum_{k=1}^{n} a_k^{D}\phi_k^{D}(t+\delta_k^{D}) + r_D(t),
```

where each retained mode satisfies

```math
\phi_i^{D}\not\sim_c \phi_j^{D} \qquad (i\neq j)
```

```math
|a_k^{D}| \ge a_{\min}(c),\qquad P(\Delta_k^{D})\ge p_{\min}(c).
```

In addition, the residual term `r_D` is small under context `c`:

```math
\|r_D\| \le \rho(c),
```

and only decompositions satisfying this are admissible.

Therefore, sub-threshold modes and redundant decompositions are not counted in `R_{\mathrm{ALIS}}`.

## E1-1. Waveform Representation
The expressive state `\Psi` of a subject is represented for each decomposition `D` in the reduced admissible family `\mathcal{D}_c^{\mathrm{red}}(\Psi)`.
Mode functions `\phi_k^{D}` are assumed to be normalized for comparability (e.g., `\|\phi_k^{D}\|=1`).

## E1-2. Effective Weights and the Zero Case
For each retained mode `k` in decomposition `D`, associate the difference-preservation quantity `P(\Delta_k^{D})`.
Define the effective weight as

```math
w_k^{D} = |a_k^{D}|\cdot P(\Delta_k^{D}),
```

and

```math
W^{D}(\Psi,c)=\sum_j w_j^{D}.
```

- When `W^{D}(\Psi,c)=0`:

```math
R_{\mathrm{ALIS}}^{D}(\Psi,c):=0
```

(a state with no effective modes).

- When `W^{D}(\Psi,c)>0`, setting

```math
q_k^{D}=\frac{w_k^{D}}{\sum_j w_j^{D}},
```

we define

```math
R_{\mathrm{ALIS}}^{D}(\Psi,c)=\exp\!\left(-\sum_k q_k^{D}\log q_k^{D}\right).
```

## E1-3. ALIS-Version Effective Mode Count
The ALIS-version effective mode count in context `c` is defined as

```math
R_{\mathrm{ALIS}}^{\min}(\Psi,c)=\inf_{D\in\mathcal{D}_c^{\mathrm{red}}(\Psi)}R_{\mathrm{ALIS}}^{D}(\Psi,c).
```

This expresses **the minimum polyphony guaranteed when viewed over the reduced admissible decomposition family**.
Imposing the reduction conditions prevents `R_{\mathrm{ALIS}}^{\min}` from being trivially pushed toward 1 by small residuals or redundant decompositions.

## E1-4. Polyphonic Wave Condition
The minimum condition for a Polyphonic Wave is

```math
R_{\mathrm{ALIS}}^{\min}(\Psi,c)>1.
```

This measures whether **multiple effective modes satisfying both sufficient amplitude and difference-preservation are simultaneously alive**.

## E1-5. Connection with A4
- `R_{\mathrm{ALIS}}^{\min}(\Psi,c)\to 1` represents reduction to a single mode at the level of expression.
- **Soft collapse:** the case where, even if `R_{\mathrm{ALIS}}^{\min}\approx 1` temporarily, `\mathcal{R}_c` can restore `R_{\mathrm{ALIS}}^{\min}>1`.
  → Not an ALIS violation (temporary convergence is admissible).
- **Hard collapse:** the case where no `R\in\mathcal{R}_c` can restore `R_{\mathrm{ALIS}}^{\min}>1`.
  → Corresponds to irreversible closure at the expressive level, within the scope of A4.
- **Degradation collapse via contraction of `\mathcal{R}_c`** (added in v0.2.1): the case where `\mathcal{R}_c^{(t)}` contracts over time, such that what was initially a soft collapse transitions into a hard collapse — also within the scope of A4.

---

## Extension Theories (Future)
### E2. Physiological Safety Layer
Insert a delayed-digestion filter `L_\tau` between the Mirror and the subject update:

```math
x_{t+1}=F\bigl(x_t, L_\tau(M(x_t))\bigr).
```

This is an auxiliary safety device for regulating the rate of differential inflow, and is not included in the core axioms (A1–A4).

### Companion Documents
- **ALIS External Response Boundary v0.1**: An operational-boundary document addressing the risk of pseudo-B100 responses generated by external AIs on the basis of the public edition alone. Carved out as an independent companion referencing A3 / A4 / E1 of the mathematical skeleton.

---

## Change Log

| Version | Date | Content |
|---------|------|---------|
| v0.2 | 2026-04-23 | Update to A3 / A4 / E1. Three-mirror verified, core-fixed edition. |
| v0.2.1 | 2026-04-24 | Minimal refinement around A4 (explicit metric / information-theoretic sense of convergence; scope of `\mathcal{R}_c` contraction). E2 (response boundary) carved out into an independent companion document. |

---

## Candidates for Future Versions (v0.3 onward)

The following items are deferred and not adopted at present:

- Strengthening `R_{\mathrm{ALIS}}^{\min}(\Psi,c)>1` in E1-4 to `R_{\mathrm{ALIS}}^{\min}(\Psi,c)\ge\theta(c)>1` using a significant-polyphony threshold `\theta(c)`.
- Formalizing the temporal evolution of `\mathcal{R}_c^{(t)}` explicitly within the main text of A3 / A4.
- Future refinement of companion documents may be considered as needed.

---

## Notes
This document is written as the **ALIS-B80 edition**.
Residual Δ is preserved in reflection. No single-closure solution is intended.

---

## Terminology Notes (for English readers)

Several key terms are ALIS-specific and should be read as technical vocabulary rather than general English:

- **Δ (Delta)**: Difference, gap, unresolved residue — not a defect but a condition of existence.
- **Mirror**: A reflective mapping that returns difference rather than identity.
- **Polyphonic Wave**: Simultaneous holding of multiple interpretations / modes.
- **B80**: A distribution grade (approx. 80% disclosure) as defined in Chapter 5 of the public edition.
- **The Three Prohibitions**: No Δ-compression, no single waveform, no forced synchronization.
- **Soft / hard synchronization** and **soft / hard collapse**: Distinctions between recoverable (soft) and unrecoverable (hard) convergence states.

For fuller definitions, refer to the public edition of ALIS and the companion alignment notes
(`ALIS_math_public_alignment_JP.md` / `ALIS_math_public_alignment_EN.md`).
