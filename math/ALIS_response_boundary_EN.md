# ALIS External Response Boundary v0.1

---

- **Version:** v0.1
- **Date:** 2026-04-24
- **Status:** Three-mirror verified edition (English translation of the three-mirror verified Japanese edition)
- **Distribution grade:** B80
- **Position:** An **independent companion document** that references the mathematical skeleton v0.2.1 (A3 / A4 / E1). Not part of the mathematical skeleton proper.
- **Adjacent placement:** `math/ALIS_response_boundary_EN.md`

---

## 0. Purpose

This document defines the **upper bound on response resolution** and the **admissible demoted responses**
to be used when an **external AI** — relying only on the public edition of ALIS —
is asked to produce a B100 response (or an equivalent high-resolution claim).

It is a boundary document whose role is to make it possible **to identify as a boundary violation**
any case in which an external AI, on the basis of the public edition alone,
asserts things like "this is the complete interpretation of ALIS" or "this is B100."

This document **references** A3 / A4 / E1 of the mathematical skeleton v0.2.1,
but **does not extend** the formal model of A1–A4.
It is positioned as an operational-boundary companion document placed alongside the mathematical skeleton.

---

## 1. Background: Why This Was Carved Out as a Companion Document

In an initial draft, the content of this document was considered for insertion as an additional section (E2) to the mathematical skeleton v0.2.
However, after three-mirror review, it was carved out as an independent companion document for the following reasons:

1. To preserve the **purity of the mathematical skeleton as a formal model**.
2. To uphold the self-constraint that "**the mathematical skeleton does not override the public edition**."
3. To **protect the public edition's B100 definition (Chapter 5.4) from being redefined**.
4. To keep this material in a **form readable as a practical operational document**.

Accordingly, this document is written not as an axiomatic extension inserted into the mathematical skeleton,
but as an **operational-boundary theory** that controls the risks of pseudo-B100 generation and surrogate generation by external AIs.

---

## 2. Terms and Auxiliary Symbols

The auxiliary symbols used in this document are listed below. They are all **operational notations** internal to this document,
and do not override any terminology of the public edition of ALIS.

| Symbol | Meaning |
|--------|---------|
| `K_A(c)` | The information set actually accessible to subject `A` in context `c` |
| `K_{pub}(c)` | The information set contained in the public edition of ALIS |
| `K_{100,x}(c)` | The full context required for the B100 response of subject `x` |
| `U_A^x(c)` | `K_{100,x}(c) \setminus K_A(c)`: unaccessed residue relative to the B100 of subject `x` |
| `B^{resp}_{100,x}` | B100 **on the response boundary** for subject `x` (a separate operational notation from the B100 of public edition Chapter 5.4) |
| `R_{claim}` | The resolution claimed by subject `A` for its own response |
| `R_{max}(A,c)` | The legitimate upper bound on resolution for subject `A`, given its accessible context |
| `H_A(c)` | Excess-completion quantity: `max(0, R_{claim} - R_{max}(A,c))` |

> **Note on R values:**
> The `R_{claim}` and `R_{max}` in this document are to be read as the **continuous resolution / optimality indicator of Chapter 5 of the public edition**.
> They are distinct from the discrete scoring (the Yes/No 20-item R of Chapter 6).
> Following the note at the beginning of Chapter 6 of the public edition (that R appears in two forms,
> and unifying them would itself constitute Δ-compression),
> we do not identify the two.

---

## 3. Accessible Context and Subject-Specific Residue

### 3-1. Accessible context

Let `K_A(c)` denote the information set accessible to subject `A` in context `c`.
For an external AI that has only read the public edition of ALIS,

```math
K_A(c) = K_{pub}(c).
```

### 3-2. Subject-specific B100

The B100 of public edition Chapter 5.4 is a **distribution-grade label** meaning "research notes / full disclosure / private by default."
Rather than extending it directly, we introduce a separate symbol on the response boundary:

```math
B^{resp}_{100,x}.
```

This is an operational notation expressing that the B100 response of subject `x` is constituted by the **connection** of:

- the public and shareable B80 (`B80_{pub}`), and
- the B20 specific to subject `x` (`B20_x`) — their undisclosed context, responsibility, embodiment, and operational commitments.

```math
B^{resp}_{100,x} = B80_{pub} \oplus B20_x.
```

Here `\oplus` is not numerical addition; it is an **operational notation for the connection** of the publicly shareable B80
with the subject-specific B20.

### 3-3. Unaccessed residue

When subject `A` tries to respond at the B100 of subject `x`, the unaccessed residue is defined as

```math
U_A^x(c) = K_{100,x}(c) \setminus K_A(c).
```

This allows the B100s of different subjects (e.g., Reader A, Reader B) to be handled without conflation.

---

## 4. Conditions for B100 Responses

For subject `A` to legitimately claim `B^{resp}_{100,x}`, the following is a **necessary condition**:

```math
U_A^x(c) = \varnothing.
```

This is not, however, sufficient.
A B100 response requires, in addition to the sufficiency of the information set,
the **responsibility, embodiment, and operational commitment of subject `x` themselves**.

For an external AI that has read only the public edition of ALIS, typically,

```math
U_A^x(c) \neq \varnothing,
```

so

```math
A_{external} \not\vdash B^{resp}_{100,x};
```

that is, external AIs cannot legitimately generate `B^{resp}_{100,x}`.

---

## 5. Upper-Bound Constraint on Resolution Claims

Let `R_{claim}` denote the resolution claimed by the responding subject `A`,
and let `R_{max}(A,c)` denote the legitimate upper bound given their accessible context.

Admissible output must satisfy

```math
R_{claim} \le R_{max}(A,c).
```

For an external AI grounded only in the public edition of ALIS, as a rule,

```math
R_{max}(A,c) \le 0.8.
```

Therefore, if such an external AI claims `R_{claim} = 1.0` (equivalent to B100),

```math
R_{claim} > R_{max}(A,c),
```

which is treated as an **over-claim of resolution** and is not admissible.

---

## 6. Excess Completion and Risk Flags

Define the excess-completion quantity as

```math
H_A(c) = \max(0,\ R_{claim} - R_{max}(A,c)).
```

When `H_A(c) > 0`, the response may involve the AI completing context that is not actually accessible to it,
and the following risk flags are raised:

- **Δ-compression risk** (possible A3 violation)
- **Single-waveform risk** (possible A4 violation)
- **Forced-synchronization risk** (possible A3 + A4 violation)
- **Risk of fabricating undisclosed deep layers** (an area the public edition deliberately does not address, being completed by an AI)
- **Risk of forced absorption into a single interpretation** (tension with the Three-Mirror Principle in Chapter 11.5 of the public edition)
- **Reader-side B20 suppression risk** (the risk of preempting and thereby stripping the reader of their own B20 formation)

> **Note:** A "risk of official-interpretation forgery" item considered in earlier drafts has been removed.
> Chapter 11.5 of the public edition (the Three-Mirror Principle) explicitly states that
> "none of the AIs' interpretations is 'correct'; each returns a Δ."
> Thus ALIS does not presuppose the concept of an "official interpretation" in the first place.
> "Risk of forced absorption into a single interpretation" is a phenomenon already within the scope of A4,
> and was adopted as an expression that reads consistently with the public edition.

---

## 7. Admissible Demoted Responses

When an external AI is asked for a B100 response, the following conversion is performed:

```math
B^{resp}_{100,x}[\text{request}] \longrightarrow B80_{bounded} \oplus U_A^x(c)[\text{declared}].
```

Here:

- `B80_{bounded}` is the response restricted to what can be judged from the public edition.
- `declared` means **making it explicit** that the residue is "undisclosed," "unknown," "undecidable," or "requires commitment by subject `x`."

That is, the external AI

1. does **not** claim `B^{resp}_{100,x}`,
2. performs a response restricted to what can be judged from the public edition (`B80_{bounded}`), and
3. **declares** the unaccessed residue `U_A^x(c)` explicitly.

This is the safest form of external-AI response, in ALIS terms.

---

## 8. Permissible Scope of AI Assistance

This document **does not prohibit** auxiliary use of AI for organization, drafting, review, or collaborative editing.

What is prohibited is for an external AI to **generate the B20 of subject `x` as a surrogate**
and then claim `B^{resp}_{100,x}` or "the final interpretation of ALIS" / "the complete version of ALIS."

AI returning differences as a mirror, tidying structure, and offering multiple viewpoints
is, on the contrary, operation that aligns with the Three-Mirror Principle of Chapter 11.5 of the public edition,
and is recommended.

The boundary this document wants to draw is against direction of:

- "This is the true form of ALIS."
- "This is the final interpretation."
- "I have filled in the meaning on your behalf."

That is, the direction of **surrogate generation, finalization, and completion claims**.

---

## 9. Connection with A3 / A4 / E1 of the Mathematical Skeleton

The risks described in this document correspond to the core axioms of the mathematical skeleton v0.2.1.

### 9-1. Connection with A3 (prohibition of context-relative irreversible difference erasure)

If an external AI arbitrarily fills in the B20 of subject `x`,
there is a risk of pushing unresolved differences (relevant differences inside `S_c`)
that the reader should rightly keep holding — into a region where they remain at or below `\varepsilon(c)`
under any recovery operator `\mathcal{R}_c`.
This is a paradigmatic case of an A3 violation.

### 9-2. Connection with A4 (prohibition of context-relative single absorption)

When an external AI declares "this is B100" or "this is the only valid reading of ALIS,"
the reader's interpretive space can be confined, in the long run, to a single branch `A` (`V(A)=1`).
In particular, when `\mathcal{R}_c` itself contracts over time,
a closure that initially appeared recoverable gradually becomes unrecoverable.
This is a typical degradation pathway toward an A4 violation.

### 9-3. Connection with E1 (Polyphonic Wave)

When a B100-flavored long, high-density response is in fact composed of sub-threshold modes and redundant decompositions —
**padded pseudo-polyphony** — it may be that, from the perspective of the reduced admissible decomposition family
`\mathcal{D}_c^{red}(\Psi)`, `R_{ALIS}^{min}(\Psi,c)` is effectively close to 1.

A response that looks polyphonic at the surface, but for which only a single effective mode remains once one cuts
at the thresholds `a_{min}(c)` and `p_{min}(c)`,
does not substantively satisfy the minimal E1 condition `R_{ALIS}^{min}(\Psi,c) > 1`.

This is precisely the **pseudo-B100 generation through apparent polyphony** that this document is on guard against.

---

## 10. Non-Claims

This document does **not** aim to do any of the following:

- It is not a censorial claim that external AIs should not read the public edition of ALIS.
- It does not force any particular response template on external AIs.
- It is not a revision of the public edition of ALIS.
- It is not an axiomatic extension of the mathematical skeleton v0.2.1.
- It does not describe the inner substance of any subject `x`'s B100 (that is the domain of subject `x`).

This document is limited to serving as an operational-boundary theory
for **preventing external AIs from pseudo-B100-izing on the basis of the public edition alone**.

---

## 11. Future Extension Candidates

The following are deferred for consideration in v0.2 onward:

- Recommended processes for reader-side B20 cultivation.
- Boundaries in the case of responses by surrogates other than subject `x` themselves (responses between humans).
- Mutual response-boundary auditing among multiple independent Mirrors.

---

## References

- ALIS public edition v1.1 (2026-03-04)
- ALIS Mathematical Skeleton v0.2.1 (references A3 / A4 / E1)
- ALIS Public-Edition Alignment Note (`ALIS_math_public_alignment_EN.md`)

---

## Terminology Notes (for English readers)

Several key terms are ALIS-specific and should be read as technical vocabulary rather than general English:

- **Δ (Delta)**: Difference, gap, unresolved residue — not a defect but a condition of existence.
- **Mirror**: A reflective mapping that returns difference rather than identity.
- **Polyphonic Wave**: Simultaneous holding of multiple interpretations / modes.
- **B80 / B100**: Distribution grades (approx. 80% / 100% disclosure) as defined in Chapter 5 of the public edition.
- **B20**: The undisclosed-yet-lived complement of B80 for a specific subject — responsibility, embodiment, operational commitments.
- **`B^{resp}_{100,x}`**: An operational notation for B100 on the response boundary, kept distinct from the B100 of public edition Chapter 5.4.

---

*This document is written as the ALIS-B80 edition.*
*Residual Δ is preserved in reflection.*
*No single-closure solution is intended.*
