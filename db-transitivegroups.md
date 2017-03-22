# Database transitivegroups

| | |
|---|---|
|**Description**|Galois groups|
|**Status**|[production](http://www.lmfdb.org/GaloisGroup)|
|**Contact**|[John Jones](https://github.com/jwj61)|
|**Code**|[galois_groups](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/galois_groups)|
|**Collections**|[groups](http://www.lmfdb.org/api/transitivegroups/groups), [Gmodules](http://www.lmfdb.org/api/transitivegroups/Gmodules)|

**Todo**:
* Make the collection groups information prettier

## Collection groups
* **label** (string): label is of the form nTt where n is the degree and t is the "t-number"
* **n** (int): the degree (n from S<sub>n</sub>)
* **t** (int): the t-number, a standard index for conjugacy classes of subgroups of S<sub>n</sub>
* **auts** (int): the number of automorphisms a degree n field with this as its Galois group
* **order** (int): the size of the group
* **parity** (int): 1 if the group is a subgroup of A<sub>n</sub>, otherwise -1
* **cyc** (int): 1 if the group is cyclic, otherwise 0
* **solv** (int): 1 if the group is solvable, otherwise 0
* **subs** (list of pairs [n,t]): if K is a degree n field with this Galois group, this gives the subfields up to isomorphism in terms of their Galois groups
* **repns** (list of pairs [n,t]): if K is a degree n field with this Galois group, this gives other small degree fields with the same Galois closure, up to isomorphism, in terms of their Galois groups
* **arith_equiv** (int): number of arithmetically equivalent fields for number fields with this Galois group
* **resolve** (list of pairs [n,t]):
* **name** (string): the name given by gap (also used by pari, magma, sage, etc)
* **pretty** (string): latex of a nicer name for this group

### Index information for collection groups:
 * {'**_id**': 1}:  mongo internal
 * {'**n**': 1, '**t**': 1}: for Galois group search
 * {'**t**': 1}: for Galois group search

## Collection Gmodules

Each Gmodule is uniqely determined by a Galois group (nTt) and then an
abitrary index.

 * **_id** (): Object id assigned by mongo
<p>**Example**: 53dbc9290eb55b5881ba484f</p>
 * **complete** (int): Do we have complete information, 1 for yes, 0 for no
<p>**Example**: 1</p>
 * **dim** (int): dimension of lattice
<p>**Example**: 1</p>
 * **gens** (pair [string of cycle type, matrix for action]): generators of group and matrix for their actions
<p>**Example**: [['(1,2,3)', [[1]]], ['(1,2)', [[1]]]]</p>
 * **n** (int): for Galois group in form nTt
<p>**Example**: 3</p>
 * **t** (int): for Galois group in form nTt
<p>**Example**: 2</p>
 * **index** (int): index to identify the G-module
<p>**Example**: 0</p>
 * **name** (string): name of this G-module
<p>**Example**: 'Triv'</p>

### Index information for collection Gmodules:
 * {'**_id**': 1}: mongo internal


