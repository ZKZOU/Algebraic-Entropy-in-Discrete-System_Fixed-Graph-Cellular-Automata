# Algebraic Entropy in Discrete System (Fixed Graph Cellular Automata)

### A New Definition of Entropy: Algebraic entropy for fixed-graph discrete systems. Non-probabilistic, coarse-graining-free entropy via node-value product. Gradient-driven dynamics guarantees strict increase. AM-GM yields upper bound. Computable, deterministic, high-resolution.



## Abstract

In the study of discrete complex systems and fixed-graph evolution, conventional entropy definitions rely on probability distributions, ensemble assumptions, or coarse-graining operations. Consequently, they struggle to directly characterize the microscopic evolutionary paths and gradient-driven mechanisms of systems with fixed topological structures. Building upon the gradient-driven multiplicative entropy framework proposed by Zou, Z. K. (2025), this paper further develops an algebraic entropy theory applicable to discrete node systems. The theory takes integer node values as its fundamental variables and, under the constraint of global sum conservation, defines the system entropy as the product of all node values. Through the arithmetic-geometric mean inequality, the conservation law directly yields a mathematical upper bound for entropy, while the gradient-driven transfer rule guarantees that every evolutionary step strictly increases entropy. This entropy definition does not rely on any probabilistic assumptions, introduces no statistical ensembles, requires no coarse-graining, and is uniquely determined by the current state of the system. The framework transforms the second law of thermodynamics from a "statistical tendency" into an "algebraic necessity," providing a computable, high-resolution microscopic foundation for the arrow of time, path selection, and complexity evolution in discrete systems.

**Keywords**: algebraic entropy; multiplicative entropy; gradient-driven; conservation law; fixed-graph evolution; discrete systems; irreversibility; AM-GM inequality

---

## 1. Introduction: The Dilemma of Entropy in Discrete Systems

In complex systems research, entropy is commonly used to measure disorder or information deficiency. However, for discrete networks, graph evolution, cellular automata, or resource allocation systems, conventional statistical entropy faces two fundamental difficulties:

1. **Observer-dependent definition**: The entropy value depends on how macroscopic states are partitioned and at which coarse-graining scale, rather than being uniquely determined by the system itself.
2. **Lack of dynamical information**: Entropy change indicates direction but does not specify how each step occurs or how gradient magnitudes affect the evolutionary path.

These problems are particularly pronounced for **fixed-topology networks** (where node adjacency relations remain invariant while node states change). Real evolving systems—such as heat conduction, information diffusion, and chemical reaction networks—are inherently **gradient-driven**: quantities flow from high-value nodes to low-value nodes. This fundamental fact suggests that entropy increase should not be merely a probabilistic statement, but an algebraic process directly tied to conservation laws and gradient rules. The multiplicative entropy framework proposed by Zou (2025) offers a new path in this direction, and this paper systematizes that theory further, presenting it for researchers in discrete systems.

## 2. Model Setup

Consider a closed discrete system consisting of N nodes, satisfying:

- Each node i carries a positive integer energy value m_i ∈ ℕ⁺ (which may represent resources, information quanta, or energy quantum numbers).
- Global sum conservation:

  E = Σᵢ m_i = constant

- Fixed network topology: adjacency relations among nodes remain unchanged throughout the entire evolution.

### 2.1 Gradient-Driven Transfer Rule

Energy transfer is allowed only between adjacent nodes, and occurs one quantum unit at a time. The transfer condition is:

m_i > m_j + 1

The transfer operation is:

m_i → m_i − 1,   m_j → m_j + 1

This rule is **deterministic**: it introduces no probabilities, relies on no ensembles, and requires no coarse-graining. The direction of evolution at each step is entirely determined by the current energy gradient distribution.

## 3. Definition of Algebraic Entropy

Define the entropy of the system at a given moment as the product of all node energy values:

S = ∏ᵢ m_i

This definition possesses the following properties:

- Independent of probability distributions or ensemble assumptions;
- Independent of coarse-graining scales;
- Uniquely determined by the current energy distribution;
- Takes positive integer values, facilitating numerical computation and path tracking.

### 3.1 Algebraic Proof of Entropy Increase

Consider a legitimate transfer: two adjacent nodes have energies a and b before transfer (a > b + 1), and become a−1 and b+1 after transfer. The entropy ratio is:

S′ / S = (a−1)(b+1) / (a·b) = 1 + (a − b − 1) / (a·b)

Since a − b − 1 > 0 and a, b > 0, we have:

S′ / S > 1 ⇒ S′ > S

**Conclusion**: Every legitimate gradient-driven transfer necessarily leads to a strict increase in algebraic entropy. Entropy increase is not a probabilistic event but an algebraic necessity.

## 4. Conservation Law as the Upper Bound of Entropy

Applying the arithmetic-geometric mean inequality (AM-GM):

E / N ≥ (∏ᵢ m_i)^(1/N)

We directly obtain:

S ≤ (E / N)^N

Equality holds if and only if all m_i are equal (uniform distribution). Therefore:

- The **first law (conservation law)** provides the absolute upper bound of entropy;
- The **second law (entropy increase)** provides the necessary path toward that upper bound.

Within this framework, the conservation law and the entropy increase law are no longer independent postulates, but constitute a unified structure of constraint and drive.

## 5. Maximum Entropy Path and Maximum Gradient Path

In a single transfer, the entropy increment is:

ΔS = S′ − S = S · (a − b − 1) / (a·b)

This expression directly shows: **the larger the energy gradient, the greater the single-step entropy increase**.

If node i can transfer to multiple lower-energy neighbors simultaneously, then transferring to the **lowest-energy** neighbor yields the largest single-step entropy increase. Hence:

Maximum gradient path = Maximum (single-step) entropy path

This equivalence transforms the second law from probabilistic language into a **gradient-driven algebraic path-selection rule**.

## 6. Implications for Fixed-Graph Evolution Research

### 6.1 Internalization of the Arrow of Time

In a fixed graph network, if no energy gradient exists, the system is in equilibrium and entropy no longer changes. The existence of the arrow of time is equivalent to the existence of transferable gradients within the system. Every transfer increases algebraic entropy, so time steps are in one-to-one correspondence with entropy-increment sequences.

### 6.2 Path Branching and Historical Dependence

Since maximum-gradient paths are not necessarily unique, different paths may lead to different intermediate states. Even with identical initial states, systems may evolve different historical trajectories due to path choices. This path branching naturally explains **multi-stability** and **historical dependence** in fixed-graph systems.

### 6.3 Connection to Classical Entropy

Taking the logarithm of algebraic entropy:

ln S = Σᵢ ln m_i

When the energy distribution is relatively smooth, this form can be related to Boltzmann entropy via Stirling's approximation or combinatorial counting. Thus, algebraic entropy is compatible with classical thermodynamics in the macroscopic limit, while providing higher-resolution descriptions at discrete microscopic scales.

## 7. Discussion and Outlook

### 7.1 Revising the Notion that "Entropy Increase Is Statistical"

Conventional views treat entropy increase as a "high-probability" event. This framework demonstrates that under conservation laws and gradient-driven rules, entropy increase is a **logical necessity**, independent of any probabilistic assumptions. This shift is significant for understanding non-equilibrium systems, finite systems, and small systems.

### 7.2 Freedom from Coarse-Graining

Algebraic entropy does not depend on the observer's definition of macroscopic states. It is computed directly from the system's microscopic state (the distribution of node values), making it applicable to systems where coarse-graining is impractical or undesirable, such as finite-scale networks, computational models, and complex adaptive systems.

### 7.3 Generalizability

Beyond energy systems, any system satisfying "node-value conservation + gradient-driven dynamics + integer values" can adopt this entropy definition, including:

- Information packet forwarding in fixed routing networks;
- Wealth transfer in fixed social networks;
- Population diffusion on spatial lattices;
- Computational resource scheduling in distributed systems.

### 7.4 Open Questions

The current framework is based on a deterministic maximum-gradient rule. Future research may explore:

- The behavior of algebraic entropy and path statistics when noise or stochastic perturbations are introduced;
- Whether this entropy definition retains similar properties in dynamic networks (with topological changes);
- The relationship with action (least-action paths), and whether equivalence conditions exist between global maximum-entropy paths and least-action paths.

## 8. Conclusion

Building upon the gradient-driven multiplicative entropy framework proposed by Zou, Z. K. (2025), this paper systematizes an algebraic entropy theory applicable to fixed-graph discrete systems. Within this framework:

- Entropy is defined as the product of node values;
- The conservation law provides the absolute upper bound of entropy via the AM-GM inequality;
- The gradient-driven rule guarantees entropy increase at every step;
- Entropy increase is an algebraic necessity, independent of probabilistic assumptions;
- The maximum-entropy path is equivalent to the maximum-gradient path.

This framework offers a clear, computable, and coarse-graining-free theoretical foundation for the arrow of time, irreversibility, path selection, and complexity evolution in discrete systems. It suggests that in the discrete world, entropy increase is not a "tendency" but a "necessity"—not "statistical" but "algebraic."

---

### References:

[1] Zou,  Z. K. (2025). The Thermodynamic Arrow of Time in a Double-Layer Topology-Invariant Chiral Space with Geometric (GR) and Gauge (QFT) Degrees of Freedom :Time-Entropy Mapping; Mass-Gravity Duality; Metric-Frequency Mirroring. Preprints. https://doi.org/10.20944/preprints202505.0270.v12

[2] Zou, Z. K. (2026). Energy Conservation as the Constraint Precondition for Monotonic Entropy Increase, The Mathematical Structure Between the First and Second Laws of Thermodynamics. Zenodo. https://doi.org/10.5281/zenodo.21896055 
