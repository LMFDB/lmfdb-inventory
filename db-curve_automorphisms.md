# Database curve_automorphisms

|||
|---|---|
|**Description**|Group actions on higher genus curves|
|**Status**|[alpha](http://beta.lmfdb.org/HigherGenus/C/aut/)|
|**Contact**|[Jen Paulhus](https://github.com/jenpaulhus)|
|**Code**|[higher_genus_w_automorphisms](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/higher_genus_w_automorphisms)|
|**Collections**|[passports](http://beta.lmfdb.org/api/curve_automorphisms/passports)|

**Notes**: families collection has been superseded by passports

**Todo**: 
* Add higher genus data.
* Add equations for curves. 


## Collection passports
* dim: diemnsion of the family of curves
* passport_label: label for the passport (numbered by conjugacy class)
* genus: genus of the family of curves
* gen_vectors: genearting vector for this aciton
* total_label: label including which generating vector
* g0: quotient genus
* label: label for whole family
* r: number of branch points of the cover
* signature: signature (encoded as string)
* group: automorphism group (GAP id encoded as string)
* _id: mongodb generated
 hyperelliptic: True/False whether curve is hyperelliptic
* hyp_inv: hyperellitpic involution if hyperelliptic
* signH: signature of full action
* full_auto: this example is not the full automorphism
* full_label: label for full automorphism group
* cc: ordered pair of integers where first number is which conjgacy class list and second is which generating vector for that conjugacy class list
* con: list of conjugacy classes where the action occurs

#### Indexes on passports collection
* **genus** - search/browse
* **group** - search/browse
* **hyperelliptic** - search/browse
* **signature** - search/brose
* **dim** - search/browse
* **label** - lookup
* **passport_label** - lookup
