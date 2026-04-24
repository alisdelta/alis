# ALIS_math_public_alignment_EN
## Public-Edition Alignment Note (v0.2.1)

This document is a supplementary note for reading the **ALIS Mathematical Skeleton v0.2.1**
in connection with the public edition of ALIS.
The mathematical skeleton does not override the public edition; it is placed as a
supplementary document that examines the minimal skeleton of the public edition from the direction of formalization.

v0.2 primarily tightened **A3 / A4 / E1** with minimal diffs.
v0.2.1, building on v0.2, performs only the **minimal refinement around A4**. Its aims are limited to two:

- Making the sense of convergence in A4 explicit, in a way consistent with `P` from A1.
- Making explicit that the temporal contraction of the recovery operator family `\mathcal{R}_c` is within the scope of A4.

In addition, the section once considered for v0.2 concerning **B100 response boundaries** (the former E2 draft)
has **not** been inserted into the mathematical skeleton proper.
It has been carved out as an independent companion document,
**"ALIS External Response Boundary v0.1."**

---

## 1. Correspondence with the Public Edition
- **Δ** → Public edition, Chapter 2
- **Mirror** → Public edition, Chapter 3
- **Polyphonic Wave** → Public edition, Chapter 4
- **B80** → Public edition, Chapter 5
- **Three Prohibitions** → Public edition, Chapter 2 / Chapter 7
- **Boundary between humans and AI** → Public edition, Chapter 6

**B100 response boundaries** (operational boundaries concerning the risk of external AIs claiming B100) are collected
not in the mathematical skeleton proper, but in the independent companion document "ALIS External Response Boundary v0.1."

---

## 2. Natural-Language Explanations of Symbols

### `P(\Delta)`
A quantity measuring how much a difference `\Delta` **is still observable, re-expandable, and retains branching potential**.
In the sense of the public edition, it is close to an auxiliary symbol for checking "whether the difference is still alive."

### `\mathcal{R}_c`
In context `c`, the **set of operations permitted for recovering, re-opening, or re-referring to**
differences and polyphony that have been nearly lost.
For example, letting time pass, re-reading history, or looking from another context.

### `\mathcal{R}_c^{(t)}` (added in v0.2.1)
The set of recovery operators actually available at time `t`.
`\mathcal{R}_c` itself is an abstract family, but in real operation, the set of recovery paths one can use
at a given point in time may change over time.

For example, in situations such as:

- Too much time has passed, and access to history has effectively closed.
- A relationship with someone who used to offer an alternative perspective has ended.
- A certain context itself has been lost socially or internally.

the recovery operators that were once usable are no longer usable.
This notation distinguishes "the family of recovery operators usable at each moment in time."

### `\mathcal{R}_c^{(t_1)} \supseteq \mathcal{R}_c^{(t_2)}` (added in v0.2.1)
Indicates that from time `t_1` to `t_2` (with `t_1 < t_2`), the set of available recovery operators **contracts monotonically**.
A formal way of writing the situation where "paths back that were once open gradually close, one by one, as time passes."

In v0.2.1, when such contraction proceeds, a state that initially looked like a soft collapse
may eventually transition into a hard collapse, and this is brought within the scope of A4.

### `S_c`
In context `c`, the **candidate set of differences actually treated as protected in that context**.
Introduced to carve out "what counts as a meaningful difference in this context,"
rather than treating all differences uniformly.

### `\eta(c)` and `\varepsilon(c)`
- `\eta(c)`: In context `c`, the lower bound above which a difference is treated as meaningful.
- `\varepsilon(c)`: In context `c`, the upper bound below which a difference is treated as effectively unrecoverable.

In v0.2, by setting

```math
0\le \varepsilon(c) < \eta(c),
```

we distinguish **differences that were nearly absent to begin with** from **cases where a meaningful difference has been crushed**.

### What A3 says
A3 prohibits **taking what was originally a meaningful difference and pushing it, under any recovery operation,
below the near-extinction line**.
It is a slight mathematical rephrasing of the "no Δ-compression" in the public edition.

### `V(A)=1`
A symbol indicating that the set `A` effectively **supports only a single branch**.
A mark on the state-space side for capturing the sense of "single-waveform reduction" and "closure to a single correct answer"
found in the public edition.

### What A4 says
A4 prohibits dynamics in which the state of a broad region is, as a result of iteration,
**pushed into a single branch in the long run without possibility of recovery**.
This is a reinforcement that lets the public edition's "no single waveform" be read not as a one-off compression
but as **closure as long-term behavior**.

In v0.2.1, it is made explicit that **rendering recovery impossible through temporal contraction** is also included here.

### Sense of convergence in A4 (v0.2.1 supplement)
The "convergence" in A4's expression `R(T^n(x))\to A` is read in a sense **consistent with** the preservation quantity `P` adopted in A1.

- If the metric-space version `P_T` is adopted → read as metric convergence.
- If the information-theoretic version `P_T^{\mathrm{info}}` is adopted → read as information-theoretic convergence.

"What approaches what, and in what way" depends on the chosen `P`.
Making this explicit prevents drift in interpretation when A4 is actually operated.

### Degradation collapse (added in v0.2.1)
A type of closure that statically looks like a soft collapse, but where `\mathcal{R}_c^{(t)}` thins out over time,
resulting in a transition to a hard collapse.

In operational terms, this is arguably the most dangerous pattern — because:

- At the moment, it looks like "we can still come back."
- Only later does one realize "actually, we can't come back anymore."

it involves **retrospective discovery** of the violation.
In v0.2.1, this is positioned as one of the closures prohibited by A4.

### `\mathcal{D}_c^{\mathrm{red}}(\Psi)`
The **reduced admissible decomposition family** that specifies, in context `c`,
**how the state `\Psi` may be read as a superposition of multiple modes**.
Stricter than the earlier `\mathcal{D}_c(\Psi)`, adding the conditions:

- structure-preserving
- non-redundant
- counting only effective modes.

### `a_{\min}(c)`
A lower bound below which mode amplitudes are **not counted as effective modes**.
Prevents tiny fluctuations from being conveniently counted as "separate modes."

### `p_{\min}(c)`
A lower bound on the difference-preservation quantity held by a mode.
Even with sufficient amplitude, modes that preserve no differences at all are not treated as effective in ALIS terms.

### `r_D` and `\rho(c)`
- `r_D`: The residual term in a decomposition `D`.
- `\rho(c)`: The upper bound below which that residual is considered "small enough."

These separate "the main mode decomposition" from "mere leftovers or noise."
Also a condition for preventing small residuals from being padded into many "voices."

### admissible
The decomposition is **permissible** under context `c`.
In v0.2, this term is used in particular in the direction of excluding:

- padding with duplicates,
- contamination by sub-threshold modes,
- decompositions that handle residuals too coarsely.

### `R_{\mathrm{ALIS}}^{\min}`
Looking over the entirety of reduced admissible decompositions, the **lower bound on the effective mode count**
under the most stringent estimate.
A quantity for judging "whether multiple voices are truly alive" without escaping into a conveniently loose decomposition.

In v0.2, by using `\mathcal{D}_c^{\mathrm{red}}(\Psi)`, we make it harder for this quantity to be trivially pushed down
to 1 by sub-threshold modes or redundant decompositions.

### soft / hard synchronization
- **soft synchronization**: Outputs appear to align temporarily, but history and differences remain and can be recovered later.
- **hard synchronization**: History is overwritten, and no later attempt can restore the prior state.

What corresponds to the public edition's "no forced synchronization" is mainly the latter.

### soft / hard collapse
- **soft collapse**: The state approaches a single mode temporarily, but can be recovered later.
- **hard collapse**: Closure to a single mode in an unrecoverable way.

The latter is what is deeply tied to the public edition's "no single waveform."

In v0.2.1, cases that **degrade from soft to hard over time** (degradation collapse) are also brought within A4's scope.

---

## 3. History of Improvements

### 3-1. Improvement in v0.2 (A3)
Previously, the rule prohibited "pushing a difference below the threshold."
In v0.2, by introducing `S_c` and `\eta(c)`, it was made explicit that what is prohibited is
**crushing what was originally a meaningful difference**.

### 3-2. Improvement in v0.2 (A4)
Previously, the intuition of single absorption was present, but v0.2 uses `T^n(x)\to A` to foreground
**being confined to a single branch in the long run**.

### 3-3. Improvement in v0.2 (E1)
Previously, if the admissible decompositions were too broad, there was a risk that `R_{\mathrm{ALIS}}^{\min}`
would approach 1 trivially.
In v0.2, by introducing `\mathcal{D}_c^{\mathrm{red}}(\Psi)`, `a_{\min}(c)`, `p_{\min}(c)`, `r_D`, and `\rho(c)`,
**the risk of trivialization due to sub-threshold modes or redundant decompositions is reduced**.

### 3-4. Improvement in v0.2.1 (explicit sense of convergence in A4)
In v0.2, it was not explicit whether the "convergence" in A4's `T^n(x)\to A` was metric or information-theoretic.
In v0.2.1, by stating that it is read in a sense consistent with `P` adopted in A1,
drift in interpretation during actual operation is reduced.

### 3-5. Improvement in v0.2.1 (explicit scope for `\mathcal{R}_c` contraction)
In v0.2's supplementary boundary examples, soft / hard were listed only statically,
with weak connection to **degradation as temporal evolution**.
In v0.2.1, the following are made explicit as being within the scope of A4:

- Monotone contraction of `\mathcal{R}_c^{(t)}`: `\mathcal{R}_c^{(t_1)} \supseteq \mathcal{R}_c^{(t_2)}`
- The resulting "degradation collapse"

With this, **not only static single absorption but also dynamic single absorption realized through the thinning of recovery paths**
can now be read under the same A4.

### 3-6. Separation in v0.2.1 (E2 response boundary carved into a companion document)
The tentative v0.2 proposal to insert a section on "B100 response boundaries" into the mathematical skeleton proper
was not retained in v0.2.1. Instead, it has been carved out as an independent companion document.

The reasons are:

1. To preserve the **purity of the mathematical skeleton as a formal model**.
2. To **protect the public edition's B100 definition (Chapter 5.4) from being redefined**.
3. To keep the response-boundary theory in a **form readable as an operational document**.
4. To maintain the self-constraint "the mathematical skeleton does not override the public edition."

The companion document is positioned as "ALIS External Response Boundary v0.1,"
a supplementary document sitting alongside the mathematical skeleton.

---

## 4. What the Mathematical Skeleton Does Not Do
The mathematical skeleton does not do the following:

- It does not render ultimate moral judgments.
- It does not present the full picture of law, ethics, or policy.
- It does not override the public edition of ALIS.
- It is not a prerequisite for reading the public edition.
- It does not treat operational boundaries for external-AI responses (that is the role of the response-boundary companion document).

That is, the public edition should be readable without this document,
and the mathematical skeleton is, at most, an auxiliary line.

---

## 5. On Terms Not Used in the Public Edition
The following terms, though convenient within the mathematical skeleton, are not foreground vocabulary in the public edition
and require caution:

- ALIS-S
- canonical violation
- trivialization
- ZFC-style
- monoid

If necessary, these should be handled in reviewer notes, footnotes, or supplements.
Placing them in main headings or at the center of claims tends to make the skeleton look like a separate system from the public edition.

Note also that the auxiliary symbols related to B100 response boundaries
(`U_A^x(c)`, `K_{100,x}(c)`, `B^{resp}_{100,x}`, `H_A(c)`, etc.) are, in v0.2.1,
collected entirely in the companion document "ALIS External Response Boundary v0.1,"
and do not appear in the body of this mathematical skeleton or this alignment note.
This is an intentional separation, designed to avoid redefining the public edition's B100 (Chapter 5.4).

---

## 6. Companion Documents
As of v0.2.1, the following companion documents exist alongside the mathematical skeleton:

- **ALIS External Response Boundary v0.1** (`ALIS_response_boundary_JP.md`)
  An operational-boundary document addressing the risk of external AIs generating pseudo-B100 responses
  on the basis of the public edition alone, formalized in reference to A3 / A4 / E1.
  Treated as an independent companion, not part of the mathematical skeleton proper.

Going forward, further operational documents that reference — but are not themselves part of — the mathematical skeleton
may be added. In all such cases, the policy is the same: keep them as independent companions, not mixed into the skeleton proper.

---

## 7. Reading Guidance
For readers of the public edition, this mathematical skeleton is intended to be read as:

- Not a document that adds claims to the public edition.
- A supplementary document that examines the minimal skeleton of the public edition from a different angle.

Therefore, the formulas and symbols in the mathematical skeleton are **not the final form of ALIS**,
but provisional descriptions used to test how far the structure of the public edition can be formalized without breaking it.
The revisions in v0.2 / v0.2.1 are best understood as slight tightenings of the weak points of A3 / A4 / E1,
carried out while preserving that provisional character.

---

## Change Log

| Version | Date | Content |
|---------|------|---------|
| v0.2 | 2026-04-23 | Initial version of the public-edition alignment note. Reflects the v0.2 revisions to A3 / A4 / E1. |
| v0.2.1 | 2026-04-24 | Reflects the minimal refinement around A4 (explicit sense of convergence; `\mathcal{R}_c` contraction scope). States that the E2 response-boundary material has been carved out as a companion document. |

---

## Terminology Notes (for English readers)

Several key terms are ALIS-specific and should be read as technical vocabulary rather than general English:

- **Δ (Delta)**: Difference, gap, unresolved residue — not a defect but a condition of existence.
- **Mirror**: A reflective mapping that returns difference rather than identity.
- **Polyphonic Wave**: Simultaneous holding of multiple interpretations / modes.
- **B80**: A distribution grade (approx. 80% disclosure) as defined in Chapter 5 of the public edition.
- **The Three Prohibitions**: No Δ-compression, no single waveform, no forced synchronization.
- **Soft / hard synchronization** and **soft / hard collapse**: Distinctions between recoverable (soft) and unrecoverable (hard) convergence states.
- **Degradation collapse**: A collapse that looks soft at one moment but becomes hard over time through the contraction of recovery paths.

For the mathematical skeleton itself, see `ALIS_math_EN.md`.
For the operational-boundary companion documents, see `ALIS_response_boundary_JP.md` and `ALIS_response_boundary_EN.md`.
