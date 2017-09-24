# Database artin

| | |
|---|---|
|Description|Artin representations|
|Status|[production](http://www.lmfdb.org/ArtinRepresentation/)|
|Contact|[John Jones](https://github.com/jwj61)|
|Code|[artin_representations](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/artin_representations)|
|Collections|[representations](http://www.lmfdb.org/api/artin/representations), [field_data](http://www.lmfdb.org/api/artin/field_data)|

**Todo**: Add index information

## Collection representations
* **Dim** (int): dimension
* **Indicator** (int): Frobenius-Schur indicator, 1 for orthogonal, -1 for symplectic, and 0 for other
* **BadPrimes** (list of int-as-string): list of bad primes, i.e., primes dividing the conductor.  Stored as strings since they may get too big
* **HardPrimes** (list of int-as-string): primes dividing the polynomial discriminant for the defining field.  These include the Bad Primes.
* **Conductor** (int-as-string): conductor
* **Conductor_key** (string): encoding of the conductor for searching.  The first four characters give the number of decimal digits minus 1 (padded with zeros), followed by the conductor itself.
* **Hide** (int): 0 if we should show it when searching for Artin rep'ns, 1 if not.  The representations are invariants of the Galois closure of the given field.  More than one field can have the same Galois closure.  We pick a best/minimal one and show that.  We have data for others for linking to the number field database.
* **NFGal** (string): comma-separated list of integers giving the coefficients of the polynomial for the corresponding number field after polredabs, starting with the constant coefficient.
* **CharacterField** (int): the n for writing the character
* **Baselabel** (string): our label in the form a.b.c.e.f.g where a=the dimension, b=conductor in factored form (using e for ^ and t form *), c=|Galois group|, d=size of the Galois orbit of characters, e= is the Galois group in the form ntm where n is the degree and m is the "t-number", g is a counter to distinguish representations with the same data.
* **GaloisConjugates** (list): list of Galois conjugate character information.


Each entry in the GaloisConjugates list is a dictionary with the following entries
* **LocalFactors** (list of list of int-as-strings): local factors for the L-function
* **Character** (list of list of ints): character for this representation.  Each sublist are coefficients for the character value written on a power basis for Z[zeta<sub>n</sub>]
* **Sign** (int): sign of the functional equation when we know it is 1 or -1, otherwise we give 0.
* **HardFactors**: local factors for bad primes
* **GalOrbIndex** (ints): an index assigned to the given character
 
## Index information for representations collection (to be added)

* ...
* **representations.rand** (auxilliary collection used for random objection access)

## Collection field_data
* **Polynomial** (string): coefficients of a polynomial defining this field, the comma-separated list of coefficients as a string.  This is the main identifier for this field from the representations collection, and also matches entries in the number field database.
* **TransitiveDegree** (int): degree of the polynomial
* **Size** (int-as-string): order of the Galois group
* **DBIndex** (int): counter to distinguish those with the same degree and size, used for crossreferencing from artrep table
* **ArtinReps** (list of pairs, [string, int]): the string is the baselabel of an entry from the Artin representation database, and the int is the GalOrbIndex for a particular character with that Baselabel
* **ConjClasses** (list of dicts): for each conjugacy class of the group: its Order (int), Representative (list of ints giving a permutation), and Size (int)
* **Frobs** (list of ints): if the i-th entry is j, then the Frobenius for the i-th prime lies in the j-th conjugacy class
* **G-Gens** (list of list of ints): inner lists are permutations given as lists which generate the Galois group
* **QpRts-p** (int): the prime p used for computing the roots p-adicly
* **QpRts-minpoly** (list of ints): coefficients for a defining polynomial over Q<sub>p</sub> used for explicitly writing roots.  The first coefficient is the constant term.
* **QpRts-prec** (int): p-adic roots are computed up to (p^prec)
* **QpRts** (list of list of string): each entry is a p-adic root, where entries in the list give the coefficients of powers of p in the p-adic approximation.  They are themselves polynomials in a, where a is a root of the QpRts-minpoly
* **ComplexConjugation** (int): index for ConjClasses to say where complex conjugation lies
* **FrobResolvents** (list of dicts):
* **G-Name** (string): name for the Galois group, but we usually substitute a latex'ed name from the Galois group database, but this is a fallback


