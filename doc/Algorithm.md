# Algorithm

The basic algorithm that we adopted currently is point double and addition.

## Double and Add
The Double-and-Add algorithm represents each scalar :math:`S_n` in its binary form :math:`S_n[i], i \in [0, Pre]`, where :math:`Pre` is the bit-length of the scalar. The MSM computation is expressed as:  

```{math}
\textit{final\_result} = \sum_{n=0}^{N} \sum_{i=0}^{Pre} (S_n[i] == 1) \times 2^i P_n.
``` 

Here, the basis points :math:`2^i P_n` are precomputed and stored offline. During runtime, only the basis points corresponding to the non-zero bits in the binary representation of :math:`S_n` are loaded for accumulation.  

While simple to implement, the Double-and-Add algorithm lacks data reuse, as scalar values exhibit minimal overlap in practice, even for large datasets (e.g., :math:`N = 2^{27} ` for :math:`2^{256}` possible 256-bit scalars). 



<!-- 
## Table

| No.  |  Prime |
| ---- | ------ |
| 1    |  No    |
| 2    |  Yes   |
| 3    |  Yes   |
| 4    |  No    |



## Code blocks

The following is a Python code block:
```python
  def hello():
      print("Hello world")
```

And this is a C code block:
```c
#include <stdio.h>
int main()
{
    printf("Hello, World!");
    return 0;
}
```


## Math

This creates an equation:
```{math}
a^2 + b^2 = c^2
```

This is an in-line equation, {math}`a^2 + b^2 = c^2`, embedded in text. -->
