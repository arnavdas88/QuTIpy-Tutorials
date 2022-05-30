# Dummy Function Template

### Partial Transpose <a href="#firstheading" id="firstheading"></a>

[`Peres–Horodecki criterion`](https://en.wikipedia.org/wiki/Peres%E2%80%93Horodecki\_criterion)&#x20;

Partial Transpose is a function that computes the partial transpose of a matrix. The transposition may be taken on any subset of the subsystems on which the matrix acts.

Defining a state `X` with \[ ... ]

```python
import numpy as np

X = np.array(
    [
        [1, 2, 3, 4],
        [5, 6, 7, 8],
        [9, 10, 11, 12],
        [13, 14, 15, 16]
    ]
)
```

Now we can apply the `partial_transpose` function over our state `X` :&#x20;

```python
from qutipy.general_functions import partial_transpose

pt = partial_transpose(X, [1], X.shape)
```
