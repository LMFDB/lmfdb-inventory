# Database transitivegroups

|||
|---|---|
|**Description**|Galois groups|
|**Status**|[production](http://www.lmfdb.org/GaloisGroup)|
|**Contact**|[John Jones](https://github.com/jwj61)|
|**Code**|[galois_groups](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/galois_groups)|
|**Collections**|[groups](http://www.lmfdb.org/api/transitivegroups/groups), [Gmodules](http://www.lmfdb.org/api/transitivegroups/Gmodules)|

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
* **resolve** (list of pairs [n,t]):
* **name** (string): the name given by gap (also used by pari, magma, sage, etc)
* **pretty** (string): latex of a nicer name for this group

## Collection Gmodules
* Field 1: ...
* Field 2: ...

