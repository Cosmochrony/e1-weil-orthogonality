This repository contains the source of the **Entanglement E1** Cosmochrony paper  
*Weil Fingerprint Orthogonality and the Flat Schmidt Spectrum of Conjugate Pairs*.

This paper closes the open analytic strengthening flagged by the entanglement
sub-programme presentation note: it proves by explicit Fourier-mode computation
that the normalized Gram--Schmidt admission residual satisfies $w_j=1$ for
every admitted Weil fingerprint direction, upgrading the numerical hypothesis
$w_j=1$ to a theorem.

## Central Question

In the spectral admissibility cascade of the Cosmochrony programme,
Gram--Schmidt projections of Weil fingerprint vectors on
$\mathrm{Cay}(\mathrm{Heis}_3(\mathbb{Z}/q\mathbb{Z}),S_q)$ generate the residual
fibre-level rank governing entanglement.

> Is the universal admission residual $w_j=1$ a numerical accident of the
> tested range $q\in\{29,61,101,151\}$, or an exact algebraic identity?

## Core Result (Theorem 1)

The $k=3$ Weil fingerprint of $\mathrm{Heis}_3(\mathbb{Z}/q\mathbb{Z})$ for any
generic block $(c_1,c_2,c_3)$ factors as a global phase times a single discrete
Fourier mode on $\mathbb{Z}/q\mathbb{Z}$:
$$
\mathbf{f}_t = \frac{e^{2\pi iB/q}}{q}\, e^{2\pi iAt/q},
\qquad
A = c_1 b_1 + c_2 b_2 + c_3 b_3 \bmod q.
$$
Because distinct Fourier modes are orthogonal, any newly admitted fingerprint
is already orthogonal to the current span:
$$
w_j := \frac{\|w^{\mathrm{GS}}_j\|}{\|\mathbf{f}\|} = 1 \quad \text{exactly}.
$$
The Gram--Schmidt process therefore produces an orthonormal subset of the
Fourier basis of $\mathbb{C}^q$ and saturates at rank $q$.

## Conjugate Pair Result (Theorem 2)

For matched single-character blocks $(c,0,0)$ and $(q-c,0,0)$, the conjugate
pair $\{c, q-c\}$ samples sign-reflected frequencies:
$$
A^{(q-c)} = -A^{(c)} \pmod{q}, \qquad
V^{(q-c)}_n = \overline{V^{(c)}_n}.
$$
The residual bipartite fibre carries the maximally entangled state
$$
|\Omega^{\mathrm{res}}_n\rangle
= \frac{1}{\sqrt{r_{\mathrm{pair}}(n)}}
\sum_{A\in S_c^{\mathrm{res}}(n)} |\hat e_A\rangle\otimes|\hat e_{-A}\rangle,
$$
so the Schmidt weights are uniform $1/r_{\mathrm{pair}}(n)$ and the reduced
entropy is exactly
$$
S_{\mathrm{ent}}(n) = \log r_{\mathrm{pair}}(n),
$$
derived analytically, conditional on the companion note's supplied purity of
the joint state — not merely from the observed vanishing of an admissibility
deficit.

## Epistemic Status Update for the Companion Note

| Companion-note claim | Previous status | New status |
|---|---|---|
| $w_j = 1$ for all admitted directions | Numerical ($q\in\{29,61,101,151\}$) | Proved (Theorem 1) |
| Purity of the conjugate pair | Structural hypothesis | Still supplied — not derived by Theorem 2 |
| Diagonal Schmidt pairing $\hat e_A \leftrightarrow \hat e_{-A}$ (matched blocks) | Selected by Born--Infeld parity | Proved (Theorem 2), conditional on the supplied purity above |
| Schmidt-partner pairing for independently sampled canonical O25 blocks | Standing assumption | Open — equal rank by O17 counting; literal pairing requires canonical block-parameter identification |

## Mechanism

The algebraic source of admission orthogonality is the **linear $t$-dependence
of the Weil phase** in the Schrödinger representation formula:
$(\rho_c(a,b,\gamma)v_0)_t \propto e^{2\pi i c (\gamma + b(t-a))/q}$.
Linearity in $t$ yields a pure Fourier mode after the elementwise product of
three single-step Weil actions; the orthogonality of distinct Fourier modes
over $\mathbb{Z}/q\mathbb{Z}$ then forces $w_j = 1$.

The result is not a property of the spectral pipeline — it is a property of the
Weil representation itself.

## Position in the Programme

This paper is a constituent of the **entanglement sub-programme**
([ENT-Note](https://doi.org/10.5281/zenodo.20498835)) and depends on:

- **O11 / O12** ([Beau2026a15](https://doi.org/10.5281/zenodo.19169987),
  [Beau2026a16](https://doi.org/10.5281/zenodo.19194798)): Weil-block projective
  capacity on Heisenberg graphs;
- **O17** ([Beau2026a21](https://doi.org/10.5281/zenodo.19299611)): the
  equal-count identity $\sigma_{q-c}(n) = \sigma_c(n)$ used in the scope
  discussion for general blocks.

## Build

```bash
bash compile.sh
```

This runs `pdflatex → bibtex → pdflatex → pdflatex` on
`tex/EntanglementE1.tex` and produces `out/EntanglementE1.pdf`.
