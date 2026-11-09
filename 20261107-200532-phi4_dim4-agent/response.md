# Derivation response: phi4_dim4

- Status: **failed**

## Problem

Derive the analytical 2 -> 2 scattering amplitude for a massless real scalar field through order $c_4^2$, including tree-level and one-loop contributions, using dimensional regularization and $\overline{\text{MS}}$ renormalization.

## Proposed Lagrangian and conventions

$$\mathcal{L} = \frac{1}{2} \partial_\mu \phi \partial^\mu \phi + c_4 \frac{\phi^4}{4!}$$ with metric $(+,-,-,-)$, canonical kinetic term, no mass term, and $c_4$ defined as the coefficient of $\phi^4/4!$.

## Derivation

### Establish the Lagrangian $\mathcal{L} = \frac{1}{2} \partial_\mu \phi \partial^\mu \phi + c_4 \frac{\phi^4}{4!}$ and derive the Feynman rules for the massless propagator and the 4-point vertex.

### Lagrangian and Action
The theory is a massless real scalar field with a $\phi^4$ interaction. Using the metric $(+,-,-,-)$ and the specified conventions, the Lagrangian density is:
$$ \mathcal{L} = \frac{1}{2} \partial_\mu \phi \partial^\mu \phi + c_4 \frac{\phi^4}{4!} $$
The action $S = \int d^4x \mathcal{L}$ splits into the free and interacting parts:
$$ S_0 = \int d^4x \frac{1}{2} \partial_\mu \phi \partial^\mu \phi, \quad S_{int} = \int d^4x c_4 \frac{\phi^4}{4!} $$

### Propagator Derivation
To find the momentum-space propagator, we evaluate the free action $S_0$. Integrating by parts and discarding boundary terms:
$$ S_0 = -\frac{1}{2} \int d^4x \phi \partial_\mu \partial^\mu \phi = -\frac{1}{2} \int d^4x \phi \Box \phi $$
Fourier transforming $\phi(x) = \int \frac{d^4p}{(2\pi)^4} e^{-ip\cdot x} \tilde{\phi}(p)$, the d'Alembertian acts as $\Box \to -p^2$. Substituting this in:
$$ S_0 = \frac{1}{2} \int \frac{d^4p}{(2\pi)^4} \tilde{\phi}(p) p^2 \tilde{\phi}(-p) $$
In the path integral $\int \mathcal{D}\phi \exp(i S_0)$, we enforce the Feynman prescription by shifting $p^2 \to p^2 + i\epsilon$ to ensure convergence. The quadratic form in the exponent is $\frac{i}{2} \tilde{\phi}(p^2 + i\epsilon)\tilde{\phi}(-p)$. The propagator is the inverse of the kinetic operator multiplied by $i$:
$$ \Delta_F(p) = \frac{i}{p^2 + i\epsilon} $$

### Vertex Rule Derivation
The Feynman rule for the 4-point vertex is derived from the expansion of the interaction weight $\exp(i S_{int})$ in the path integral. To first order in $c_4$:
$$ \exp(i S_{int}) \approx 1 + i \int d^4x c_4 \frac{\phi(x)^4}{4!} + \dots $$
For a 4-point scattering process, we contract the 4 fields in $\phi(x)^4$ with the 4 external states. There are $4!$ identical ways to perform this contraction, which exactly cancels the $1/4!$ symmetry factor in the Lagrangian. 
Thus, the vertex factor is simply the coefficient of the interaction term multiplied by $i$:
$$ V_4 = i c_4 $$
*(Note: The sign is strictly positive because $\mathcal{L}_{int} = +c_4 \phi^4/4!$. While the potential is $V = -\mathcal{L}_{int}$, the vertex rule follows directly from $i \mathcal{L}_{int}$ in the path integral, yielding $+i c_4$.)*

### Tree-Level Amplitude
The amplitude $\mathcal{A}$ is defined by $i \mathcal{A} = \sum \text{connected, amputated diagrams}$. 
At tree level (order $c_4$), the only diagram for $2 \to 2$ scattering $\phi(p_1) \phi(p_2) \to \phi(p_3) \phi(p_4)$ is the single contact interaction. Amputating the external legs removes the external propagators, leaving only the vertex factor. Therefore:
$$ i \mathcal{A}_{tree} = i c_4 \implies \mathcal{A}_{tree} = c_4 $$

```final
A_tree = c4
```

### Construct the tree-level diagrams for $\phi \phi \to \phi \phi$ and compute the order $c_4$ amplitude $\mathcal{A}_{\text{tree}}$ in terms of Mandelstam variables $s, t, u$.

### Tree-Level Amplitude Derivation

The interaction part of the Lagrangian is given by:
$$ \mathcal{L}_{\text{int}} = c_4 \frac{\phi^4}{4!} $$

The S-matrix expanded to first order in the coupling $c_4$ is:
$$ S^{(1)} = i \int d^4x \, \mathcal{L}_{\text{int}}(x) = i c_4 \int d^4x \frac{\phi(x)^4}{4!} $$

For the $2 \to 2$ scattering process $\phi(p_1) \phi(p_2) \to \phi(p_3) \phi(p_4)$, we evaluate the matrix element between the initial state $|i\rangle = |p_1, p_2\rangle$ and the final state $|f\rangle = |p_3, p_4\rangle$. 

Using Wick's theorem, we contract the four fields in $\phi(x)^4$ with the four external particle states. Since all four fields are identical and all four external particles are identical scalars, there are $4! = 24$ distinct ways to perform the contractions. This combinatorial factor exactly cancels the $1/4!$ symmetry factor in the Lagrangian.

The remaining spacetime integral yields the momentum-conserving delta function:
$$ \langle f | S^{(1)} | i \rangle = i c_4 \int d^4x \, e^{-i(p_1 + p_2 - p_3 - p_4) \cdot x} = i c_4 (2\pi)^4 \delta^{(4)}(p_1 + p_2 - p_3 - p_4) $$

The invariant amplitude $\mathcal{A}$ is defined by stripping off the momentum-conserving delta function and a factor of $i$:
$$ \langle f | S | i \rangle = i \mathcal{A} (2\pi)^4 \delta^{(4)}(p_1 + p_2 - p_3 - p_4) $$

Comparing the two expressions, we find:
$$ i \mathcal{A}_{\text{tree}} = i c_4 \implies \mathcal{A}_{\text{tree}} = c_4 $$

Because this is a point-like contact interaction with no internal propagators, the tree-level amplitude is a constant and does not depend on the Mandelstam variables $s, t,$ or $u$.

```final
A_tree = c4
```

### Identify all one-loop topologies (s, t, u channel bubbles) at order $c_4^2$, determining their symmetry factors and overall vertex factors.

### One-Loop Topologies at Order $c_4^2$

At order $c_4^2$, the scattering amplitude receives contributions from diagrams with exactly two 4-point vertices. For $2 \to 2$ scattering $\phi(p_1) \phi(p_2) \to \phi(p_3) \phi(p_4)$, each vertex must absorb or emit external legs while the remaining legs are connected by internal propagators. Since each vertex has 4 legs and there are 4 external legs in total, the only valid 1-loop topology is the "bubble" (or 2-point sunset) diagram, where two vertices are connected by two internal lines. 

The distinct assignments of external momenta to the two vertices define the three kinematic channels:
1. **s-channel**: Vertex 1 connects to $p_1, p_2$; Vertex 2 connects to $p_3, p_4$. The total momentum flowing through the internal lines is $P_s = p_1 + p_2$.
2. **t-channel**: Vertex 1 connects to $p_1, p_3$; Vertex 2 connects to $p_2, p_4$. The total momentum flowing through the internal lines is $P_t = p_1 - p_3$.
3. **u-channel**: Vertex 1 connects to $p_1, p_4$; Vertex 2 connects to $p_2, p_3$. The total momentum flowing through the internal lines is $P_u = p_1 - p_4$.

### Symmetry Factors and Vertex Factors

To determine the symmetry factor $S$ for a given channel (e.g., the s-channel), we count the number of valid Wick contractions. 
- At Vertex 1, we choose 2 legs out of 4 to contract with $p_1, p_2$: $4 \times 3 = 12$ ways.
- At Vertex 2, we choose 2 legs out of 4 to contract with $p_3, p_4$: $4 \times 3 = 12$ ways.
- The remaining 2 legs at Vertex 1 must contract with the remaining 2 legs at Vertex 2: $2! = 2$ ways.
This yields $12 \times 12 \times 2 = 288$ contractions for a fixed assignment of spacetime vertices $(x, y)$ to the channels. 

The Dyson series provides a factor of $\frac{1}{2!}$, and the Lagrangian interaction terms provide $\frac{1}{(4!)^2} = \frac{1}{576}$. The integral $\int d^4x \, d^4y$ contains 2 permutations of $(x, y)$ that match the external leg assignment (either $x$ is Vertex 1 and $y$ is Vertex 2, or vice versa). The total diagram weight is:
$$ \text{Weight} = \frac{1}{2!} \times \frac{1}{576} \times 2 \times 288 = \frac{1}{2} $$
Thus, the symmetry factor is $S = 2$. This corresponds to the single non-trivial automorphism of the diagram: exchanging the two identical internal propagators.

The overall vertex factor for two vertices is $(i c_4)^2 = -c_4^2$. 
The two internal massless propagators carrying loop momentum $k$ and $(P - k)$ contribute:
$$ \frac{i}{k^2 + i\epsilon} \frac{i}{(P - k)^2 + i\epsilon} = \frac{-1}{(k^2 + i\epsilon)((P - k)^2 + i\epsilon)} $$

### Channel Amplitudes and Scalar Integrals

We define the denominator-only scalar integral for a generic channel with momentum $P$ as:
$$ I(P^2) = \int \frac{d^d k}{(2\pi)^d} \frac{1}{(k^2 + i\epsilon)((P - k)^2 + i\epsilon)} $$
where $d = 4 - 2\epsilon$.

For the s-channel, the contribution to $i\mathcal{A}$ is:
$$ i\mathcal{A}_s = \frac{1}{S} (\text{vertices}) (\text{propagators}) \times I(s) = \frac{1}{2} (-c_4^2) (-1) I(s) = \frac{c_4^2}{2} I(s) $$
Dividing by $i$, the s-channel amplitude is $\mathcal{A}_s = -i \frac{c_4^2}{2} I(s)$.

By identical reasoning, the t-channel and u-channel amplitudes are:
$$ \mathcal{A}_t = -i \frac{c_4^2}{2} I(t), \quad \mathcal{A}_u = -i \frac{c_4^2}{2} I(u) $$

### Total One-Loop Amplitude

Summing the connected, amputated diagrams across all three channels gives the total one-loop amplitude:
$$ \mathcal{A}_{\text{loop}} = \mathcal{A}_s + \mathcal{A}_t + \mathcal{A}_u = -i \frac{c_4^2}{2} \left[ I(s) + I(t) + I(u) \right] $$

```final
A_tree = c4
A_loop = -i * (c4^2 / 2) * (I(s) + I(t) + I(u))
```

## Result

No final result was accepted.
