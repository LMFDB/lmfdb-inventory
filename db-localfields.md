# Database localfields

| | |
|---|---|
|**Description**|Local number fields|
|**Status**|[production](http://www.lmfdb.org/LocalField)|
|**Contact**|[John Jones](https://github.com/jwj61)|
|**Code**|[local_fields](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/local_fields)|
|**Collections**|[fields](http://www.lmfdb.org/api/local_fields/fields)|

**Todo:**
* Extend range?


## Collection fields
 * **_id**: Assigned by mongo

  **Example**: ObjectId('4e6647840eb55b3887000003')
 * **n** (integer): degree

  **Example**: 6
 * **p** (integer): prime p for the base \Q_p

  **Example**: 11
 * **e** (integer): ramification degree

  **Example**: 3
 * **f** (integer): residue field degree

  **Example**: 2
 * **c** (integer): valuation of the discriminant

  **Example**: 4
 * **label** (string): label

  **Example**: '11.6.4.1'
 * **coeffs** (list of integers): coefficients of a defining polynomial, starting with the constant term

  **Example**: [41503, 0, 0, 220, 0, 0, 1]
 * **aut** (integer): number of automorphisms of the field

  **Example**: 6
 * **gal** (pair of integers): the Galois group [n, t] for nTt

  **Example**: [6, 2]
 * **galT** (integer): the T-number for the Galois group

  **Example**: 2
 * **inertia** (four-tuple, degree, whether it is transitive or not, the pair [d,t] for the degree and t-number if transitive, and optionally an html display string): inertia subgroup

  **Example**: [3, 'i', [3, 1], '<i>C</i><sub>3</sub>']
 * **slopes** (list of rational numbers as string): wild ramification slopes

  **Example**: '[]'
 * **t** (integer): tame degree for the Galois closure

  **Example**: 3
 * **u** (integer): degree of maximal unramified subfield of the Galois closure

  **Example**: 2
 * **gms** (rational number as string): Galois mean slope

  **Example**: '2/3'
 * **hw** (TeX string): Hasse-Witt invariant as a string

  **Example**: '$1$'
 * **rf** (pair of integers): root field

  **Example**: [1, 1]
 * **unram** (polynomial in t as a string): polynomial defining maximal unramified subfield

  **Example**: 't^2 - t + 7'
 * **eisen** (polynomial as string, in variable y over Q_p(t)): Eisenstein polynomial defining relative extension of this field over the maxmial unramified subfield

  **Example**: 'y^3 - 11*t^3'

### Index information for collection fields
 * {'**_id**': 1}: Created by mongo
 * {'**e**': 1}: search by ramification index
 * {'**f**': 1}: search by residue field degree
 * {'**label**': 1}: search by label
 * {'**metadata**': 1}: Created by mongo
 * {'**n**': 1}: search by degree
 * {'**p**': 1}: search by prime
 * {'**p**': 1,'**n**': 1}: search by prime and degree
