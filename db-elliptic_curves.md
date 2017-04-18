# Database elliptic_curves

| | |
|---|---|
|**Description**|Elliptic curves over **Q** and other number fields|
|**Status**|[production](http://www.lmfdb.org/EllipticCurve/)|
|**Contact**|[John Cremona](https://github.com/JohnCremona)|
|**Code**|[elliptic_curves](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/elliptic_curves/)|
|**Collections**|[curves](http://www.lmfdb.org/api/elliptic_curves/curves), [nfcurves](http://www.lmfdb.org/api/elliptic_curves/nfcurves), [padic_db](http://www.lmfdb.org/api/elliptic_curves/padic_db)|

**Notes**: In good shape over Q (collection curves).  Over quadratic and
cubic fields (collection nfcurves) complete as far as curves matching
Hilbert modular forms go; awaiting addition of curves over more fields
of degrees 4-6 to match Hilbert modular forms.

**Todo**:
* Complete the finding and uploading of curves over totally real
  fields to match the HMF newforms for fields of degrees >3.
* compute and add p-adic data for curves over Q of conductor > 130000.
* compute more ranks and generators for ecnf

## Collection curves

* Content: elliptic curves over Q
* Contributors: John Cremona, Andrew Sutherland, Jeremy Rouse
* Origin: Cremona database, https://github.com/JohnCremona/ecdata
* Extent: complete for conductors up to 380,000 (as of February 2016)

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
<td> _id </td><td> Mongo id </td><td> ObjectId </td><td>-</td><td>
</td>
<td>assigned by Mongo; contains creation timestamp</td></tr>

<tr>
<td> label </td><td> Cremona label </td><td> string </td><td> -
</td><td> '1225a2' </td>
<td>&nbsp;</td></tr>

<tr>
<td> lmfdb_label </td><td> LMFDB label </td><td> string </td><td>
- </td><td> '1225.a2' </td>
<td>&nbsp;</td></tr>

<tr>
<td> conductor </td><td> Conductor </td><td> int </td><td> N
</td><td> 1225 </td>
<td>&nbsp;</td></tr>

<tr>
<td> iso </td><td> Cremona isogeny class code </td><td> string
</td><td> - </td><td> '11a' </td>
<td>&nbsp;</td></tr>

<tr>
<td> lmfdb_iso </td><td> LMFDB isogeny class code </td><td> string
</td><td> - </td><td> '11.a' </td>
<td>&nbsp;</td></tr>

<tr>
<td> iso_nlabel </td><td> numerical version of the LMFDB isogeny
class label </td><td> int </td><td> Z </td><td> 0 </td>
<td>&nbsp;</td></tr>

<tr>
<td> number </td><td> Cremona curve number within its class
</td><td> int </td><td> N </td><td> 2 </td>
<td>&nbsp;</td></tr>

<tr>
<td> lmfdb_number </td><td> LMFDB curve number within its class
</td><td> int </td><td> N </td><td> 2 </td>
<td>&nbsp;</td></tr>

<tr>
<td> ainvs </td><td> a-invariants (coefficients of minimal reduced
Weierstass model) </td><td> list of 5 strings representing integers
</td><td> Z^5 </td><td> ['0', '1', '1', '10617', '75394'] </td>
<td>&nbsp;</td></tr>

<tr>
<td> xainvs </td><td> a-invariants (coefficients of minimal reduced
Weierstass model) </td><td> string representing list of 5 integers
</td><td> Z^5 </td><td> '[0, 1, 1, 10617, 75394]' </td>
<td>&nbsp;</td></tr>

<tr><td> jinv </td><td> j-invariant </td><td> string representing a rational </td><td> Q </td><td> '-4096/11' </td><td>&nbsp;</td></tr>

<tr><td> signD </td><td> sign of Discriminant </td><td> int </td><td>
Z </td><td> -1 </td><td>in {-1,+1}</td></tr>

<tr><td> cm </td><td> CM code </td><td> int </td><td> Z </td><td> 0
(for no CM), or a negative discriminant </td><td>in {0, -3, -4, -7,
-8, -11, -12, -16, -19, -27, -28, -43, -67, -163}</td></tr>

<tr><td> rank </td><td> rank </td><td> int </td><td> N_0 </td><td> 0
</td><td>May be missing</td></tr>

<tr><td> torsion </td><td> torsion order </td><td> int </td><td> Z
</td><td> 1 </td><td>&nbsp;</td></tr>

<tr><td> torsion_structure </td><td> invariants of torsion subgroup
 </td><td> list of at most 2 strings representing ints </td><td> N^t
 (0&le;t&le2) </td><td> ['3'] </td><td>&nbsp;</td></tr>

<tr><td> torsion_generators </td><td> generators of torsion subgroup
</td><td> list of strings representing points </td><td> A^2(Q)^t
(0&le;t&le2) </td><td> ['(5, 5)'] </td><td>&nbsp;</td></tr>

<tr><td> x-coordinates_of_integral_points </td><td> x-coordinates of
integral points </td><td>string representing list of integers</td><td>
Z^k </td><td> '[5,16]' </td><td>&nbsp;</td></tr>

<tr><td> gens </td><td> generators of infinite order </td><td> list of
strings representing points </td><td> P^2(Q)^k  (k&ge;0)
</td><td> ['(0:0:1)'] </td><td>May be missing</td></tr>

<tr><td> heights </td><td> heights of generators </td><td> list of
floats </td><td> R^k  (k&ge;0)
</td><td> [0.4754476141654406, 2.4031247402073275]</td><td>May be
missing</td></tr>

<tr><td> regulator </td><td> regulator </td><td> float </td><td> R
</td><td> 1.0 </td><td>May be missing; approximate if rank>0</td></tr>

<tr><td> tamagawa_product </td><td> Tamagawa product </td><td> int
</td><td> N </td><td> 4 </td><td>&nbsp;</td></tr>

<tr><td> special_value </td><td> special value of r'th derivative of
L-function (divided by r!) </td><td> float </td><td> R </td><td>
1.490882041449698 </td><td>approximate</td></tr>

<tr><td> real_period </td><td> real period </td><td> float </td><td> R
</td><td> 0.3727205103624245 </td><td>approximate</td></tr>

<tr><td> degree </td><td> degree of modular parametrization </td><td>
int </td><td> N </td><td> 1984 </td><td>&nbsp;</td></tr>

<tr><td> non-surjective_primes </td><td> primes p for which the mod p
Galois representation is not surjective </td><td> list of ints
</td><td> N^k (k&ge;0)</td><td> [5] </td><td>&nbsp;</td></tr>

<tr><td> non-maximal_primes </td><td> primes p for which the mod p
Galois representation is not maximal </td><td> list of ints
</td><td> N^k (k&ge;0)</td><td> [5] </td><td>&nbsp;</td></tr>

<tr><td> galois_images </td><td> Sutherland codes for the images of
the mod p Galois representations for the non-surjective primes
</td><td> list of strings </td><td> - </td><td> ['5B']
</td><td>Sutherland notation; for CM curves, only primes<100</td></tr>

<tr><td> mod-p_images </td><td> Sutherland codes for the images of
the mod p Galois representations for the non-maximal primes
</td><td> list of strings </td><td> - </td><td> ['5B']
</td><td>Sutherland notation</td></tr>

<tr><td> 2adic_label </td><td> Rouse label of the associated modular
curve (None for CM curves) </td><td> string </td><td> - </td><td>
'X225g' </td><td>based on Rouse, Zureik-Brown classification</td></tr>

<tr><td> 2adic_index </td><td> index in GL(2,Z2) of the 2-adic
representation (or 0 for CM curves) </td><td> int </td><td> N
</td><td> 1 </td><td>&nbsp;</td></tr>

<tr><td> 2adic_log_level </td><td> the smallest n such that the image
contains the kernel of reduction modulo 2^n (or None for CM curves)
</td><td> int </td><td> N_0 </td><td> 1 </td><td>&nbsp;</td></tr>

<tr><td> 2adic_gens </td><td> list of matrices in GL(2,Z/2^nZ)
generating the image (None for CM curves) </td><td> list of lists of 4
ints </td><td> GL(2,Z)^k  (k&ge;0)</td><td> [[5,0,0,5],[5,5,0,1],[5,5,0,3]]
</td><td>&nbsp;</td></tr>

<tr><td> isogeny_matrix </td><td> isogeny matrix </td><td> list of
lists of ints)</td><td> M_k(N)  (k&ge;0)</td><td> [[1,5,25],[5,1,5],[25,5,1]]
</td><td>&nbsp;</td></tr>

<tr><td> sha_an </td><td> analytic order of Sha </td><td> float
</td><td> R </td><td> 9.0 </td><td> approximate unless
rank<2</td></tr>

<tr><td> sha </td><td> analytic order of sha </td><td> int </td><td> N
</td><td> 9 </td><td>rounded value of sha_an</td></tr>

<tr><td> sha_primes </td><td> primes dividing sha </td><td> list of
ints </td><td> N^k  (k&ge;0)</td><td> [2] </td><td>&nbsp;</td></tr>

<tr><td> torsion_primes </td><td> primes dividing torsion </td><td>
list of ints </td><td> N^k  (k&ge;0)</td><td> [2,3] </td><td>&nbsp;</td></tr>

<tr><td> local_data </td><td> reduction data at bad primes </td><td>
list of dicts, one per prime, each with keys 'p' (value:int),
'ord_cond' (value: int), 'ord_disc' (value: int), 'ord_den_j' (value:
int), 'red' (value: int), 'cp' (value: int), 'kod' (value:
string)</td><td> &nbsp; </td><td> [{'cp': 1, 'kod': '\\( I_{1} \\)',
'ord_cond': 1, 'ord_den_j': 1, 'ord_disc': 1, 'p': 11, 'red': 1}]
</td><td>&nbsp;</td></tr>

<tr><td> min_quad_twist </td><td> minimal quadratic twist </td><td>
dict with keys 'label' (value:string) and 'disc' (value: int)</td><td>
N </td><td> {'disc': 1, 'label': '11a2'} </td><td>&nbsp;</td></tr>

<tr><td> aplist </td><td> Traces of Frobenius </td><td> list of 25
ints</td><td> Z^25 </td><td> [0, 1, -1, ..., 2] </td><td>a_p for p<100</td></tr>

<tr><td> anlist </td><td> L-series coefficients </td><td> list of 20
ints</td><td> Z^20 </td><td> [0, 1, -1, ..., 2] </td><td>a_n for
0<=np<20</td></tr>

<tr><td> iwdata </td><td> Iwasawa invariants </td><td> dictionary with
keys ints, values lists of ints</td><td> Z^20 </td><td> {u'11': [1,
0], u'3': [0, 0], u'2': [0, 1, 0], u'5': [0, 1]} </td><td>keys are primes,
including all bad multiplicative primes and all primes up to some
bound</td></tr>

<tr><td> iwp0 </td><td> Iwasawa prime </td><td> int</td><td> N
</td><td> 7 </td><td>if nonzero, a prime p0 such that lambda=mu=0 for
all good p>=p0</td></tr>

</table>

Index information on collection curves:

-  {'_id': 1} (created by mongo)
-  {'rank': 1, 'number': 1} (for searching and stats)
-  {'number': 1} (for searching and stats)
-  {'conductor': 1, 'iso_nlabel': 1, 'lmfdb_number': 1} (for sorting)
-  {'non-surjective_primes': 1} (for searching)
-  {'non-maximal_primes': 1} (for searching)
-  {'cm': 1} (for searching)
-  {'conductor': 1} (for searching)
-  {'lmfdb_label': 1,'number': 1} (for searching)
-  {'lmfdb_iso': 1} (for searching)
-  {'sha': 1} (for searching)
-  {'lmfdb_label': 1} (for searching)
-  {'rank': 1} (for searching)
-  {'label': 1} (for searching)
-  {'jinv': 1} (for searching)
-  {'torsion_structure': 1} (for searching)
-  {'iso': 1} (for searching)
-  {'torsion': 1} (for searching)
-  {'label': 1, 'number': 1} (for searching)
-  {'xainvs': 1} (for searching)
-  curves2.rand (auxilliary collection used for random objection access)


## Collection padic_db

* Content: p-adic regulators for elliptic curves over Q
* Contributors: unkown
* Origin: unknown
* Extent: primes p with 3,p<100 of good ordinary reduction, for curves of
 conductor up to 130,000 only (last updated in 2010)

<table border=2>
<tr>
<th>Field</th>
<th>Description</th>
<th>Type of stored data</th>
<th>Mathematical type</th>
<th>Example of stored data</th>
<th>Remarks</th>
</tr>

<tr> <td> _id </td><td> Mongo id </td><td> ObjectId </td><td>
</td>-<td> </td> <td>assigned my Mongo; contains creation
timestamp</td></tr>

<tr> </td><td> lmfdb_iso </td><td> LMFDB label of isogeny class
</td><td> string </td><td>-</td><td> '58.a' </td><td>&nbsp;</td> </tr>

<tr> </td><td> p </td><td> prime </td><td> int </td><td>N (prime)</td><td> 97
</td><td>&nbsp;</td> </tr>

<tr> </td><td> prec </td><td> p-adic precision </td><td> int
</td><td>N</td><td> 20 </td><td>&nbsp;</td> </tr>

<tr> </td><td> unit </td><td> unit factor of regulator </td><td>
string representing integer </td><td>Z_p (mod p^N)</td><td>
'8471152617139064438417376357679138234' </td><td>&nbsp;</td></tr>

<tr> </td><td> val </td><td> valuation of p-adic regulator </td><td>
int </td><td>N_0</td><td> 1 </td><td>&nbsp;</td> </tr>

</table>

## Collection nfcurves

* Content: elliptic curves over number fields other than Q
* Contributors: John Cremona, Alyson Deines, Steve Donelly, Paul Gunnells, Warren Moore, Haluk Sengun, John Voight, Dan Yasaki.
* Origin: https://github.com/JohnCremona/ecnf-data
* Extent: contains curves over several totally real fields (of degrees up to 6) and a few imaginary quadratic fields, in each case complete up to some conductor norm bound
* Updated collection and description 22 July 2016.

* Explanation of data fields representing elements of the field, including points:
  - Each field of degree d has a distinguished generator w.
  - A rational number is represented as a string.
  - A field element (NFelt) is usually represented as an NFelt-string, being d
  rational-strings, representing the coordinates with respect to
  the w-power basis, joined by ","; or in some contexts as a string
  representing the element as a polynomial in the field generator w.
  - A point (in projective coordinates) is represented as a
  point-string:  3 NFelt-strings surrounded by "[","]", joined with
  ",", the whole surrounded again by "[","]".
  - An ideal is represented as an ideal-string [N,a,alpha] where N is
  the norm, a the smallest positive integer and alpha a second
  generator expressed as a polynomial in w.

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
<td> _id </td><td> Mongo id </td><td> ObjectId </td><td>-</td><td>
</td>
<td>assigned my Mongo; contains creation timestamp</td></tr>

<tr><td> field_label </td><td> Base field label </td><td> string
</td><td>&nbsp;</td><td> '2.0.8.1' </td><td>&nbsp;</td></tr>

<tr><td> degree </td><td> Base field degree </td><td> int </td>
<td>N</td><td>2</td> <td>&nbsp;</td></tr>

<tr><td> signature </td><td> Base field signature </td><td> list of 2
ints </td><td>N_0^2</td><td> [0, 1] </td><td>&nbsp;</td></tr>

<tr><td> abs_disc </td> <td>absolute value of discriminant of base
field </td><td> int </td> <td>N</td><td> 8 </td><td>&nbsp;</td></tr>

<tr><td> label </td> <td>full label </td> <td> string </td><td>-</td> <td>
'2.0.8.1-[3618,1146,3]-e2'</td> <td>&nbsp;</td></tr>

<tr><td> short_label </td> <td> short label (excludes field) </td>
<td> string </td> <td>-</td><td> '[3618,1146,3]-e2' </td>
<td>&nbsp;</td></tr>

<tr><td> class_label </td> <td> full label of isogeny class </td> <td>
string </td> <td>-</td><td> '2.0.8.1-[3618,1146,3]-e' </td>
<td>&nbsp;</td></tr>

<tr><td> short_class_label </td> <td> short label of isogeny class
(excludes field) </td> <td> string </td> <td>-</td><td>
'2.0.8.1-[3618,1146,3]-e'</td> <td>&nbsp;</td></tr>

<tr><td> conductor_label </td> <td> condcutor label </td> <td> string
</td><td>-</td> <td> '[3618,1146,3]' or '37.1' </td>
<td>&nbsp;</td></tr>

<tr><td> iso_label </td> <td> isogeny class label </td> <td> string
</td> <td>-</td><td> 'e' </td> <td>base 26 representation of isogeny
class index</td></tr>

<tr><td> iso_nlabel </td> <td> isogeny class index
</td> <td> int </td> <td>N_0</td><td> 4 </td> <td>&nbsp;</td></tr>

<tr><td> conductor_ideal </td> <td>  data defining the conductor
</td> <td> ideal-string </td> <td>-</td><td>
'[13931,13931,-25*w^2+11*w]' </td> <td>representation generators</td></tr>

<tr><td> conductor_norm </td> <td> conductor norm </td> <td> int </td>
<td>N</td><td> 3618 </td> <td>&nbsp;</td></tr>

<tr><td> number </td> <td> index of curve in isogeny class </td> <td>
int </td><td>N</td> <td> 2 </td> <td>starts at 1</td></tr>

<tr><td> isogeny_matrix </td> <td> Isogeny matrix </td> <td> list of
list of ints (degrees) </td><td>M_k(N) (k&ge;0)</td> <td> [[1, 2], [2,
1]] </td> <td>&nbsp;</td></tr>

<tr><td> ainvs </td> <td> a-invariants </td> <td> string
</td><td>&nbsp;</td> <td> '0,0,1;0,0,0;1,1,1;0,2,-2;1,-1,-1' </td>
<td>5 Weierstrass coefficients as NFelt-strings, joined by ";"</td></tr>

<tr><td> jinv </td> <td> j-invariant </td> <td> string
</td> <td>&nbsp;</td><td> ['288857903821/4771277298',
'7556047939133/9542554596'] </td> <td>NFelt-string</td></tr>

<tr><td> analytic_rank </td> <td> analytic rank </td> <td> int </td>
<td>N_0</td><td> 0 </td> <td>&nbsp;</td></tr>

<tr><td> rank </td> <td> rank </td> <td> int </td> <td>N_0</td><td> 0
</td> <td>&nbsp;</td></tr>

<tr><td> rank_bounds </td> <td> lower and upper rank bounds </td> <td>
list of 2 ints </td> <td>N_0^2</td><td> [0, 0] </td>
<td>&nbsp;</td></tr>

<tr><td> sha_an </td> <td> analytic order of Sha </td> <td> int </td>
<td>N</td><td> 1 </td> <td>rounded float</td></tr>

<tr><td> gens </td> <td> generators of infinite order </td> <td> list
of point-strings </td> <td>P^2(K)^r
(0&le;r&le;rank)</td><td> ['[[0,-1,1],[0,0,0],[1,0,0]]', '[[0,-1,0],[-2,-1,1],[1,0,0]]']
</td> <td>&nbsp;</td></tr>

<tr><td> torsion_order </td> <td> torsion order </td> <td> int </td>
<td>N</td><td> 6 </td> <td>&nbsp;</td></tr>

<tr><td> torsion_structure </td> <td> invariants of torsion subgroup
</td> <td> list of at most 2 ints </td> <td> N^t (0&le;t&le2)
</td><td> [3, 3] </td> <td>&nbsp;</td></tr>

<tr><td> torsion_gens </td> <td> torsion generators </td><td> list of
point-strings </td><td>P^2(K)^t (0&le;t&le2)</td><td>['[[0,0,0],[0,1,-1],[1,0,0]]', '[[1/2,-3/4,0],[-5/8,1/8,1/2],[1,0,0]]'] </td> <td>&nbsp;</td></tr>

<tr><td> q_curve </td> <td> Q-curve flag </td> <td> boolean </td>
<td>{True, False}</td><td> False </td> <td>&nbsp;</td></tr>

<tr><td> base_change </td> <td> labels of base change source curves
</td> <td> list of strings </td> <td>-</td><td> ['4032.k2',
'63.a2']</td> <td>&nbsp;</td></tr>

<tr><td> cm </td><td> CM code </td><td> int </td><td> Z </td><td> 0
(for no CM), or a negative discriminant </td><td>&nbsp;</td></tr>

<tr><td> local_data</td><td>List of local data at bad
  primes</td><td>{'p','normp','red','kod',ord_cond','ord_disc','ord_den_j'}^k</td><td>[{'cp':
  1, 'kod': '\\( I_{27} \\)', 'normp': '2', 'ord_cond': 1,
  'ord_den_j': 27, 'ord_disc': 27, 'p': '[2,2,-w-10]', 'red':
  -1}]</td> <td>'p': ideal_string (prime ideal), 'normp':int (its
  norm), 'kod': string (Kodaira symbol), 'red': {-1,0,1} (reduction type), ord_cond:int (conductor
  exponent), ord_disc: int (discriminant exponent), ord_den_:int
  (j-invariants denominator exponent)</td></tr>

<tr><td> minD</td> <td> minimal discriminant ideal </td>
<td>ideal-string</td> <td>Ideal</td> <td>'[1399489,199927,101*w^2-44*w-121]</td><td>&nbsp;</td></tr>

<tr><td> heights</td> <td>heights of generators</td> <td> list of
floats </td><td>R^r</td><td>[0.2815779492939666, 0.25465400108973096]</td>
<td>&nbsp;</td></tr>

<tr><td> reg</td><td> regulator </td><td> float </td><td>R</td><td><td>0.01024588468931388</td>
<td>&nbsp;</td></tr>

<tr><td> non_min_p</td><td>Non-minimal primes</td><td> list of ideal-strings</td><td>{ideals}^k</td><td>[]</td>
<td>&nbsp;</td></tr>

<tr><td> equation</td><td> Weierstrass equation</td><td>string</td><td>&nbsp;</td><td>'\\( y^2 + x y + y = x^{3} + a x^{2} + \\left(-30047 a - 303287\\right) x - 9341927 a - 94305014  \\)</td>
<td>&nbsp;</td><td>&nbsp;</td></tr>


</table>

Index information for collection nfcurves

-  {'_id': 1} (created by mongo)
-  {'field_label': 1}
-  {'degree': 1}
-  {'number': 1}
-  {'label': 1}
-  {'field_label':1, 'conductor_norm':1, 'conductor_label':1, 'iso_nlabel':1,'number':1}

-  nfcurves.rand (auxilliary collection used for random objection access)

