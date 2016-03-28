# Database Lfunctions

Status:

Contact/Maintainer: Jonathan Bober

Description:

Todo:
* ...


## Collection first_zeros_testing
* To delete...

## Collection full_collection
* ???...

## Collection Lfunctions
| Field | type | Example|
|-------|------|--------|
|`origin`         | string      | 'EllipticCurve/Q/162/d' |
|`conductor`      | integer     |   162                   |
|`degree`         | integer     | 2 |
|`motivic_weight` | integer     | 1 |
|`gamma_factors`  | a pair of lists of numbers the first list being the `Gamma_R` shifts, and the second list being the `Gamma_C` shifts. store, e.g., '1/2' if exact. | [[],[0]] |
|`primitive`      | boolean     | True  |
|`root_number`    | number      | 1     |
|`sign_arg`       | number      | 0     |
|`central_character` | string (conrey label) | '162.1' |
|`self_dual`      | bool        | True |
|`symmetry_type`  | string      | 'unitary' or 'orthogonal' or 'symplectic' |
|`algebraic`      | bool        | True
|`instances`      | list of strings | ['EllipticCurve/Q/162/d', 'ModularForms/GL2/Q/holomorphic/162/2/1/d'] |
|`leading_term`   | number      | 1.736780166943524 |
|`values`         | list of pairs of numbers (optional) | [] |
|`euler_factors`  | list of lists (little endian polynomials) | [[1, -1], [1], [1, -3, 5], [1, 4, 7], ...] |
|`bad_lfactors`   | list of pairs (number, list(polynomial))  | [[2, [1, -1]], [3, [1]]] |
|`st_group`       | string                                    | 'SU(2)' |
|`types`          | list of strings ('EC', 'MF', 'DIR', 'G2'...?) | ['EC', 'MF'] |
|`order_of_vanishing` | integer | 0 |
|`coefficient_field`  | string (a field label or description)     | '1.1.1.1' |
|`hash`               | integer                                   | 1795737022127482060 |
|`analytic_normalization` | number                                |.5 |
|`positive_zeros`     | list of (strictly positive) numbers       | [...]
|`plot_delta`         | number (float expected) |
|`plot_values`        | list of numbers (floats expected) |
|`gamma1`             | float     |
|`gamma2`             | float     |
|`gamma3`             | float     |
|`a2`                 | pair of floats |
|`a3`                 | pair of floats |
|`a4`                 | pair of floats |
