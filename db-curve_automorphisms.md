# Database curve_automorphisms

|||
|---|---|
|**Description**|Group actions on higher genus curves|
|**Status**|development|
|**Contact**|[Jen Paulhus](https://github.com/jenpaulhus)|
|**Code**|[higher_genus_w_automorphisms](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/higher_genus_w_automorphisms)|
|**Collections**|[families](http://www.lmfdb.org/api/curve_automorphisms/families)|

**Notes**:  Collection families is the data for the released version, Collection passports is the data for the proposed changes to these pages.   Eventually passport will probably replace families

**Todo**: 
* Add higher genus data.
* Add equations for curves. 


## Collection families
* dim: dimension of the family of curves
* genus: genus of the family of curves
* gen_vectors: generating vector for this action
* label: label of action
* r:  number of branch points of the cover
* g0: quotient genus
* signature: signature
* group: automorphism group
* _id: mongodb defined id
* hyperelliptic: True/False whether curve is hyperelliptic
* hyp_inv: hyperellitpic involution if hyperelliptic
* eqn: model for family
* signH: signature of full action
* full_auto: this example is not the full automorphism
* full_label: label for full automorphism group

## Indexes
*{'_id':1} (created by mongo db)


## Collection passports
* dim: diemnsion of the family of curves
* passport_label: label for the passport (numbered by conjugacy class)
* genus: genus of the family of curves
* gen_vectors: genearting vector for this aciton
* total_label: label including which generating vector
* g0: quotient genus
* label: label for whole family
* r: number of branch points of the cover
* signature: signature
* group: automorphism group
* _id: mongodb generated
 hyperelliptic: True/False whether curve is hyperelliptic
* hyp_inv: hyperellitpic involution if hyperelliptic
* signH: signature of full action
* full_auto: this example is not the full automorphism
* full_label: label for full automorphism group
* cc: ordered pair of integers where first number is which conjgacy class list and second is which generating vector for that conjugacy class list
* con: list of conjugacy classes where the action occurs


## Indexes
{'_id':1} (created by mongo db)

