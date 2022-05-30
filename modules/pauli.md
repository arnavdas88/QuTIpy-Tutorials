---
description: >-
  In mathematical physics and mathematics, the Pauli matrices are a set of three
  2 × 2 complex matrices which are Hermitian, involutory and unitary.
---

# Pauli



The [Pauli matrices,](https://en.wikipedia.org/wiki/Pauli\_matrices) also called the Pauli spin matrices, are complex matrices that arise in Pauli's treatment of spin in quantum mechanics. They are defined by:

$$\sigma_1 = \sigma_x = \begin{bmatrix} 0 && 1 \\ 1 && 0 \end{bmatrix}$$

$$\sigma_2 = \sigma_y = \begin{bmatrix} 0 && -i \\ i && 0 \end{bmatrix}$$

$$\sigma_3 = \sigma_z = \begin{bmatrix} 1 && 0 \\ 0 && -1 \end{bmatrix}$$

In [quantum mechanics](https://en.wikipedia.org/wiki/Quantum\_mechanics), pauli matrices occur in the [Pauli equation](https://en.wikipedia.org/wiki/Pauli\_equation) which takes into account the interaction of the [spin](https://en.wikipedia.org/wiki/Spin\_\(physics\)) of a particle with an external [electromagnetic field](https://en.wikipedia.org/wiki/Electromagnetic\_field).&#x20;

{% hint style="info" %}
_Pauli matrices_ also represent the interaction states of two polarization filters for horizontal / vertical polarization, 45º polarization, and circular polarization.
{% endhint %}

Each Pauli matrix is [Hermitian](https://en.wikipedia.org/wiki/Hermitian\_matrix), and together with the identity matrix $$I$$, the Pauli matrices form a [basis](https://en.wikipedia.org/wiki/Basis\_\(linear\_algebra\)) for the real [vector space](https://en.wikipedia.org/wiki/Vector\_space) of 2 × 2 Hermitian matrices. This means that any 2 × 2 [Hermitian matrix](https://en.wikipedia.org/wiki/Hermitian\_matrix) can be written in a unique way as a linear combination of Pauli matrices, with all coefficients being real numbers.

{% hint style="info" %}
The identity matrix $$I$$ is sometimes considered as the zero$$^{th}$$ Pauli matrix or $$\sigma_0$$
{% endhint %}



The Pauli matrices are important in the context of quantum mechanics, and [quantum information](https://en.wikipedia.org/wiki/Quantum\_information) more generally, as they can be used to describe the quantum states, as well as the evolution of the quantum states, of 2 Dimensional quantum systems, called [qubits](https://en.wikipedia.org/wiki/Qubit). They are also involved in fundamental quantum information processing protocols such as [quantum teleportation](https://en.wikipedia.org/wiki/Quantum\_teleportation).

### Pauli&#x20;

[`Pauli Metrices`](https://en.wikipedia.org/wiki/Pauli\_matrices)

Generating Pauli-X for `n` qubits,

To define $$X = \sigma_x( 111 )$$ using numpy, one need to define the entire _matrix_ .

```python
import numpy as np

# Define Pauli-X for [ 1 1 1 ] using numpy
X = np.array([
       [0, 0, 0, 0, 0, 0, 0, 1],
       [0, 0, 0, 0, 0, 0, 1, 0],
       [0, 0, 0, 0, 0, 1, 0, 0],
       [0, 0, 0, 0, 1, 0, 0, 0],
       [0, 0, 0, 1, 0, 0, 0, 0],
       [0, 0, 1, 0, 0, 0, 0, 0],
       [0, 1, 0, 0, 0, 0, 0, 0],
       [1, 0, 0, 0, 0, 0, 0, 0]
])
```

These kind of definition for $$X = \sigma_x( 111 )$$ can be obtained easily using QuTIpy.

```python
from qutipy.Pauli import generate_nQubit_Pauli_X

# Define Pauli-X for [ 1 1 1 ] using qutipy
X = generate_nQubit_Pauli_X([1, 1, 1])
```
