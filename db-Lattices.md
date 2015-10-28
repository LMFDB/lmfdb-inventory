# Database Lattices

Status:

Contact/Maintainer:

Description:

Todo:
* ...


## Collection lat
* **aut** (int): size of automorphism group
* **base_label** (string): part of the **label** which is completely deterministic
* Field 3: name = class_number; description = class number or genus of a lattice; type = int;
* Field 4: name = comments; description = comments and historical remarks; type = string;
* Field 5: name = density; description = density; type = string;
* Field 6: name = det; description = determinant; type = int;
* Field 7: name = dim; description = dimension; type = int;
* Field 8: name = genus_reps; description = list of genus representatives (matrices); type = list of list of lists with int entries;
* Field 9: name = gram; description = Gram matrix; type = list of lists integers ;
* Field 10: name = hermite; description = Hermite number; type = string;
* Field 11: name = index; description = index; type = int;
* Field 13: name = kissing; description = Kissing number; type = int;
* Field 14: name = label; description = LMFDB label; type = string;
* Field 15: name = level; description = level; type = int;
* Field 16: name = minimum; description = lenght of the shortest vector; type = int;
* Field 17: name = name; description = name of a lattice; type = string;
* Field 18: name = shortest; description = list of shortest vestors; dimension; type = list of lists of integers;
* Field 19: name = theta_series; description = q-expansion of the associated theta series; type = list of integers;

### One example of lat

```
  {
    "_id": "562cf752ffe979688b0a1f15", 
    "aut": 12, 
    "base_label": "2.3.3.1", 
    "class_number": 1, 
    "comments": "This is the $A2$ root lattice, also called the hexagonal lattice or triangular lattice", 
    "density": "0.906899682117108925297039128820", 
    "det": 3, 
    "dim": 2, 
    "genus_reps": [
      [
        [
          2, 
          1
        ], 
        [
          1, 
          2
        ]
      ]
    ], 
    "gram": [
      [
        2, 
        -1
      ], 
      [
        -1, 
        2
      ]
    ], 
    "hermite": "1.15470053837925152901829756100", 
    "index": 1, 
    "kissing": 6, 
    "label": "2.3.3.1.1", 
    "level": 3, 
    "minimum": 2, 
    "name": "A2", 
    "shortest": [
      [
        1, 
        0
      ], 
      [
        1, 
        1
      ], 
      [
        0, 
        1
      ]
    ], 
    "theta_series": [
      1, 
      0, 
      6, 
      0, 
      0, 
      0, 
      6, 
      0, 
      6, 
      0, 
      0, 
      0, 
      0, 
      0, 
      12, 
      0, 
      0, 
      0, 
      6, 
      0, 
      0, 
      0, 
      0, 
      0, 
      6, 
      0, 
      12, 
      0, 
      0, 
      0, 
      0, 
      0, 
      6, 
      0, 
      0, 
      0, 
      0, 
      0, 
      12, 
      0, 
      0, 
      0, 
      12, 
      0, 
      0, 
      0, 
      0, 
      0, 
      0, 
      0, 
      6, 
      0, 
      0, 
      0, 
      6, 
      0, 
      12, 
      0, 
      0, 
      0, 
      0, 
      0, 
      12, 
      0, 
      0, 
      0, 
      0, 
      0, 
      0, 
      0, 
      0, 
      0, 
      6, 
      0, 
      12, 
      0, 
      0, 
      0, 
      12, 
      0, 
      0, 
      0, 
      0, 
      0, 
      0, 
      0, 
      12, 
      0, 
      0, 
      0, 
      0, 
      0, 
      0, 
      0, 
      0, 
      0, 
      6, 
      0, 
      18, 
      0, 
      0, 
      0, 
      0, 
      0, 
      12, 
      0, 
      0, 
      0, 
      0, 
      0, 
      0, 
      0, 
      0, 
      0, 
      12, 
      0,
      0, 
      0, 
      0, 
      0, 
      0, 
      0, 
      12, 
      0, 
      0, 
      0, 
      12, 
      0, 
      6, 
      0, 
      0, 
      0, 
      0, 
      0, 
      12, 
      0, 
      0, 
      0, 
      0, 
      0, 
      0, 
      0, 
      0, 
      0, 
      0, 
      0, 
      12, 
      0, 
      0, 
      0, 
      6
    ]
  }
```
