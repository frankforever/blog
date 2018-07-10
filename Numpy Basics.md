# **Numpy Basics**

```python
import numpy as np

np.flatnonzero()		#返回非零值下标

np.random.choice(a, size=None, replace=True, p=None)	#Generate a uniform random sample from 														np.arange(5) of size 3	

np.reshape(a, newshape, order='C')

np.sqrt(x, /, out=None, *, where=True, casting='same_kind', order='K', dtype=None, subok=True[, 		signature, extobj])
np.square(x, /, out=None, *, where=True, casting='same_kind', order='K', dtype=None, 				subok=True[, signature, extobj])
np.sum(a, axis=None, dtype=None, out=None, keepdims=<class numpy._globals._NoValue>)

np.argsort(a, axis=-1, kind='quicksort', order=None) 	#Returns the indices that would sort an 														array.

np.ndarray.tolist()		#Return the array as a (possibly nested) list.
np.ndarray.flatten(order='C')	#Return a copy of the array collapsed into one dimension.

np.argmax(a, axis=None, out=None)	#Returns the indices of the maximum values along an axis.

np.bincount(x, weights=None, minlength=0)	#Count number of occurrences of each value in array 											of non-negative ints.
```

