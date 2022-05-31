---
description: In Hilbert Space, nobody can hear you scream...
---

# General Functions

### Hilbert Space <a href="#firstheading" id="firstheading"></a>

[`Hilbert Space`](https://en.wikipedia.org/wiki/Hilbert\_space)

The primary mathematical object in quantum theory is the [Hilbert space](https://en.wikipedia.org/wiki/Hilbert\_space). We consider only finite-dimensional **Hilbert spaces**, denoted by $$\mathcal{H}$$. Although we will be considering _finite-dimensional spaces_ exclusively, we note here that many of the statements and claims extend directly to the case of separable, _infinite-dimensional Hilbert spaces_, especially for operationally-defined tasks and information quantities.

A $$d$$-dimensional Hilbert space $$(1 \le d < \infty)$$ is defined to be a complex vector space equipped with an inner product. We use the notation $${\displaystyle |\psi\rangle}$$to denote a vector in $$\mathcal{H}$$. More generally, a **Hilbert space** is a "**complete inner product**" space.

{% hint style="info" %}
**Completeness** is an issue that pops up only in _infinite-dimensional spaces_, so all _finite-dimensional inner-product spaces_ are **Hilbert spaces**.
{% endhint %}

### Bra-Ket Notation <a href="#firstheading" id="firstheading"></a>

[`Driac's Notation`](https://en.wikipedia.org/wiki/Bra%E2%80%93ket\_notation)

A **ket** is of the form $${\displaystyle |v\rangle }$$ . Mathematically it denotes a [vector](https://en.wikipedia.org/wiki/Vector\_space), $${\displaystyle {\boldsymbol {v}}}$$, in an abstract (complex) [vector space](https://en.wikipedia.org/wiki/Vector\_space) $${\displaystyle V}$$, and physically it represents a state of some quantum system. An example of a **Ket** can be $${\displaystyle |r\rangle } = \begin{bmatrix} x \\ y\\ z\end{bmatrix}$$ represents a vector $${\displaystyle \vec{r} } = \begin{bmatrix} x \\ y\\ z\end{bmatrix}$$.

A **bra** is of the form $${\displaystyle \langle f|}$$. Mathematically it denotes a [linear form](https://en.wikipedia.org/wiki/Linear\_form) $${\displaystyle f:V\to \mathbb {C} }$$, i.e. a [linear map](https://en.wikipedia.org/wiki/Linear\_map) that maps each vector in $${\displaystyle V}$$ to a number in the complex plane $${\displaystyle \mathbb {C} }$$. Letting the linear functional $${\displaystyle \langle f|}$$ act on a vector $${\displaystyle |v\rangle }$$ is written as $${\displaystyle \langle f|v\rangle \in \mathbb {C} }$$. The **bra** is similar to the **ket**, but the values are in a **row**, and each element is the complex [conjugate](https://en.wikipedia.org/wiki/Complex\_conjugate) of the **ket**'s elements.



In the simple case where we consider the vector space  $${\displaystyle \mathbb {C} ^{n}}$$, a **ket** can be identified with a [column vector](https://en.wikipedia.org/wiki/Column\_vector), and a **bra** as a [row vector](https://en.wikipedia.org/wiki/Row\_vector).



#### Meaning :&#x20;

$${\displaystyle \langle A| }=\begin{bmatrix}A_1&A_2&A_3&\dots\end{bmatrix}$$     &     $${\displaystyle |B\rangle }=\begin{bmatrix}B_1\\B_2\\B_3\\\vdots\end{bmatrix}$$

#### Example:

$${\displaystyle |0\rangle }=\begin{bmatrix}1\\0\end{bmatrix}$$,  for two dimensional Hilbert Space ,



Defining a basis state $${\displaystyle |0\rangle }$$, we can use the `ket` module like this:

```python
from qutipy.general_functions import ket

# Defining a ket 0 in a 2Dimensional Hilbert space,
# The first argument takes a dimension of the Hilbert space,
# while the secind argument takes the ket value.
v = ket(2,0)
```

Here we have defined the **ket** v for $${\displaystyle |v\rangle } = \begin{bmatrix} 1 \\ 0 \end{bmatrix}$$. In numpy, defining the same would need one to define the matrix manually, just as shown in the [Overview section](../getting-started/overview.md#bra-ket-notation).

### Partial Transpose <a href="#firstheading" id="firstheading"></a>

[`Peres–Horodecki criterion`](https://en.wikipedia.org/wiki/Peres%E2%80%93Horodecki\_criterion)&#x20;

The Partial Transpose plays an important role in quantum information theory due to its connection with entanglement. In fact, it leads to a sufficient condition for a bipartite state to be entangled.

Given quantum systems $$A$$ and $$B$$, the partial transpose on $$B$$ is denoted by $$T_B\equiv id_A \otimes T_B$$, and it is defined as,&#x20;

$$T_B(X_{AB})  :=  \sum\limits^{d_B-1}_{j, j'=0}   (\mathbf{1}_A  \otimes  \ket{i}\bra{i'}_B)  X_{AB}  (\mathbf{1}_A  \otimes  \ket{i}\bra{i'}_B)$$



`partial_transpose(...)` is a function that computes the partial transpose of a matrix. The transposition may be taken on any subset of the subsystems on which the matrix acts.&#x20;

Defining a state `X` with \[ ... ]

```python
import numpy as np

X = np.array(
    [
        [ 1,  2,  3,  4],
        [ 5,  6,  7,  8],
        [ 9, 10, 11, 12],
        [13, 14, 15, 16]
    ]
)
```

Now we can apply the `partial_transpose` function over our state `X` :&#x20;

```python
from qutipy.general_functions import partial_transpose

pt = partial_transpose(X, [1], X.shape)
```

