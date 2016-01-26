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
Weierstass model) </td><td> list of strings representing integers
</td><td> Z^5 </td><td> ['0', '1', '1', '10617', '75394'] </td>
<td>&nbsp;</td></tr>

<tr><td> jinv </td><td> j-invariant </td><td> string representing a rational </td><td> Q </td><td> '-4096/11' </td><td>&nbsp;</td></tr>

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

<tr><td> galois_images </td><td> Sutherland codes for the images of
the mod p Galois representations for the non-surjective primes
</td><td> list of strings </td><td> - </td><td> ['5B']
</td><td>Sutherland notation; for CM curves, only primes<100</td></tr>

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

</table>

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
* Extent: contains curves over several real and imaginary quadratic fields, in each case complete up to some conductor norm bound

* Explanation of data fields representing elements of the field, including points:
  - Each field of degree d has a distinguished generator
  - A rational number is represented as a string
  - A field element is represented as a list of d strings, each representing the coordinate with respect to the power basis
  - A point is represented (in projective coordinates) as a list of 3 field elements, i.e. a list of 3 lists of d strings
  - Generator fields are represented by lists of points

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

<tr><td> conductor_ideal </td> <td> data defining the conductor ideal
</td> <td> string </td> <td>-</td><td>
'[3618,1146,3]' </td> <td>representation generators</td></tr>

<tr><td> conductor_norm </td> <td> conductor norm </td> <td> int </td>
<td>N</td><td> 3618 </td> <td>&nbsp;</td></tr>

<tr><td> number </td> <td> index of curve in isogeny class </td> <td>
int </td><td>N</td> <td> 2 </td> <td>starts at 1</td></tr>

<tr><td> isogeny_matrix </td> <td> Isogeny matrix </td> <td> list of
list of ints (degrees) </td><td>M_k(N) (k&ge;0)</td> <td> [[1, 2], [2,
1]] </td> <td>&nbsp;</td></tr>

<tr><td> ainvs </td> <td> a-invariants </td> <td> list of 5 lists of d
strings </td><td>&nbsp;</td> <td> [['1', '0'], ['1', '-1'], ['1',
'1'], ['17', '-7'], ['9', '22']] </td> <td>coordinates with respect to
power basis; d is the degree of the field</td></tr>

<tr><td> jinv </td> <td> j-invariant </td> <td> list of d strings
</td> <td>&nbsp;</td><td> ['288857903821/4771277298',
'7556047939133/9542554596'] </td> <td>coordinates with respect to
power basis; d is the degree of the field</td></tr>

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
of lists of 3 lists of d strings </td> <td>A^2(K)^r
(0&le;r&le;rank)</td><td> [[['2', '2'], ['11', '-12'], ['1', '0']]]
</td> <td>&nbsp;</td></tr>

<tr><td> torsion_order </td> <td> torsion order </td> <td> int </td>
<td>N</td><td> 6 </td> <td>&nbsp;</td></tr>

<tr><td> torsion_structure </td> <td> invariants of torsion subgroup
</td> <td> list of at most 2 ints </td> <td> N^t (0&le;t&le2)
</td><td> [3, 3] </td> <td>&nbsp;</td></tr>

<tr><td> torsion_gens </td> <td> torsion generators </td><td> list of
lists of 3 lists of d strings </td><td>A^2(K)^t (0&le;t&le2)</td><td>
[[['-9', '2'], ['16', '18'], ['1', '0']]] </td> <td>&nbsp;</td></tr>

<tr><td> q_curve </td> <td> Q-curve flag </td> <td> boolean </td>
<td>{True, False}</td><td> False </td> <td>&nbsp;</td></tr>

<tr><td> base_change </td> <td> labels of base change source curves
</td> <td> list of strings </td> <td>-</td><td> ['4032.k2',
'63.a2']</td> <td>&nbsp;</td></tr>

<tr><td> cm </td><td> CM code </td><td> int </td><td> Z </td><td> 0
(for no CM), or a negative discriminant </td><td>&nbsp;</td></tr>

</table>
