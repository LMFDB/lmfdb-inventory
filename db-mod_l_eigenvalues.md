# Database mod_l_eigenvalues

|||
|---|---|
|**Description**|---|
|**Status**|---|
|**Contact**|[Samuele Anni](https://github.com/sanni85)|
|**Code**|---|
|**Collections**|[modlmf](http://beta.lmfdb.org/api/mod_l_eigenvalues/modlmf)|

## Collection modlmf

|||
|---|---|
|**Description**|Mod-ell modular forms|
|**Status**|[alpha](http://beta.lmfdb.org/ModularForm/GL2/ModL/)|
|**Contact**|[Samuele Anni](https://github.com/sanni85)|
|**Code**|[modlmf](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/modlmf)|
|**Collections**|[modlmf](http://beta.lmfdb.org/api/mod_l_eigenvalues/modlmf)|

Contibutors: Samuele Anni, Anna Medvedovsky, Bartosz Naskrecki, David Roberts

The data is coming from [here](https://github.com/sanni85/Mod-l-modular-forms).

Format of the data:

* **characteristic** (integer): the characteristic of the base ring of the form
* **deg** (integer): degree of base field over prime field
* **level** (integer): minimal level of the form, that is the smallest level in which the eigenvalue system does occurr. If the associated representation is irreducible this is the Artin conductor away from l.
* **weight_grading** (integer): weight of the form modulo ell-1
* **reducible** (list [string, integer, string, integer, integer]): this means that the associated representation is reducible of the form 
<p align="center">
chi_1 cycl^a + chi_2 cycl^b,                  with a < b
</p>
where chi_1, chi_2 are mod ell Dirichlet characters and cycl is the mod ell cyclotomic character. This is the format
<p align="center">
[dirchar_label(chi_1), power of cyclotomic a, dirchar_label(chi_2), power of cyclotomic b, eisenstein_weight] 
</p>

   The dirchar_label is the **full** label of the character.
   The eisenstein_weight is the minimal weight of the Eisenstein lift of smallest weight.

It is empty in the **irreducible** case.

* **cuspidal_lift**(list [integer, string, string, string]): description of the characteristic zero cuspidal lift of smallest weight and smalles Galois orbit (alphabetical order). This consists of 
    * (int) the weight of the newform, 
    * (string) the label of the newform 
    * (string) the polynomial giving the Hecke eigenvalue field.
    * (string) the ideal used for the reduction, in terms of the generators. 
* **dirchar** (int): label of the mod ell Dirichlet character. 
* **atkinlehner** (list of two-element lists of integers): [[int(p^e), int(W_{p^e})] for p^e exactly dividing N] 
* **n_coeffs** (integer): the number of Fourier coefficients
* **coeffs** (list of strings): coefficients of the q-expansion. The finite field where the coefficients belongs is represented using Conway polynomials.
* **ordinary**(boolean): 1 means ordinary 
* **min_theta_weight** (integer): minimum weight in a theta cycle
* **theta_cycle**(list of tuples [int, str]): theta cycle, formattes as list of [weight, label of the Galois orbit]

## LMFDB label for a Galois orbit of mod ell modular forms. 

The label of a Galois orbit of mod ell modular forms is given by

<p align="center" ><b>
finite_field . level . weight . dirchar_index . number
</b></p>  
where 
* **finite_field** is given by the string characterist+e+degree (unless the degree is 1, so the finite_field is given by the characteristic)
* **level** is the minimal level as above
* **weight** is the weight_grading (modulo ell -1)
* **dirchar_index** comes from the label of the mod ell Dirichlet label which is characteristic.level.m
* the **number** denotes the Galois orbit, ordered looking at the q_expansion (at the moment this is relies on the code which computes the data).

## Indexes

* {'**_id_**': 1}  (created by mongo db)
* {'**characteristic_1**': 1} (for searching by characteristic)
* {'**deg_1**': 1} (for searching by degree of the finite field)
* {'**dirchar_1**': 1} (for searching by mod l Dirichlet characters)
* {'**level_1**': 1}, (for searching by level)
* {'**weight_grading_1**': 1}, (for searching by weight)

### One example of modlmf

```
{u'_id': ObjectId('581754e4051b691b8170c62f'),
 u'atkinlehner': u'',
 u'base_label': u'3e2.23.0.1',
 u'characteristic': 3,
 u'coeffs': [u'0',
  u'1',
  u'2*x',
  u'2*x + 2',
  u'x + 2',
  u'x',
  u'2*x + 1',
  u'x + 2',
  u'2*x + 2',
  u'2',
  u'2*x + 2',
  u'2*x + 2',
  u'2*x',
  u'0',
  u'2',
  u'x + 2',
  u'0',
  u'2*x + 2',
  u'x',
  u'1',
  u'1',
  u'2*x',
  u'2*x + 1',
  u'1',
  u'2',
  u'x + 2',
  u'0',
  u'x + 1',
  u'2*x + 2',
  u'0',
  u'2',
  u'0',
  u'2*x + 2',
  u'2',
  u'2*x + 1',
  u'1',
  u'2*x + 1',
  u'2*x',
  u'2*x',
  u'0',
  u'x + 2',
  u'x + 2',
  u'x + 1',
  u'0',
  u'2*x',
  u'2*x',
  u'2*x',
  u'2*x + 2',
  u'0',
  u'2*x + 1',
  u'2',
  u'2',
  u'0',
  u'2*x + 1',
  u'x + 2',
  u'x + 2',
  u'2*x',
  u'2*x + 2',
  u'0',
  u'2*x + 1',
  u'2*x + 2',
  u'2*x + 1',
  u'0',
  u'2*x + 1',
  u'2*x + 1',
  u'0',
  u'x',
  u'x + 2',
  u'2*x',
  u'2*x + 2',
  u'2*x',
  u'x + 2',
  u'x + 1',
  u'x',
  u'x + 1',
  u'2*x',
  u'x + 2',
  u'2*x',
  u'0',
  u'2*x',
  u'0',
  u'1',
  u'2',
  u'x + 2',
  u'2',
  u'x + 2',
  u'0',
  u'0',
  u'2',
  u'x + 1',
  u'x + 1',
  u'0',
  u'x + 2',
  u'0',
  u'2*x + 1',
  u'x',
  u'2',
  u'2',
  u'1',
  u'x + 1'],
 u'cuspidal_lift': [2, u'3.23.1', u'', u''],
 u'deg': 2,
 u'dirchar': u'3.23.1',
 u'index': 1,
 u'label': u'3e2.23.0.1.1',
 u'level': 23,
 u'min_theta_weight': 2,
 u'n_coeffs': 100,
 u'ordinary': 1,
 u'reducible': u'',
 u'theta_cycle': [[6, u'23.6.1'], [6, u'23.6.1']],
 u'weight_grading': 0}
```
