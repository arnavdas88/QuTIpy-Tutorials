---
description: The absolute basics for beginners
---

# Overview

## QuTIpy: the absolute basics for beginners

Welcome to the absolute beginner’s guide to QuTIpy! If you have comments or suggestions, please don’t hesitate to [reach out](mailto:khatri6000@gmail.com)!

### Welcome to QuTIpy!

QuTIpy (**Quantum Theory of Information for Python**; pronounced _`/cutiɛ paɪ/`_) is an open source Python library that’s used for performing calculations with quantum states, channels and protocols. While there are many quantum information theory toolboxes that allow the user to perform basic operations such as the [partial transposition](../modules/general-functions.md#firstheading-1), new tests are constantly discovered.

### Installing QuTIpy

To install QuTIpy, we strongly recommend using a scientific Python distribution. If you’re looking for the full instructions for installing QuTIpy on your operating system, see [Installing QuTIpy](installation/install-with-git.md).

If you already have Python, you can install QuTIpy with:

```
$ python -m pip install https://github.com/sumeetkhatri/QuTIpy.git
```

### How to import

To access QuTIpy and its functions import it in your Python code like this:

```python
# Importing necessary dependencies
import cvxpy
import numpy as np
```

```python
# Importing QuTIpy
from qutipy.general_functions import dag, eye, ...
```

We suggest `numpy` and `cvxpy` to be imported as complimentary packages.

### Starting with an example code

We can start with a **Complex Conjugate Transpose** as an example for our demonstration.&#x20;

Let's define an arbitrary matrix. Say `X`:&#x20;

$$
X=\begin{bmatrix}
1 & 2 & 3 & 4 \\
5 & 6 & 7 & 8 \\
9 & 10 & 11 & 12 \\
13 & 14 & 15 & 16
\end{bmatrix}
$$

```python
# Creating an arbitrary matrix
X = np.array(
    [
        [ 1,  2,  3,  4],
        [ 5,  6,  7,  8],
        [ 9, 10, 11, 12],
        [13, 14, 15, 16]
    ]
)
```

Now that we have our matrix `X` defined, we can import the `dag` function from our QuTIpy library and use it to find the complex conjugate transpose of our defined matrix.

```python
from qutipy.general_functions import dag

# getting the complex conjugate transpose of `X`
dag(X)
```

The output will be the Complex Conjugate Transpose of the array X :&#x20;

```python
# Output
np.array([
    [1, 5,  9, 13],
    [2, 6, 10, 14],
    [3, 7, 11, 15],
    [4, 8, 12, 16]
])
```

### Bra-Ket Notation

Let's jump into another common example, **Driac Notation** or [**Bra-Ket Notation**](../modules/general-functions.md#firstheading) as an example for our next demonstration.&#x20;

The _Bra_-_Ket notation_ is a concise and convenient way to describe quantum states.&#x20;

A **Ket** is of the form $${\displaystyle |v\rangle }$$. Mathematically it denotes a [vector](https://en.wikipedia.org/wiki/Vector\_space), $${\displaystyle {\boldsymbol {v}}}$$, in an complex [vector space](https://en.wikipedia.org/wiki/Vector\_space) $${\displaystyle V}$$ , and physically it represents a state of some quantum system. An example of a **Ket** can be $${\displaystyle |r\rangle } = \begin{bmatrix} x \\ y\\ z\end{bmatrix}$$can represent a vector $$\vec{r} = \begin{bmatrix} x \\ y\\ z \end{bmatrix}$$.

A **bra** is of the form $${\displaystyle \langle f|}$$ . Mathematically it denotes a [linear form](https://en.wikipedia.org/wiki/Linear\_form) $${\displaystyle f:V\to \mathbb {C} }$$ , i.e. a [linear map](https://en.wikipedia.org/wiki/Linear\_map) that maps each vector in $${\displaystyle V}$$ to a number in the complex plane $${\displaystyle \mathbb {C} }$$. Letting the linear functional $${\displaystyle \langle f|}$$ act on a vector $${\displaystyle |v\rangle }$$is written as $${\displaystyle \langle f|v\rangle \in \mathbb {C} }$$.

Lets define a **ket** v for$${\displaystyle |v\rangle } = \begin{bmatrix} 1 \\ 0 \end{bmatrix}$$,

To define $${\displaystyle |v\rangle }$$ using numpy, one need to define the vector space as _matrices_ .

```python
import numpy as np

# Define a Ket using numpy
v = np.array([
    [1.],
    [0.]
])
```

But one can directly define $${\displaystyle |v\rangle }$$with QuTIpy.

Example: `ket( 2, 0 )=`$${\displaystyle |0\rangle }$$ and `ket( 2, 1 )=`$${\displaystyle |1\rangle }$$

```python
from qutipy.general_functions import ket

# Define a Ket using QuTIpy
v = ket(2, 0)
```

The `ket` function takes the _**vector space as the first argument**_, and the _**ket value as the second argument**_.&#x20;

Different states of different sizes can be generated based on the arguments.

`ket( 2, 1 )=`$${\displaystyle |01\rangle }$$  `=` $$\begin{bmatrix} 0 \\ 1 \end{bmatrix}$$

`ket( 3, 1 )=`$${\displaystyle |010\rangle }$$`=` $$\begin{bmatrix} 0 \\ 1  \\ 0 \end{bmatrix}$$

{% content-ref url="../modules/general-functions.md" %}
[general-functions.md](../modules/general-functions.md)
{% endcontent-ref %}
