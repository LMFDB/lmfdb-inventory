# Database elliptic_curves

Status: In good shape over Q (collection curves) and quadratic fields
(collection nfcurves);  awaiting addition of curves over fields of
degrees 3-6 to match Hilbert modular forms.

Contact/Maintainer: John Cremona

Description: Elliptic curves over Q and other number fields.

Todo:
* Complete the finding and uploading of curves over totally real
  fields to match the HMF newforms for fields of degrees >3.
* compute and add p-adic data for curves over Q of conductor > 130000.

## Collection curves

* Content: elliptic curves over Q
* Contributors: John Cremona, Andrew Sutherland, Jeremy Rouse
* Origin: Cremona database, https://github.com/JohnCremona/ecdata
* Extent: complete for conductors up to 370,000 (as of November 2015)

| Field | Description | Type | Example |
| --- | --- | --- | --- |
| _id | Mongo id | ObjectId | |
| label | Cremona label | string | '1225a2' |
| lmfdb_label | LMFDB label | string | '1225.a2' |
| conductor | Conductor | int | 1225 |
| iso | Cremona isogeny class code | string | '11a' |
| lmfdb_iso | LMFDB isogeny class code | string | '11.a' |
| iso_nlabel | numerical version of the LMFDB isogeny class label | int | 0 |
| number | Cremona curve number within its class | int | 2 |
| lmfdb_number | LMFDB curve number within its class | int | 2 |
| ainvs | a-invariants | list of strings representing integers | ['0', '1', '1', '10617', '75394'] |
| jinv | j-invariant | string representing a rational | '-4096/11' |
| cm | CM code | int | 0 for no CM, or -3, -4, ... |
| rank | rank | int 0 |
| torsion | torsion order | int | 1 |
| torsion_structure | invariants of torsion subgroup | list of at most 2 strings representing ints | ['3'] |
| torsion_generators | generators of torsion subgroup | list of strings representing points | ['(5, 5)'] |
| x-coordinates_of_integral_points | x-coordinates of integral points | string representing list of ints | '[5,16]' |
| gens | generators of infinite order | list of strings representing points | ['(0:0:1)'] |
| regulator | regulator | float | 1.0 |
| tamagawa_product | Tamagawa product | int | 4 |
| special_value | special value of r'th derivative of L-function (divided by r!) | float | 1.490882041449698 |
| real_period | real period | float | 0.3727205103624245 |
| degree | degree of modular parametrization | int | 1984 |
| non-surjective_primes | primes p for which the mod p Galois representation is not surjective | list of ints |  [5] |
| galois_images | Sutherland codes for the images of the mod p Galois representations for the non-surjective primes | list of strings | ['5B'] |
| 2adic_index | index in GL(2,Z2) of the 2-adic representation (or 0 for CM curves) | int | 1 |
| 2adic_log_level | the smallest n such that the image contains the kernel of reduction modulo 2^n (or None for CM curves) | int | 1 |
| 2adic_gens | list of matrices in GL(2,Z/2^nZ) generating the image (None for CM curves) | list of lists of 4 ints | [[5,0,0,5],[5,5,0,1],[5,5,0,3]] |
| 2adic_label |  Rouse label of the associated modular curve (None for CM curves) | string | 'X225g' |
| isogeny_matrix |  isogeny matrix | list of lists of ints)| [[1,5,25],[5,1,5],[25,5,1]] |
| sha_an | analytic order of sha (approximate unless r<2) | float | 9.0 |
| sha | analytic order of sha (rounded value of sha_an) | int | 9 |
| sha_primes | primes dividing sha | list of ints | [2] |
| torsion_primes | primes dividing torsion | list of ints | [2,3] |

## Collection padic_db

* Content: p-adic regulators for elliptic curves over Q
* Contributors: unkown
* Origin: unknown
* Extent: primes p with 3,p<100 of good ordinary reduction, for curves of
 conductor up to 130,000 only (last updated in 2010)

* Field 1: ...
* Field 2: ...

## Collection nfcurves

* Content: elliptic curves over number fields other than Q
* Contributors: John Cremona, Alyson Deines, Steve Donelly, Paul Gunnells, Warren Moore, Haluk Sengun, John Voight, Dan Yasaki.
* Origin: https://github.com/JohnCremona/ecnf-data
* Extent: contains curves over several real and imaginary quadratic fields, in each case complete up to some conductor norm bound

* Field 1: ...
* Field 2: ...

