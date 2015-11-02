# Database limbo

Status: Fields for the most recent version will change soon.  Then older versions can be deleted.

Contact/Maintainer: John Jones

Description: These are different versions of the Artin representation databases.  They come in pairs: artrep with Artin representations and nfgal which has corresponding information about Galois groups.  A given Galois group may have several representations, so they are separated to avoid having the same information entered repeatedly.

Todo:
* ...

## Collection artintest
* Field 1: ...
* Field 2: ...

## Collection artrep20130430
* Field 1: ...
* Field 2: ...

## Collection artrep20130910
* Field 1: ...
* Field 2: ...

## Collection artrep20130914
* **Dim** (int): dimension
* **Indicator** (int): Frobenius-Schur indicator, 1 for orthogonal, -1 for symplectic, and 0 for other
* **BadPrimes** (list of int-as-string): list of bad primes, i.e., primes dividing the conductor.  Stored as strings since they may get too big
* **HardPrimes** (list of int-as-string): not sure how this differs from bad primes
* **Conductor** (int-as-string): conductor
* **Show** (int): 1 if we should show it when searching for Artin rep'ns, 0 if not (representations are present multiple times each)
* **NFGal** (list of 3 ints-as-strings): this is a pointer into the nfgal database where the triple is (transitive degree, Size, DBIndex), where Size is really |G|
* **LocalFactors** (list of list of int-as-strings): ?
* **Character** (list of list of ints): character for this representation.  Each sublist are coefficients for the character value written on a power basis for Z[zeta<sub>n</sub>]
* **CharacterField** (int): the n for writing the character
* **Sign** (int?): sign of the functional equation; not sure what is here if it isn't 1 or -1
* **Conductor_plus** (bson pair (val, len) where val is a string and len in an int): encoding of the conductor as a bson pair so we can sort them properly for searching ranges
* **galorbit** (string): code to match representations in the same orbit
* **DBIndex** (int): used to link here from the nfgal database, it is the index of representations with the same dimension and conductor
* **Galois_nt** (pair of ints): the Galois group of the definining field in the form (n,t)
 
## Collection nfgal20130430
* Field 1: ...
* Field 2: ...

## Collection nfgal20130910
* Field 1: ...
* Field 2: ...

## Collection nfgal20130914
* **Polynomial** (list of ints): coefficients of a polynomial defining this field
* **TransitiveDegree** (int): degree of the polynomial
* **Size** (int): order of the Galois group
* **DBIndex** (int): counter to distinguish those with the same degree and size, used for crossreferencing from artrep table
* **ArtinReps** (list of dicts): each entry from the list corresponds to an Artin representation for this field, giving its dimension (Dim), Character, index from the artin rep database (DBIndex), Conductor, and CharacterField
* **ConjClasses** (list of dicts): for each conjugacy class of the group: its Order (int), Representative (list of ints giving a permutation), and Size (int)
* **Frobs** (list of ints): if the i-th entry is j, then the Frobenius for the i-th prime lies in the j-th conjugacy class
* **G-Gens** (list of list of ints): inner lists are permutations given as lists which generate the Galois group
* **QpRts-p** (int): the prime p used for computing the roots p-adicly
* **QpRts-minpoly** (list of ints): coefficients for a defining polynomial over Q<sub>p</sub> used for explicitly writing roots.  The first coefficient is the constant term.
* **QpRts-prec** (int): p-adic roots are computed up to (p^prec)
* **QpRts** (list of list of string): each entry is a p-adic root, where entries in the list give the coefficients of powers of p in the p-adic approximation.  They are themselves polynomials in a, where a is a root of the QpRts-minpoly
* **ComplexConjugation** (int): index for ConjClasses to say where complex conjugation lies
* **FrobResolvents** (list of dicts):
* **label** (string): label of the number field in the global number field database
* **G-Name** (string): name for the Galois group, but we usually substitute a latex'ed name from the Galois group database


## Collection nfgal_01
* Field 1: ...
* Field 2: ...

## Collection tim_artin_01
* Field 1: ...
* Field 2: ...

## Collection tim_artin_02
* Field 1: ...
* Field 2: ...

## Collection tim_artin_03
* Field 1: ...
* Field 2: ...

## Collection tim_artin_04
* Field 1: ...
* Field 2: ...

## Collection tim_artin_06
* Field 1: ...
* Field 2: ...

## Collection tim_nfgal_03
* Field 1: ...
* Field 2: ...

## Collection tim_nfgal_04
* Field 1: ...
* Field 2: ...

## Collection tim_nfgal_06
* Field 1: ...
* Field 2: ...

