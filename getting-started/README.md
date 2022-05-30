---
description: >-
  QuTIpy (Quantum Theory of Information for Python; pronounced /cutiɛ paɪ/) is
  an open source library that makes performing calculations with quantum states,
  channels and protocols, quick and easy.
---

# Getting Started

QuTIpy (**Quantum Theory of Information for Python**; pronounced _`/cutiɛ paɪ/`_) is an open source Python library that’s used for performing calculations with quantum states and channels. While there are many quantum information theory toolboxes that allow the user to perform basic operations such as the [partial transposition](../modules/general-functions.md#firstheading), new tests are constantly discovered.



The core of QuTIpy package is a suite of mathematical functions that make working with quantum states, channels and protocols, quick and easy.

Calculating things like **Normalized Trace Distances** between Quantum States could be as easy as

```python
from qutipy.distance_measures import norm_trace_dist

# Calculating Normalized Trace Distance between
# Quantum State X and Quantum State Y
norm_trace_dist(X, Y)
```

QuTIpy also provides generic gates like $$H$$ and $$R_x$$which are as easy as calling a function

```python
from qutipy.gates import H_i, Rx_i

# Applying Hadamard Gate to the 2nd qubit in a 5 qubit system
H_i(1, 5)

# Applying Rx(0.2) Gate to the 2nd qubit in a 5 qubit system
Rx_i(1, 0.2, 5)
```



### Principles of Quantum Communication Theory: A Modern Approach <a href="#principles-of-quantum-communication-theory" id="principles-of-quantum-communication-theory"></a>

By [**Sumeet Khatri**](https://sumeetkhatri.com/) and [**Mark M. Wilde**](https://www.markwilde.com/)****

This is a preliminary version of a book in progress on the theory of quantum communication. We adopt an information-theoretic perspective throughout and give a comprehensive account of fundamental results in quantum communication theory from the past decade (and earlier), with an emphasis on the modern one-shot-to-asymptotic approach that underlies much of today's state-of-the-art research in this field.&#x20;

In Part I, we cover mathematical preliminaries and provide a detailed study of quantum mechanics from an information-theoretic perspective. We also provide an extensive and thorough review of the quantum entropy zoo, and we devote an entire chapter to the study of entanglement measures. Equipped with these essential tools.

In Part II we study classical communication (with and without entanglement assistance), entanglement distillation, quantum communication, secret key distillation, and private communication.&#x20;

In Part III, we cover the latest developments in feedback-assisted communication tasks, such as quantum and classical feedback-assisted communication, LOCC-assisted quantum communication, and secret key agreement.

{% embed url="https://arxiv.org/abs/2011.04672" %}
By [Sumeet Khatri](https://arxiv.org/search/quant-ph?searchtype=author\&query=Khatri%2C+S) and [Mark M. Wilde](https://arxiv.org/search/quant-ph?searchtype=author\&query=Wilde%2C+M+M)
{% endembed %}
