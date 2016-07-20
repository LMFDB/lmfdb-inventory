# Database modularforms2

|||
|---|---|
|**Description**|Classical modular forms|
|**Status**|[production](http://www.lmfdb.org/ModularForm/GL2/Q/holomorphic/)|
|**Contact**|[Stefan Ehlen](https://github.com/sehlen), [Fredrik Strömberg](https://github.com/fredstro)|
|**Code**|[modular_forms/elliptic_modular_forms](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/modular_forms/elliptic_modular_forms)|
|**Collections**|[dimension_table](http://www.lmfdb.org/api/modularforms2/dimension_table), [webchar](http://www.lmfdb.org/api/modularforms2/webchar), [webchar.chunks](http://www.lmfdb.org/api/modularforms2/webchar.chunks), [webchar.files](http://www.lmfdb.org/api/modularforms2/webchar.files), [webmodformspace](http://www.lmfdb.org/api/modularforms2/webnewforms), [webnewformspace.chunks](http://www.lmfdb.org/api/modularforms2/webmodformspace.chunks), [webnewformspace.files](http://www.lmfdb.org/api/modularforms2/webmodformspace.files), [webnewforms](http://www.lmfdb.org/api/modularforms2/webnewforms), [webnewforms.chunks](http://www.lmfdb.org/api/modularforms2/webnewforms.chunks), [webnewforms.files](http://www.lmfdb.org/api/modularforms2/webnewforms.files), [webeigenvalues](http://www.lmfdb.org/api/modularforms2/webeigenvalues), [webeigenvalues.chunks](http://www.lmfdb.org/api/modularforms2/webeigenvalues.chunks), [webeigenvalues.files](http://www.lmfdb.org/api/modularforms2/webeigenvalues.files)|

**Todo**: Document the collections listed above (and either document or delete all others)
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
* Field 1: ...
* Field 2: ...

## Collection webmodformspace.chunks
* Field 1: ...
* Field 2: ...

## Collection webmodformspace.files
   Description: GridFS files associated with WebModFormSpace objects.
* Field 1: ...
* Field 2: ...

## Collection webnewforms
    Description: Json data associated with WebNewform objects as defined in '/modular_forms/elliptic_modular_forms/backend/web_newforms.py'
* Field 1: ...
* Field 2: ...

## Collection webnewforms.chunks
* Field 1: ...
* Field 2: ...

## Collection webnewforms.files
   Description: GridFS files associated with WebNewform objects.
* Field 1: ...
* Field 2: ...

## Collection webeigenvalues.chunks
    Description: GridFS files associated with WebEigenvalue objects.
* Field 1: ...
* Field 2: ...

## Collection webeigenvalues.files
* Field 1: ...
* Field 2: ...

# Collections used for computing webobjects 

## Collection Newform_Factor

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
 


## Collection Modular_symbols.files'
    Description: GridFS files containing modular symbols. 
    File format: Sage object of type 'sage.modular.modsym.ambient.ModularSymbolsAmbient_wtk_eps_with_category'
    Example: Modular Symbols space of dimension 75 and level 500, weight 2, character [-1, zeta4], sign 1, over Cyclotomic Field of order 4 and degree 2
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
    Example: Modular Symbols subspace of dimension 1 of Modular Symbols space of dimension 70 for Gamma_0(372) of weight 2 with sign 1 over Rational Field
| Field | type | Example| Description |
|-------|------|--------|---------------|
|  `N` | integer | 372 | level |
|  `ambient_id` | string | ObjectId('56be2428769754c49d4031d5') | id of the corresponding ambient space record in Modular_Symbols.files |
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
  
## Collection aps.files
    Description: GridFS files containing aps.
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

