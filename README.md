Sageball
========

Sageball is an extension of SageMath with additional functionalities.

**It should be imported in a sagemath script.**

Author: pikaball (whitesworder@gmail.com)

install:
```python
    pip install sageball
```

Currently Implemented Functionalities:
---------------------------------------
+ `hensel_solve(f,p,r)`: solve polynomial roots on $GF(p^r)$ using Hensel's lifting method


Usage:
---------------------------------------
```python
    sage: from sageball import *
    sage: from Crypto.Util.number import *
    sage: p = getPrime(256)
    sage: R.<y> = PolynomialRing(Zmod(p**20))
    sage: f = y^3 + 88*y^2 - 99999
    sage: assert(len(f.change_ring(Zmod(p)).roots())!=0)
    sage: x = hensel_solve(f, p, 20)
    sage: assert(f(x[0]) == 0)
```