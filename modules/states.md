---
description: >-
  Quantum states are the key mathematical objects in quantum theory. Quantum
  states are states of knowledge, representing uncertainty about the real
  physical state of the system.
---

# States

Quantum mechanics is the backbone for quantum information processing, and many aspects of it cannot be explained by classical reasoning.&#x20;

{% hint style="warning" %}
For example, there is no strong classical analogue for pure quantum states or entanglement, and this leads to stark differences between what is possible in the classical and quantum worlds.&#x20;
{% endhint %}

However, at the same time, it is important to emphasize that all of classical information theory is subsumed by quantum information theory, so that whatever is possible with classical information processing is also possible with quantum information processing. As such, quantum information subsumes classical information while allowing for richer possibilities.

### Quantum Systems

A quantum system $$A$$ is associated with a [Hilbert space](general-functions.md#firstheading) $$H_{A}$$. The state of the system $$A$$ is described by a density operator, which is a unit-trace, positive semi-definite linear operator acting on $$H_{A}$$.

#### Bipartite Quantum Systems

For distinct quantum systems $$A$$ and $$B$$ with associated [Hilbert spaces](general-functions.md#firstheading) $$H_{A}$$ and $$H_{B}$$ , the composite system $$AB$$ is associated with the [Hilbert space](general-functions.md#firstheading) $$H_{A} \otimes  H_{B}$$. This joint state is described by a bipartite quantum state $$\rho_{AB} \in D(H_{A} \otimes H_{B})$$. For brevity, the joint [Hilbert space](general-functions.md#firstheading) $$H_A \otimes H_B$$ of the composite system $$AB$$ is denoted by $$H_{AB}$$ .

#### ``[`Measurement`](https://en.wikipedia.org/wiki/Measurement\_in\_quantum\_mechanics)``

The **measurement** of a [quantum system](states.md#quantum-systems) $$A$$ is described by a [**Positive Operator Valued Measure (POVM)**](https://en.wikipedia.org/wiki/POVM) $$\{M_{x}\}_{x \in {X}}$$, which is defined to be a collection of positive semi-definite operators indexed by a finite alphabet satisfying $$\sum_{x \in X} {M_x} = 1_{H_A}$$.

If the system is in the state $$\rho$$, then the probability $$Pr[x]$$ of obtaining the outcome $$x$$ is given by the Born rule as $$Pr[x] = Tr[M_x \rho ]$$.

#### ``[`Evolution`](https://en.wikipedia.org/wiki/Quantum\_channel#Time\_evolution)``

The **evolution** of the state of a quantum system is described by a quantum channel, which is a linear, completely positive, and trace-preserving map acting on the state of the system.

### Quantum States

A [quantum state](https://en.wikipedia.org/wiki/Quantum\_state) is a mathematical entity that provides a probability distribution for the outcomes of each possible measurement on a [system](states.md#quantum-systems). The [state](https://en.wikipedia.org/wiki/Quantum\_state) of a [quantum system](states.md#quantum-systems) is described by a [density operator](https://en.wikipedia.org/wiki/Density\_matrix#Definition\_and\_motivation) acting on the underlying [Hilbert space](general-functions.md#firstheading) of the [quantum system](states.md#quantum-systems). Knowledge of the [quantum state](https://en.wikipedia.org/wiki/Quantum\_state) together with the rules for the system's [evolution in time](https://en.wikipedia.org/wiki/Quantum\_channel#Time\_evolution) exhausts all that can be predicted about the system's behavior.

{% hint style="info" %}
A [density operator](https://en.wikipedia.org/wiki/Density\_matrix#Definition\_and\_motivation) is a unit-trace, positive semi-definite linear operator. We denote the set of density operators on a [Hilbert space](general-functions.md#firstheading) $$H$$ as $$D(H)$$
{% endhint %}

We typically use the Greek letters $$\rho$$, $$\sigma$$, $$\tau$$, or $$\omega$$ to denote [quantum states](https://en.wikipedia.org/wiki/Quantum\_state).

#### QuTIpy States

QuTIpy contains the definitions of these states, inside the `states` sub-module, and can be imported as such

```python
from qutipy.states import (
    Bell_state,
    GHZ_state,
    MaxEnt_state,
    MaxMix_state,
    RandomDensityMatrix,
    RandomStateVector,
    Werner_state,
    Werner_twirl_state,
    graph_state,
    isotropic_state,
    isotropic_twirl_state,
    singlet_state
)
```

### Maximally Entangled State

A pure state $$\displaystyle \psi_{AB} = |\psi\rangle\langle\psi|_{AB}$$, for two systems $$A$$ and $$B$$ of the same dimension $$d$$, is called **Maximally Entangled** if the Schmidt coefficients of $$\displaystyle |\psi\rangle_{AB}$$ are all equal to $$\frac{1}{\sqrt{d}}$$ , with $$d$$ being the Schmidt rank of $$\displaystyle |\psi\rangle_{AB}$$.

In other words, $$\psi_{AB}$$ is called maximally entangled if $$\displaystyle |\psi\rangle_{AB}$$ has the Schmidt decomposition,$$\displaystyle |\psi\rangle_{AB} = \frac{1}{\sqrt{d}}\sum_{k=1}^{d} |e_k\rangle_A \otimes |f_k\rangle_B$$ for some orthonormal sets $$\displaystyle \{ |e_k\rangle_A : 1 \le k \le d \}$$ and $$\displaystyle \{ |f_k\rangle_B : 1 \le k \le d \}$$.&#x20;



In simple terms, the **Maximally Entangled** can be written as $$\displaystyle (\frac{1}{\sqrt{d}})*(|0\rangle|0\rangle+|1\rangle|1\rangle+...+|d-1\rangle|d-1\rangle)$$ and can be created using the `MaxEnt_state` function.

```python
# This will create a Macimally Entangled State for a 3 dimensional system.
# The resultant matrix will be of shape 9x9.
MaxEnt_state(3)
```

### Bell State

[`EPR Pairs`](https://en.wikipedia.org/wiki/Bell\_state)

A [Bell state](https://en.wikipedia.org/wiki/Bell\_state) is defined as a [maximally entangled quantum state](states.md#maximally-entangled-state) of two qubits. It can be described as one of four entangled two qubit quantum states, known collectively as the four "[Bell states](https://en.wikipedia.org/wiki/Bell\_state)".

$$\displaystyle |\phi^{+}\rangle \equiv |\phi_{0, 0}\rangle = \frac{1}{\sqrt{2}} (|0, 0\rangle + |1, 1\rangle)$$

$$\displaystyle |\phi^{-}\rangle \equiv |\phi_{1, 0}\rangle = \frac{1}{\sqrt{2}} (|0, 0\rangle - |1, 1\rangle)$$

$$\displaystyle |\psi^{+}\rangle \equiv |\phi_{0, 1}\rangle = \frac{1}{\sqrt{2}} (|0, 1\rangle + |1, 0\rangle)$$

$$\displaystyle |\psi^{-}\rangle \equiv |\phi_{1, 1}\rangle = \frac{1}{\sqrt{2}} (|0, 1\rangle - |1, 0\rangle)$$

A generalized version of the above [Bell States](https://en.wikipedia.org/wiki/Bell\_state) is explained below,&#x20;

Using the operators $$X$$, $$Z$$, and $$ZX$$, we define the following set of four entangled two-qubit state vectors $$\displaystyle |\phi_{z,x}\rangle = (Z^zX^x \otimes I)|\phi^{+}\rangle$$ for $$z, x \in {0, 1}$$.

To generates a $$d$$-dimensional Bell State with $$0 <= z$$, $$x <= d-1$$, we can simply call the module `Bell_state` that was imported above.&#x20;

```python
# This will create a Bell State for a 2 dimensional system.
# The resultant matrix will be of shape 4x4.
Bell_state(d=2, z=1, x=1)
```

### Singlet State <a href="#firstheading" id="firstheading"></a>

A singlet state is defined as  $$\frac{1}{(d^2-d)} \times (I_{(d^2)}-F)$$ where $$F$$ is a Swap Operator.&#x20;

Generating a singlet state is as easy as writing a single word,

```python
# This will create a Singlet State for a 3 dimensional system.
# The resultant matrix will be of shape 9x9.
singlet_state(3)
```

