# Database Lattices

Status: Work in progress, on beta: beta.lmfdb.org/Lattice hidden link

Contact/Maintainer: Samuele Anni 

Description: Database of integral lattices

Contributors: Samuele Anni, Anna Haensch, Gabriele Nebe and Neil Sloane

The data is coming from [here](https://github.com/annahaensch/lattice_data).

Todo:
* add L series for even dimensional lattices using the new avaliable pari functionalities
* upload all the data from [here](https://github.com/annahaensch/lattice_data).

## Collection lat
* **aut** (int): size of automorphism group
* **base_label** (string): part of the **label** which is completely deterministic
* **class_number** (int): class number or genus of a lattice
* **comments** (string): comments and historical remarks
* **density** (string): density of a lattice
* **det** (int): determinant of a lattice
* **dim** (int): dimension of a lattice
* **genus_reps** (list of matrices with int entries): list of genus representatives (matrices)
* **gram** (matrix with int entries): Gram matrix of a lattice
* **hermite**(string): Hermite number of a lattice
* **index** (int): index of a lattice
* **kissing**(int): Kissing number of a lattice
* **label**(string): LMFDB label of a lattice
* **level**(int): level of a lattice
* **minimum**(int): lenght of the shortest vector
* **name**(list of strings): list of known names of a given lattice
* **shortest** (list of vectors of int): list of shortest vectors*
* **theta_series** (list of int): coefficients of the q-expansion of the theta series associated to a lattice*

*for the Leech lattice it is a list of strings

## LMFDB label of an integral lattice in lat

The LMFDB label has the following structure:

    dimension.determinant.level.class_number.number

the first 4 parameters are uniquely defined, given a lattice, the last is depending on the ordering we compute/upload the data

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
    "name": ["A2"], 
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
