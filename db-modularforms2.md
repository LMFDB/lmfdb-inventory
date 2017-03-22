# Database modularforms2

| | |
|---|---|
|**Description**|Classical modular forms|
|**Status**|[production](http://www.lmfdb.org/ModularForm/GL2/Q/holomorphic/)|
|**Contact**|[Stefan Ehlen](https://github.com/sehlen), [Fredrik Strömberg](https://github.com/fredstro)|
|**Code**|[modular_forms/elliptic_modular_forms](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/modular_forms/elliptic_modular_forms)|
|**Collections**|[dimension_table](http://www.lmfdb.org/api/modularforms2/dimension_table), [webchar](http://www.lmfdb.org/api/modularforms2/webchar), [webchar.files](http://www.lmfdb.org/api/modularforms2/webchar.files), [webmodformspace](http://www.lmfdb.org/api/modularforms2/webnewforms), [webnewformspace.files](http://www.lmfdb.org/api/modularforms2/webmodformspace.files), [webnewforms](http://www.lmfdb.org/api/modularforms2/webnewforms), [webnewforms.files](http://www.lmfdb.org/api/modularforms2/webnewforms.files), [webeigenvalues](http://www.lmfdb.org/api/modularforms2/webeigenvalues), [webeigenvalues.files](http://www.lmfdb.org/api/modularforms2/webeigenvalues.files)|
|**Other data**| [Atkin_Lehner.files](http://beta.lmfdb.org/api/modularforms2/AtkinLehner.files), [Modular_symbols.files](http://beta.lmfdb.org/api/modularforms2/Modular_symbols.files), [Newform_factors.files](http://beta.lmfdb.org/api/modularforms2/Newform_factors.files), [ap.files](http://beta.lmfdb.org/api/modularforms2/ap.files), [vector_on_basis.files](http://beta.lmfdb.org/api/vector_on_basis.files)|

## General notes
* All collections contain the field `_id` which is an object of the type bson.ObjectId and uniquely identifies the record in the database. 
* All collections with names ending with .chunks contain chunks of files for GridFS for the corresponding collection with name ending with .files and will not be further described.
* All collections with names ending with .files contain data for GridFS files and will (or at least *should*) all contain the following fields (which will not be repeted below except 'filename' which has a different format in each collection):

| Field | type | Example| Description |
|-------|------|--------|---------------|
| `_id` | bson.ObjectId | ObjectId('52daa5560964b55ea2a516ec')| Unique id|
| `chunkSize` | integer | 261120 |  size of associated chunks |
| `length` | integer |  408 | length of the file in bytes |
| `md5`:  |  string | '7828b070ebd9a49aacd950f8e621267a' | has of the file |
| `uploadDate` | datetime | datetime.datetime(2014, 9, 10, 13, 52, 20, 258000)} | date this file was uploaded |
| `filename` | string  | `atkin_lehner_evs-   17-  2-  0-  0` | filename in gridfs |
 

## Collection dimension_table
    Description: Dimension data for modular forms. 
This collection contains two types of records: 
#### Gamma1
| Field | type | Example| Description
|-------|------|--------|---------------|
| `level` | integer | 29 | level
| `weight` | integer |6 | weight
| `d_eis` | integer | 28 | The dimension of the space of Eisenstein series E_k(Gamma_1(N))
| `d_mod` |  integer | 189| The dimension of the space of all modular forms  M_k(Gamma_1(N))
| `d_newf` | integer|  integer | 161 | The dimension of the space of all cuspidal newforms in S_k(Gamma_1(N))
| `gamma1_label` | string | '29.6' | A label for the space, of the form level.weight
| `all_in_db`| bool | True | True if the spaces S_k^{new}(N,chi) for all chi are in the db, False otherwise
| `one_in_wdb` | bool |  True | True if at least one of these spaces is in the db
#### Gamma0 with character
| Field | type | Example| Description
|-------|------|--------|---------------|
|   `cchi` | integer | 9 | Conrey character number |
|   `character_orbit` | list |  [9, 11] | List of conrey character numbers of elements of the orbits of 'cchi'|
|   `character_orbit_rep` | integer | 9 | The number of the representative of the Galois orbit |
|  `character_parity` | integer | 1 | '1' if the character is even and '-1' if it is odd |
|  `d_cusp` | integer |  24 | Dimension of space of cusp forms S_k(N, chi), where N is the level, chi is the character specified by cchi. |
|  `d_eis` |  integer | 4 | Dimension of  Eisenstein series E_k(N,chi) |
|  `d_mod` | integer | 28 | Dimension of modular forms M_k(N,chi) |
|  `d_newf` | integer | 8 | Dimension of (cuspidal) newforms in S_k(N,chi)|  
|  `in_msdb` | integer | 1 | Equals 1 if this space has a record in the Modular_Symbols.files collection, else 0|
|  `in_wdb` |  integer | 1 |   is 1 if we have this space in the web database, i.e. an entry exists in the collection webmodformspace and all galois orbits of newforms are stored in the collection webnewforms, else 0 |
|  `level` | integer | 14 | The level of the space |
|  `space_label`| string | '14.14.9' | the label of this space  of the form N.k.i where N is the level, k the weight and i the Conrey character number|,
|  `space_orbit_label` | string |  '14.14.2' | The label of the Galois orbit of this space of the form N.k.i, where i is the index of the Galois orbit of the character in the list of Galois orbits of characters of this level. The Galois orbits are ordered by the minimal number appearing in the orbit. |
|  ` weight` | integer |  14 | the weight of self |

## collection webmodformspace_dimension
    Description: more dimension data for webmodform spaces
| Field | type | Example| Description |
 |-------|------|--------|---------------|
    `weight_max` | integer | 100 | the largest weight in the table
    `group` | string | u'gamma0' | the group, either 'gamma0' or 'gamma1' 
    `level_max` | integer | 100 | the maximum level contained in this table
    `date`  | datetime | datetime.datetime(2016, 5, 4, 17, 33, 55, 54000) | when this dimension data was generated 
    `data` | string | "{'1' : {'12' : [1,1] }}" | unicode string giving json formatted dimension data in the form data[level][weight]=[d,i] where d is the dimension and i=1 if this space is in the database and otherwise 0
## Collection webchar
    Description: Json data for WebCharacter objects as defined in '/modular_forms/elliptic_modular_forms/backend/web_character.py'
| Field | type | Example| Description |
|-------|------|--------|---------------|
| `conductor` | integer | 1 | conductor |
| `label`: | string | '1.1' | label  of the form M.i where M is the modulus and i is the Conrey character number |
| `latex_name`: | string | '\\chi_{1}(1, \\cdot)' | latex_string |
| `modulus` | integer|  1 | modulus |
| `modulus_euler_phi` | integer | 1 | Euler phi function of modulus |
| `number` | integer | 1 | Conrey character number |
| `order` | integer | 1 | order of this character |
| `version` | float | 1.2 | version number | 

## Collection webchar.files
    Description: GridFS files associated with WebCharacter objects.
| Field | type | Example| Description |
|-------|------|--------|---------------|
| `modulus` | integer | 3 | modulus of the character |
| `number` | integer | 1 | Conrey character number |

## Collection webmodformspace
    Description: Json data for a Modular form space object of type 'WebModFormSpace' defined in  /modular_forms/elliptic_modular_forms/backend/web_modform_space.py
| Field | type | Example| Description |
|-------|------|--------|---------------|
| `_has_oldspace` | integer | 0 | 1 if we have computed the decomposiiton of the space of oldforms, else 0|
| `bitprec` |  integer | 53 | the precision (in bits) of the stored embedded coefficients default is 53 = double precision|
| `character` |  integer |  1 | number of the character|
| `character_naming_scheme` |  string | `Conrey' | 'Conrey' or 'Sage', used to denote the naming/labeling scheme used. Default is 'Conrey' |
| `character_orbit_rep` |  integer | 1 | The number of the character which is the representative of the Galois orbit (in the same naming scheme as above). The representative is chosen as the smallest integer in the list of character numbers |
| `character_used_in_computation` |  integer | 1 | number of the character which was used in the computation (could be another character in the Galois orbit)|
| `creation_date` | datetime | datetime.datetime(1970, 1, 1, 0, 0) | when the record was created |
| `cuspidal` |  integer |  1 | 1 if the record describes a space of cusp forms, else 0 |
| `dimension` |  integer |  0 | dimension of this space|
| `dimension_cusp_forms` |  integer | 0 | dimension of the space of cusp forms with this level, weight and character |
| `dimension_modular_forms` |  integer |  1 | dimension of the space of modular forms with this level, weight and character|
| `dimension_new_cusp_forms` |  integer |  0 |   dimension of the space of (cuspidal) newforms with this level, weight and character|
| `hecke_orbits` | list | [] | list of labels of the newforms Hecke orbits of self which are stored in the collection 'webnewforms' |
| `level` |  integer | 2 | level |
| `prec` |  integer | 10 | number of coefficients stored in the q-expansions for the newforms (if they are stored) |
| `space_label` |  string | `2.2.1' | label of the format level.weight.character where character is the number above (in particular given by the naming scheme in 'character_naming_scheme') |
| `space_orbit_label` | string | `2.2.0' | label of the format level.weight.o where o is the number of the galois orbit of the character in the list of all galois orbits (ordered by their minimal element)|
| `sturm_bound` | integer |  0 | the Sturm bound for this space, i.e. a general bound on the number of coefficients which must be given to uniquely indentify a modular form in this space |
| `version` | float | 1.2 | version number |
| `weight` |  integer | 2 | weight |
| `zeta_orders` | list | [] | list of orders of the generators of the cyclotomic fields which are the base fields of the Fourier coefficients of the newforms in the database|
  
## Collection webmodformspace.files
    Description: GridFS files associated with WebModFormSpace objects which are also given by records in the collection webmodformspace. See the definition of  'WebModFormSpace' in /modular_forms/elliptic_modular_forms/backend/web_modform_space.py 
    File format: a dictionary containing data for the webmodformspace as described in the second table below. 

| Field | type | Example| Description |
|-------|------|--------|---------------|
| `space_label` | string | '10.8.7' | label of the form level.weight.character  corresponding to the record in the collection 'webmodformspace'|
| `version` | float | version number |

### Data structure for the file 
| Field | type | Example| Description |
|-------|------|--------|---------------|
|`_character_galois_orbit`| list | [1] | list of characters in the Galois orbit of the character|
| `_character_galois_orbit_embeddings` | dict | {} | embeddings (if computed) |
| `character_naming_scheme` | string | 'Conrey' | character naming scheme |
| `character_orbit_rep` | integer | 1 | the number of the representative of the Galois orbit (should be the smallest number in the orbit) |
| `character_used_in_computation` | integer | 1 | the character used to compute this space |
| `group` | string |  'x\x9ck`J.NLO\xd5\xcb\xcdO)\xcdI,...' | a binary string givng the subgroup as an object of type sage.modular.arithgroup.congroup_gamma0.Gamma0_class_with_category|
| `oldspace_decomposition` | {} | the decomposition of the old subspace of this modular form space|
| `space_label`: '32.6.1' | the label in format level.weight.character |
| `version` | float | 1.3 | version number|
| `zeta_orders` | list | [] | list of orders of the generators of the cyclotomic field which the character takes values in|

## Collection webnewforms
    Description: Json data for a Newform object of type 'WebNewform' as defined in '/modular_forms/elliptic_modular_forms/backend/web_newforms.py'
| Field | type | Example| Description |
|-------|------|--------|---------------|
| `absolute_polynomial` | string | `x^2 - 3072' | the absolute polynomial for the coefficient field |
| `base_ring` | string  | `1.1.1.1' | the base field of the coefficient field. Should be the same as the field in which the character has values (we view the trivial character as having values in Q which has label '1.1.1.1')|
| `character` | integer | 1 | the character number in the scheme described below|
| `character_naming_scheme` | string  | `Conrey' | The naming scheme of the character used for this object|
| `cm_disc` | integer | 0 | equals D, the discriminant of the imaginary quadratic field with which this newform has CM if it has CM, else 0|
| `coefficient_field` |  string | `2.2.12.1' | the label (in the format as given by lmfdb number fields) of the coefficient field|
| `coefficient_field_degree` | integer | 2 | the absolute degree of the coefficient field|
| `creation_date` | datetime datetime.datetime(2016, 4, 13, 9, 43) | when this record was created |
| `dimension` | integer |2 | dimension of this newform as an irreducible submodule of the ambient space |
| `hecke_orbit_label` | string | '32.6.1.d' | the label of format level.weight.character.label where 'label' is given in the field `label` below|
| `is_cm` | integer | 0 | 1 if this newform has CM, else 0 |
| `is_cuspidal` | integer |1  | 1 if this record corresponds to a cuspidal newform (for future compatibility if Eisenstein series will be included), else 0  |
| `is_rational` | integer | 0 | 1 if this newform has rational Fourier coefficients, else 0|
| `label` |  | `d' | label of this orbit in the 'Cremona label' convention, i.e. the first (0th in python ordering) orbit has label 'a', the second 'b', the 27-th 'aa' and then 'ab', the 702nd is 'aaa' etc.|
| `level` | integer | 32 | level |
| `modification_date` | datetime | datetime.datetime(2016, 4, 13, 9, 43, 44, 974000) | when this record was last modified |
| `parent` |  | `32.6.1' | label of form label.weight.character of the space which contains the given newform (corresponding to the key 'space_label' in the collection webmodformspace)|
| `prec` | integer | 190 | number of coefficients in the stored q-expansion (either in this record or in the gridfs record)|
| `q_expansion` |  string | 'q + 1/2*a*q^3 + 46*q^5 - 3*a*q^7 + 525*q^9' | string formatted q-expansion of this newform (if not stored here it is taken from the gridfs object in webmodformspace.files)|
| `version` | 1.3 | version number|
| `weight` |integer | 6 | weight|

## Collection webnewforms.files
    Description: GridFS files associated with WebNewform objects in the collection webnewforms
    File format: a dictionary containing data for the webnewform as described in the second table below. 
| Field | type | Example| Description |
|-------|------|--------|---------------|
`hecke_orbit_label` | string | '11.12.1.b' | the label of this newform, corresponds to the same entry in the collection webnewforms
|`prec` | integer | 220 | the number of coefficients which are stored in this record

### Data structure for the file 
| Field | type | Example| Description |
|-------|------|--------|---------------|
|`_atkin_lehner_eigenvalues` | dict | { 2:-1 } | Atkin-Lehner eigenvalues (if they are known) corresponding to divisors of N 
|`_cm_values` | list |  [] | values of self at CM-points (computed numerically)
|`_embeddings` |  dict |  {`bitprec` :  53,  `prec` :  191,  `values` :  {0: [0.0],  1: [1.0, 1.0], 2: [0.0, 0.0],   3: [-27.7128129211020, 27.7128129211020]} | dictionary of complex embeddings with keys 'bitprec' -- the precision of the computed embeddings, 'prec'-- the number of coefficients and 'values' -- dictionary of lists containing the embeddings 
|`explicit_formulas` | dict | {'as_polynomial_in_E4_and_E6': [2,  {0: [0, 2], 1: [3, 0]},   (-1/1728, 1/1728)]} | dictionary containing information about explicit formulas
|`_coefficients` | dict | {1:1,2:0,3:1/2*a} | dictionary of coefficients as elements of the coefficient field given by sage objects
|`absolute_polynomial` |  x^2 - 3072 | the absolute polynomial of the coefficient field
|`base_ring` |  dict | {`base` :  'QQ', `gens` : ('x',), `relative polynomial` : 'x'}, | dictionary representing the base ring (field) with keys: 'base' -- the base ring this is defined over (usually QQ), 'gens'-- the name(s) of the variable(s) in the polynomial, and 'relative_polynomial' -- the relative polynomial of this number field over the base 
|`coefficient_field` |  {`base` :  'QQ',  `gens` :  'a',  `relative polynomial` |  `a^2 - 3072`} | the coefficient field in the same format as above
|`q_expansion` | sage object | q + 1/2*a*q^3 + 46*q^5 +O(q^7) | q-expansion as an element of sage.rings.power_series_poly.PowerSeries_poly over the coefficient field
|`satake` | dict |  {`alphas` :  {0: {3: -0.888888888888889 + 0.458122847290851*I,    },   1: {3: 0.888888888888889 + 0.458122847290851*I,  + 0.767295761583521*I}},  `alphas_latex` :  {0: {3: -0.888888888888889 + 0.458122847290851i, }, 1: {3: 0.888888888888889 + 0.458122847290851i}},  `ps` :  [3],  `thetas` :  {0: {3: 2.66571040392938,   1: {3: 0.475882249660417}}},  `thetas_latex` :  {0: {3: 2.66571040392938},  1: {3: 0.475882249660417}}} | 
|`twist_info` | list | [False, [`4.6.1.a`]] | the first entry is True if this newform is primitive and False if it is a twist, the second entry is a list of labels of newforms which twist to this newform
|`version` |  float | 1.3 | version number
    
## Collection webeigenvalues.files
    Description: Contains GridFS files with Hecke aigenvalues of newforms. 
    The format of the file is a dictionary containing the matrix and vector E and v as returned by the method compact_system_of_eigenvalues in sage. The precise format is given in the second table below.
| Field | type | Example| Description |
|-------|------|--------|---------------|
|`hecke_orbit_label` | string | '28.6.1.a' | label of the newform, matching the record in the collection webnewforms
|`prec` | integer | 100 | the number of coefficients we can get with the eigenvalues in this file
|`version` | float | 1.3 | version number
### Data structure for the file 
| Field | type | Example| Description |
|-------|------|--------|---------------|
|`E` | string | '' | binary string giving a matrix as a sage object
|`v` | string | '' | binary string giving a vector as a sage object
|`meta` | dict | {'cputime': u'', 'version': u''} | metadata
 
# Collections used for computing webobjects -- not present on the cloud database

## Collection Atkin_Lehner.files 
    Description: GridFS files containing Atkin-Lehner eigenvalues for newforms.
    File format: a string of '+' and '-'  corresponding to eigenvalue 1 or -1 of W_p for p in prime_divisors(N)
| Field | type | Example| Description |
|-------|------|--------|---------------|
| `N` | integer |  17 | level |
| `cchi` | integer | 1 | Conrey character number |
| `chi` | integer | 0 | Sage character number (index in DirichletGroup(N) |
| `cputime`  | float | 5.744359 | time to compute the eigenvalues |
| `k` | integer |  2 | weight |
| `newform` | integer | 0 | index of the newform in the list of all newforms with this level, weight and character, ordered as in Sage by traces of Hecke operators (?)
| `sage_version`:  | string | '7.2' | version of sage used to compute this object |
| `filename` | string  | `atkin_lehner_evs-   17-  2-  0-  0` | filename in gridfs |
 
## Collection Modular_symbols.files
    Description: GridFS files containing modular symbols. 
    File format: Sage object of type 'sage.modular.modsym.ambient.ModularSymbolsAmbient_wtk_eps_with_category'
    Example: Modular symbols space of dimension 75 and level 500, weight 2, character [-1, zeta4], sign 1, over Cyclotomic Field of order 4 and degree 2
| Field | type | Example| Description |
|-------|------|--------|------------------|
| `N` | integer | 500 | level |
| `cchi` | integer | 307 | Conrey character number |
| `character_galois_orbit` | list | [307, 443] | Conrey character numbers of the orbit of cchi
| `chi` | integer | 16 | sage character number |
| `complete` |  integer | 4 | indicates how 'complete' all records for this space is, set to 4 (currently the maximum) if all newform orbits and their aps up to the bound given by the L-functions requirements are computed |
| `conrey_galois_orbit_number` |  integer | 16 | the number of the Galois orbit in the list of all Galois orbits in DirichletGroup_Conrey |
| `cputime` | float | 0. | time it took  to compute this record in seconds | 
| `dima` |  integer | 75 | dimension of ambient space of modular symbols of weight k, level N, character chi and sign =-1 |
| `dimc` |  integer | 65 |  dimension of cuspidal submodule |
| `dimn` |  integer | 48 | dimension of new submodule of the cuspidal submodule |
| `filename` | string | 'gamma0-ambient-modsym-00500-002-016' | filename in gridfs |
| `k` |  integer | 2 | weight |
| `nfactors` |  integer | 0 | number of newform factors in the database for this record (should be updated after the orbits are computed) | 
| `orbits` |  integer | 0 | same as 'nfactors' (probably one of these were introduced by some bug some time ago) |
| `sage_version` | string | '6.1beta' | version of sage used to compute the object (and that may be needed to unpickle it sucessfully) |
| `space_label` |  string | '500.2.307' | label of the space in the format N.k.cchi |
| `space_orbit_label` | string  | '500.2.16' | label of the orbit of the space in the format N.k.o where 'o' is the order of the Galois orbit in the list of all Galois orbits in DirichletGroup_Conrey
  
## Collection Newform_factors.files
    Description: GridFS files containing newform factors.
    File format: Sage object of type 'sage.modular.modsym.subspace.ModularSymbolsSubspace_with_category'
    Example: Modular symbols subspace of dimension 1 of Modular Symbols space of dimension 70 for Gamma_0(372) of weight 2 with sign 1 over Rational Field
| Field | type | Example| Description |
|-------|------|--------|---------------|
|  `N` | integer | 372 | level |
|  `ambient_id` | string | ObjectId('56be2428769754c49d4031d5') | id of the corresponding ambient space record in Modular_symbols.files |
|  `cchi` | integer |  1 | conrey character number |
|  `character_galois_orbit` | list | [1] |  | Conrey character numbers of the orbit of cchi
|  `chi` |  integer | 0 |  sage character number |
|  `chunkSize` | integer |  261120 | chunk size of gridfs files |
|  `conrey_galois_orbit_number` |  integer | 0  | the number of the Galois orbit in the list of all Galois orbits in DirichletGroup_Conrey |
|  `cputime` | 0.8625200000000002 | time it took  to compute this record in seconds | 
|  `filename` |  |  'gamma0-factors-00001-00500/00372-002-000-002' time it took  to compute this record in seconds | 
|  `hecke_orbit_label` | string |  `372.2.1.c' | the label of the Hecke orbit in the format N.k.cchi.label where 'label' is the string representation given by 'newform' using the 'Cremona label' conventions |
|  `k` |  integer | 2 | weight |
|  `length` |  integer | 152207 | length of the file |
|  `md5` |  string |  '19ea166976add07563e23bece2eb9458' | hash of the file |
|  `newform` |  integer | 2 | the number of the newform in the list of all newforms of level `N`, weight `k` and character `cchi`, ordered as in Sage (by traces of Hecke eigenvalues...) |
|  `sage_version` |  |  '6.10' | version of sage used to compute the object |
|  `uploadDate` | datetime | datetime.datetime(2016, 2, 12, 18, 27, 55, 213000)| time the file was uploaded |
|  `v` | list | [1] | the dual eigenvector as returned by the sage method compact_system_of_eigenvalues although this seems to be set to '1' in all records so I assume the records in 'vector_on_basis.files' or 'ap.files' should be used instead? |
  
## Collection ap.files
    Description: GridFS files containing ap's.
    File format: Tuple of the form (E,v) where E is an 'n times d' matrix
    and v is a length d vector as returned by the method 'compact_system_of_egenvalues(primes_first_n(n))' on a newform factor (object in the GridFS collection 'Newform_factors'). 
    Example: (25 x 4 dense matrix over Number Field in a with defining polynomial x^4 + 4*zeta12*x^2 + (4*zeta12^3 - 8*zeta12^2 - 8*zeta12 + 4)*x + 6*zeta12^2 - 10 over its base field, (1, (8/37*zeta12^3 - 109/444*zeta12^2 + 6/37*zeta12 + 5/111)*a^3 + (29/111*zeta12^3 - 5/12*zeta12^2 - 61/444*zeta12 + 1/12)*a^2 + (-83/111*zeta12^3 + 139/148*zeta12^2 + 121/444*zeta12 - 53/148)*a - 7/3*zeta12^3 - 293/222*zeta12^2 + 19/6*zeta12 - 244/111, ...))
| Field | type | Example| Description |
|-------|------|--------|---------------|
| `N` | integer | 90 | level |
| `ambient_id` | ObjectId('55baa63d769754a2084cc440') | id of the ambient space in the collection Modular_Symbols.files 
| `cchi` | integer |47 | Conrey character number |
| `character_galois_orbit` | [23, 47, 77, 83] | the galois orbit of cchi
| `chi` | integer |4 | sage character number
| `conrey_galois_orbit_number` | integer |5 | the number of the Galois orbit in the list of all Galois orbits in DirichletGroup_Conrey |
| `cputime` | 2.290000000000001 | time it took to compute this (in seconds)
| `filename` |  | `gamma0-aplists-00090-002-005-001-00000-00100' | file name in gridfs |
| `hecke_orbit_label` |  | `90.2.47.b' | label of the Hecke orbit (see above) |
| `k` | integer |2 | weight |
| `newform` | integer |1 | the number of the newform in the list of all newforms with level N, weight k and character cchi |
| `nmax` | integer |100 | the end prime in the list, for instance 97 |
| `nmin` | integer | 0 | the starting prime in the list ('0' means the first prime which is 2)
| `prec` | integer | 100 | the number of a(n) that can be obtained by the a(p)'s in this file
| `sage_version` | string  | `Sage Version 5.0.beta7, Release Date: 2012-03-05' | version of sage used to compute this object |

## Collection computations
    Description: contains information about ongoing computations (however this doesn't really work as intended at the moment...)
| Field | type | Example| Description |
|-------|------|--------|---------------|
|`N` | integer| 32 | level|
| `cch` | integer | 31 | character number in Conrey scheme|
|`k` | integer |10 | weight|
|`pid` | integer | 15136 | process id for this computation|
|`server` | srting | u'atkin' | server name where the process is running|
|`startTime` | datetime | datetime.datetime(2016, 6, 24, 17, 6, 41, 595000) | when this computation started|
|`type` | string | 'mf' | type of computation|
 
 ## Collection vector_on_basis.files
    Description: Contains GridFS files with the vector v which describes Hecke eigenvalues of newforms. This is the vector returned by the sage method compact_system_of_eigenvalues() on an irreducible Hecke invariant subspace of the ambient space. 
    File format: object of the type sage.modules.free_module_element.FreeModuleElement_generic_dense

| Field | type | Example| Description |
|-------|------|--------|---------------|
| `N` |  integer | 1 | level|
| `ambient_id` |ObjectId|  ObjectId('5232e16888aece65ecf74814')||
| `cchi` |  integer | 1 | character number in Conrey ordering|
| `chi` |  integer | 0 | character number in Sage ordering|
| `filename` | string | 'gamma0-ambient-v-00001-036-000-000'| file name in GridFS|
| `k` |  integer | 36 | weight|
| `newform` |  integer | 0 | the index  of the newform in the list of all newforms with level N, weight k and character cchi (starting from 0)|
| `prec` |  integer | 100 | the number of coefficients which can be obtained from the vector in the gridfs file|
| `sage_version` |  string | '6.0' | sage version used to ompute this object|
  
