# Database siegel_modular_forms

|||
|---|---|
|**Description**|Siegel modular forms|
|**Status**|[production](http://www.lmfdb.org/ModularForm/GSp/Q/)|
|**Contact**|[Nils Skouruppa](https://github.com/nilsskoruppa)|
|**Code**|[siegel_modular_forms](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/siegel_modular_forms)|
|**Collections**|[dimensions](http://www.lmfdb.org/api/siegel_modular_forms/dimensions), [samples](http://www.lmfdb.org/api/siegel_modular_forms/samples)| 
**Todo**: Add details to samples collection and document dimensions collection

## Collection samples
* **_id**: unique ObjectId assigned by mongo
* **data_type**: string equal to one of "sample", "ev", or "fc"

Records with **data_type** equal to "sample" contain the following additional fields:
* **collection**: array of strings identifying "collections" (not in the mongdo dbs sense) of Siegel modular forms
* **name**: name uniquely identifying the sample within any of the collections it belongs to
* **courtesy_of**: string identifying the source of the sample (e.g. authors and date)
* **degree**: string encoding an integer (currently an element of {2,3,4})
* **degree_of_field**: string encoding the integer degree of field_poly
* **field_poly**: string encoding a monic polynomial f(x) in **Z**[x] defining a number field **Q**(a):=**Q**[x]/(f(x)) (x is used for **Q**)
* **explicit_formular**: string encoding a polynomial in **Q**(a)[A,B,C,D]
* **is_eigenform**: boolean
* **is_integral**: boolean
* **representation**: string encoding an integer (currently an element of {0,2})
* **type**: string describing the type of sample (e.g. "Ikeda lift, cusp form")
* **weight**: string encoding an integer (currently an even integer in [2,58])

Records with **data_type** equal to "ev" (eigenvalue) contain the following additional fields:
* **owner_id**: Object(id) equal to the _id attribute of the sample to which this eigenvalue data belongs
* **index**: string encoding the integer index of the eigenvalue (currently an integer in [2,100]).  This uniquely identifies the eigenvalue among other eigenvalues with the same owner_id.
* **data**: string encoding the eigenvalue as an element of the number field **Q**(a) of the sample (as defined by field_poly)

Records with **data_type** equal to "fc" (Fourier coefficient) contain the following additional fields:
* **owner_id**: Object(id) equal to the _id attribute of the sample to which this Fourier coefficient data belongs
* **det**: string encoding an integer that uniquely identifies this Fourier coefficient data record among others with the same owner_id
* **data**: dictionary whose keys are strings encoding integer vectors and whose values are strings encoding (possibly constant) polynomials in **Q**(a)[x,y]

### Index information for collection samples
* **collection**: search/browse
* **name**: search/browse
* **weight**: search/browse
* **det**: search/browse
* **index**: search/browse
* **data_type**: internal lookup
* **owner_id**: internal lookup

## Collection dimensions
* Field 1: ...
* Field 2: ...

