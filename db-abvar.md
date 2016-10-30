# Database abvar

|||
|---|---|
|**Description**|Isogeny classes of abelian varieties over finite fields|
|**Status**|[beta](http://beta.lmfdb.org/Variety/Abelian/Fq/)|
|**Contact**|[David Roe](https://github.com/roed314)|
|**Code**|[abvar/fq](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/abvar/fq)|
|**Collections**|[fq_iosg](http://beta.lmfdb.org/api/abvar/fq_isog)|

**Todo**:
* Compute and add data on Frobenius angle ranks

## Collection fq_isog

* Content: Isogeny classes of abelian varities over finite fields
* Contributors: Kiran Kedlaya, Taylor Dupuy, David Roe, Christelle Vincent
* Extent: Complete for pairs (g, q) where the number of isogeny classes is less than 10^5 (as of October 2016)

<table border=2>
<tr>
<th>Field</th>
<th>Description</th>
<th>Type of stored data</th>
<th>Mathematical type</th>
<th>Example of stored data</th>
<th>Remarks</th>
</tr>

<tr>
<td> _id </td><td> Mongo id </td><td> ObjectId </td><td>-</td><td></td>
<td>assigned by Mongo; contains creation timestamp</td></tr>

<tr>
<td> label </td><td> LMFDB Label </td><td> string </td><td> - </td><td> '2.16.am_cn' </td>
<td>[Labeling Scheme](http://beta.lmfdb.org/Variety/Abelian/Fq/Labels)</td></tr>

<tr>
<td> g </td><td> Genus </td><td> int </td><td> N </td><td> 2 </td>
<td> The degree of the Weil L-polynomial is 2g. </td></tr>

<tr>
<td> q </td><td> Cardinality of Field </td><td> int </td><td> prime power </td><td> 16 </td>
<td> All of the roots of the Weil L-polynomial have absolute value $1/\sqrt{q}$. </td></tr>

<tr>
<td> polynomial </td><td> Coefficients of the Weil L-polynomial </td><td> list of ints </td><td> Z^(2g+1) </td><td> [1,-12,65,-192,256] </td>
<td> The first entry will always be 1 and the last $q^g$.  For i between 0 and g, $a_{2g-i} = q^{g-i} a_i$. </td></tr>

<tr>
<td> angle_numbers </td><td> Frobenius angle numbers </td><td> list of doubles </td><td> R^g </td><td> [0.0826163580681,0.320878822416] </td>
<td> The positive arguments of the roots (considered as complex numbers) of the Weil L-polynomial.  There will be g of them unless the list includes 0 or pi. </td></tr>

<tr>
<td> angle_rank </td>
<td> The dimension of the </td></tr>

<tr>
<td> p_rank </td><td> The $p$-rank of the abelian variety </td><td> int </td><td> N </td><td> 2 </td>
<td> The rank of the p-torsion subgroup of the abelian variety.  Equal to the number of occurences of the slope 0 in the newton slopes. </td></tr>

<tr>
<td> slopes </td><td> The slopes of the Newton polygon of the Weil polynomial </td><td> list of strings </td><td> Q^(2g+1) </td><td> ["0", "1/2", "1/2", "1"] </td>
<td> The slopes are in increasing order, are symmetric under the involution $s \to 1-s$, and the corresponding Newton polygon has endpoints (0,0) and (2g,g).</td></tr>

<tr>
<td> A_counts </td><td> The number of points of the abelian variety over extensions of F_q </td><td> list of ints </td><td> N^g </td><td> [118, 62068] </td>
<td> Counts are given for $A(F_{q^n})$ for $1 \le n \le g$; counts over larger extension fields can be determined from these using the Weil conjectures.</td></tr>

<tr>
<td> C_counts </td><td> The number of points of a corresponding curve </td><td> list of ints </td><td> Z^g </td><td> [5, 243] </td>
<td> These are the point counts of a genus g curve of which this is the Jacobian.  If any point counts are negative then this abelian variety cannot be a Jacobian.</td></tr>

<tr>
<td> known_jacobian </td><td> An integer encoding whether the abelian variety is a Jacobian </td><td> int </td><td> - </td><td> 0 </td>
<td> 1 means that it is definitely a Jacobian, -1 that it is definitely not, and 0 indicates uncertainty. </td></tr>

<tr>
<td> principally_polarizable </td><td> An integer encoding whether the abelian variety is principally polarizable </td><td> int </td><td> - </td><td> 0 </td>
<td> 1 means that it is definitely principally polarizable, -1 that it is definitely not, and 0 indicates uncertainty. </td></tr>

<tr>
<td> decomposition </td><td> The decomposition into simple factors </td><td> list of pairs (string, int) </td><td> - </td><td> [['2.16.am_cn',1], ['1.16.ah',2]] </td>
<td> The first entry in each pair is the label of the factor, the second is its multiplicity. </td></tr>

<tr>
<td> brauer_invariants </td><td> The Brauer invariants of the endomorphism algebra </td><td> list of strings </td><td> Q^k </td><td> </td>
<td> The number of invariants is the number of primes above p in the number field defined by the Weil polynomial.</td></tr>

<tr>
<td> primitive_models </td>
<td></td></tr>

<tr>
<td> number_field </td><td> The label of the number field defined by the Weil polynomial </td><td> string </td><td> - </td><td> "4.0.27792.2" </td>
<td>&nbsp;</td></tr>
<tr>
<td> galois_n </td><td> The degree label of the Galois group of the Weil polynomial </td><td> int </td><td> - </td><td> 4 </td>
<td> </td></tr>
<tr>
<td> galois_t </td><td> The transitive label of the Galois group of the Weil polynomial </td><td> int </td><td> - </td><td> 2 </td>
<td> </td></tr>
</table>

Index information on collection fq_isog:

- {'_id': 1} (created by mongo)
- {'label': 1} (for searching)
- {'polynomial': 1} (for searching)
- {'p_rank': 1} (for searching)
- {'slopes': 1} (for searching)
- {'A_counts': 1} (for searching)
- {'C_counts': 1} (for searching)
- {'known_jacobian': 1} (for searching)
- {'principally_polarizable': 1} (for searching)
