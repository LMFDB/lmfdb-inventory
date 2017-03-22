# Database Lfunctions

| | |
|---|---|
|**Description**|L-functions|
|**Status**|[production](http://www.lmfdb.org/L/)|
|**Contact**|[Jonathan Bober](https://github.com/jwbober), [David Farmer](https://github.com/davidfarmer)|
|**Code**|[lfunctions](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/lfunctions)|
|**Collections**|[instances](http://www.lmfdb.org/api/Lfunctions/instances), [Lfunctions](http://www.lmfdb.org/api/Lfunctions/Lfunctions)|

**Todo**: Document indexes for Lfunctions (some appear to be obsolete or never used)

## Collection instances

| Field | type | Example|
|----------|    ------     | -----   |
|`url`| string | 'EllipticCurve/Q/162/d'|
|`Lhash`| string |    | 
|`type`| string | 'ECQ' or 'G2Q' or 'DIR' or ...|

Indexes for instances collection:
* **Lhash**: lookup by L-function hash (used to find all objects with the same L-function)
* **url**: lookup by object homepage URL
* **type**: used to filter instances by type

## Collection Lfunctions
| Field | type | Example|
|-------|------|--------|
|`origin`         | string      | 'EllipticCurve/Q/162/d' |
|`load_key`       | string      | 'cremona'               |
|`Lhash`          | string      | ?                       |
|`conductor`      | integer     |   162                   |
|`degree`         | integer     | 2 |
|`motivic_weight` | integer     | 1 |
|`gamma_factors`  | a pair of lists of numbers the first list being the `Gamma_R` shifts, and the second list being the `Gamma_C` shifts. store, e.g., '1/2' if exact. | [[],[0]] |
|`primitive`      | boolean     | True  |
|`root_number`    | number      | 1     |
|`sign_arg`       | number      | 0     |
|`central_character` | string (conrey label) | '162.1' |
|`self_dual`      | bool        | True |
|`conjugate`      | string (the `Lhash`) entry of the conjugate |  |
|`symmetry_type`  | string      | 'unitary' or 'orthogonal' or 'symplectic' |
|`algebraic`      | bool        | True
|`leading_term`   | number      | 1.736780166943524 |
|`values`         | list of pairs of numbers (optional) | [] |
|`euler_factors`  | list of lists (little endian polynomials) | [[1, -1], [1], [1, -3, 5], [1, 4, 7], ...] |
|`bad_lfactors`   | list of pairs (number, list(polynomial))  | [[2, [1, -1]], [3, [1]]] |
|`dirichlet_coefficients`| list of numbers (optional) |
|`st_group`       | string                                    | 'SU(2)' |
|`types`          | list of strings ('EC', 'MF', 'DIR', 'G2'...?) | ['EC', 'MF'] |
|`order_of_vanishing` | integer | 0 |
|`coefficient_field`  | string (a field label or description)     | '1.1.1.1' |
|`analytic_normalization` | number                                |.5 |
|`positive_zeros`     | list of (strictly positive) numbers       | [...]
|`plot_delta`         | number (float expected) |
|`plot_values`        | list of numbers (floats expected), which are values of Z(k * plot_delta) for k = 0, 1, 2, ... |
|`z1`             | float (imaginary part of the first positive zero) | 
|`z2`             | float (imaginary part of the second positive zero)|
|`z3`             | float (imaginary part of the third positive zero) |
|`a2`                 | pair of floats (a complex number), the embedding of the 2nd dirichlet coefficient in the analytic normalization|
|`a3`                 | pair of floats |
|...|...|
|`a9`                 | pair of floats |
|`a10`                | pair of floats |
|`A2`                 | string (integer in arithmetic normalization)|
|`A3`                 | string |
|...|...|
|`A9`                 | string |
|`A10`                | string |
