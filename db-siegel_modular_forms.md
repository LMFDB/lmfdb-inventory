# Database siegel_modular_forms

| | |
|---|---|
|**Description**|Siegel modular forms|
|**Status**|[production](http://www.lmfdb.org/ModularForm/GSp/Q/)|
|**Contact**|[Nils Skouruppa](https://github.com/nilsskoruppa), [Andrew Sutherland](https://github.com/AndrewVSutherland)|
|**Code**|[siegel_modular_forms](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/siegel_modular_forms)|
|**Collections**|[dimensions](http://www.lmfdb.org/api/siegel_modular_forms/dimensions), [samples](http://www.lmfdb.org/api/siegel_modular_forms/samples), [families](http://www.lmfdb.org/api/siegel_modular_forms/families)| 
**Todo**: Add details expanding on utilitarian descriptions below

## Collection samples
* **_id**: ObjectId assigned by mongo db (referenced by owner_id below, must not change when moving/copying)
* **data_type**: string equal to one of "sample", "ev", or "fc"

Records with **data_type** equal to "sample" contain the following additional fields:
* **collection**: array of strings identifying families of spaces of Siegel modular forms that contain this sample (the families currently defined are not disjoint, so the same sample may appear in multiple families)
* **name**: name uniquely identifying the sample within any of the collections it belongs to
* **courtesy_of**: string identifying the source of the sample (e.g. authors and date)
* **deg**: integer degree of the form (forms on M_k(Sp(2d)) have degree d, currently we have samples for d=2,3,4)
* **fdeg**: integer degree of field_poly (current an integer in [1..29])
* **field_poly**: string encoding a monic polynomial f(x) in **Z**[x] defining a number field **Q**(a):=**Q**[x]/(f(x)) (x is used for **Q**)
* **explicit_formula**: string encoding a polynomial in **Q**(a)[A,B,C,D]
* **is_eigenform**: boolean
* **is_integral**: boolean
* **representation**: string encoding an integer (currently an element of {0,2})
* **data_type**: string describing the type of sample (e.g. "Ikeda lift, cusp form")
* **wt**: integer weight (currently an even integer in [2,58])

Records with **data_type** equal to "ev" (eigenvalue) contain the following additional fields:
* **owner_id**: Object(id) equal to the _id attribute of the sample to which this eigenvalue data belongs
* **index**: string encoding the integer index of the eigenvalue (currently an integer in [2..100]).  This uniquely identifies the eigenvalue among other eigenvalues with the same owner_id.
* **data**: string encoding the eigenvalue as an element of the number field **Q**(a) of the sample (as defined by field_poly)

Records with **data_type** equal to "fc" (Fourier coefficient) contain the following additional fields:
* **owner_id**: Object(id) equal to the _id attribute of the sample to which this Fourier coefficient data belongs
* **det**: string encoding an integer that uniquely identifies this Fourier coefficient data record among others with the same owner_id (currently an integer in [0..2999])
* **data**: dictionary whose keys are strings encoding integer vectors and whose values are strings encoding (possibly constant) polynomials in **Q**(a)[x,y]

### Index information for collection samples
* **collection**: search/browse
* **name**: search/browse
* **weight**: search/browse
* **degree**: search/browse
* **degree_of_field**: search/browse
* **det**: search/browse
* **index**: search/browse
* **data_type**: internal lookup
* **owner_id**: internal lookup

## Collection dimensions
* **_id**: ObjectId assigned by mongo db
* **title**: string (currently always set to "Hilbert Poincare series")
* **group**: name of the modular group, string (currently always "Gamma(2)")
* **description**: string describing the space
* **space**: string describing the type of the space (either "total" or "cusp")
* **sym_power**: string encoding a nonnegative even integer (currently in [0,100])
* **note**: string containing a latex note
* **author**: string naming the author(s)
* **111111**: string encoding a rational function in **Q**(t)
* **21111**: string encoding a rational function in **Q**(t)
* **2211**: string encoding a rational function in **Q**(t)
* **222**: string encoding a rational function in **Q**(t)
* **3111**: string encoding a rational function in **Q**(t)
* **321**: string encoding a rational function in **Q**(t)
* **33**: string encoding a rational function in **Q**(t)
* **411**: string encoding a rational function in **Q**(t)
* **42**: string encoding a rational function in **Q**(t)
* **51**: string encoding a rational function in **Q**(t)
* **6**: string encoding a rational function in **Q**(t)

### Index information for collection dimensions
* **sym_power**: search/browse
* **group**: search/browse
* **space**: search/browse

## Collection families
* **_id**: ObjectedId assigned by mongo db
* **name**: string identifying the family (e.g. "Sp4Z")
* **degree*: integer degree of the famly (currently 2, 3, or 4)
* **latex_name**: latex string for displaying the name
* **order**: integer used to control the ordering of the families for display purposes
* **dim_args_default**: for families with dimension formulas, a dictionary with default values for k and j

### Index information for families
* **name** search/lookup
* **order** browsing
