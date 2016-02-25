# Database genus2_curves

Status: In good shape over QQ (all collections synced).

Contact/Maintainer: Jeroen Sijsling.

Description: Genus 2 curves over QQ.

Todo:
* Match with automorphic objects.


## Collection curves

* Content: Basic data for genus 2 curves over QQ.
* Contributors: Andrew Sutherland.
* Origin: Code by Andrew Sutherland.
* Extent: 66158 curves so far, see arXiv:1602.03715 for heuristics on the
  completeness of this collection.


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
<td> _id </td>
<td> Mongo id </td>
<td> ObjectId </td>
<td> - </td>
<td> </td>
<td> assigned my Mongo; contains creation timestamp</td>
</tr>

<tr>
<td> aut_grp </td>
<td> automorphism group (shorthand) </td>
<td> list of integers </td>
<td> - </td>
<td> [6, 2] </td>
<td> </td>
</tr>

<tr>
<td> class </td>
<td> isogeny class </td>
<td> string </td>
<td> - </td>
<td> u'169.a' </td>
<td> </td>
</tr>

<tr>
<td> cond </td>
<td> conductor </td>
<td> integer </td>
<td> NN </td>
<td> 169 </td>
<td> </td>
</tr>

<tr>
<td> disc_key </td>
<td> representation of the discriminant D of the curve: the first three digits
are int(log_10 (D)), which is followed by digits representing the absolute
value of |D|. </td>
<td> string </td>
<td> - </td>
<td> u'002169' </td>
<td> </td>
</tr>

<tr>
<td> disc_sign </td>
<td> sign of the discriminant </td>
<td> integer </td>
<td> - </td>
<td> -1 </td>
<td> </td>
</tr>

<tr>
<td> g2inv </td>
<td> G2 invariants </td>
<td> list of strings </td>
<td> - </td>
<td> [u'-1/169', u'33/169', u'43/169'] </td>
<td> </td>
</tr>

<tr>
<td> geom_aut_grp </td>
<td> geometric automorphism group (shorthand) </td>
<td> list of integers </td>
<td> - </td>
<td> [12, 4] </td>
<td> </td>
</tr>

<tr>
<td> igusa </td>
<td> Igusa invariants </td>
<td> list of strings </td>
<td> - </td>
<td> [u'1', u'-33', u'-43', u'-283', u'-169'] </td>
<td> </td>
</tr>

<tr>
<td> igusa_clebsch </td>
<td> Igusa-Clebsch invariants </td>
<td> list of strings </td>
<td> - </td>
<td> [u'8', u'3172', u'30056', u'-692224'] </td>
<td> </td>
</tr>

<tr>
<td> is_gl2_type </td>
<td> whether the curve is of GL2-type over its base field </td>
<td> boolean </td>
<td> - </td>
<td> True </td>
<td> </td>
</tr>

<tr>
<td> label </td>
<td> LMFDB label </td>
<td> string </td>
<td> - </td>
<td> u'169.a.169.1' </td>
<td> </td>
</tr>

<tr>
<td> min_eqn </td>
<td> representation of defining polynomials </td>
<td> list of lists of integers </td>
<td> - </td>
<td> [[0, 0, 0, 0, 1, 1], [1, 1, 0, 1]] </td>
<td> </td>
</tr>

<tr>
<td> num_rat_wpts </td>
<td> number of rational Weierstrass points </td>
<td> integer </td>
<td> NN_0 </td>
<td> 0 </td>
<td> </td>
</tr>

<tr>
<td> real_geom_end_alg </td>
<td> endomorphism ring over base field tensored with RR </td>
<td> string </td>
<td> - </td>
<td> u'M_2(R)' </td>
<td> </td>
</tr>

<tr>
<td> st_group </td>
<td> Sato-Tate group over base field </td>
<td> string </td>
<td> - </td>
<td> u'E_6' </td>
<td> </td>
</tr>

<tr>
<td> torsion </td>
<td> rational torsion group of the Jacobian, represented by the invariant
factors [d_1, d_2, ...] for which this torsion group is isomorphic to ZZ / d_1
ZZ x ZZ / d_2 ZZ x ...  </td>
<td> list of integers </td>
<td> - </td>
<td> [19] </td>
<td> </td>
</tr>

<tr>
<td> torsion_order </td>
<td> rational torsion order of the Jacobian </td>
<td> integer </td>
<td> NN_0 </td>
<td> 19 </td>
<td> </td>
</tr>

<tr>
<td> two_selmer_rank </td>
<td> 2-Selmer rank </td>
<td> integer </td>
<td> NN_0 </td>
<td> 0 </td>
<td> </td>
</tr>

</table>


## Collection endomorphisms

* Content: Endomorphism data for genus 2 curves over QQ.
* Contributors: Jeroen Sijsling.
* Origin: Code by Jeroen Sijsling
* Extent: Data known for all curves in the genus 2 curves database.

* The representation of the endomorphism lattice by subfields of the full field
  of definition of the endomorphism ring has a rather terse format. It is a
  list of lists, and its entries are as follows.
* First entry: A triple that describes the base field by its LMFDB label, a
  list representing a minimal polynomial, and a list representing a generator
  in the smallest field over which all endomorphisms are defined, as described
  by fod_coeffs.
* Second entry: At most two lists that indicate the factors of the endomorphism
  algebra. Two first entries of these lists base fields of the corresponding
  factors, as in the description of the first entry above. The third entry
  indicates whether the corresponding factor is a field or not. If -1 then it
  is; otherwise this entry is the norm of the discriminant of the corresponding
  quaternion algebra over the base field described by the first two entries.
* Third entry: A sequence of strings describing End ox RR.
* Fourth entry: A list that describes the endomorphism ring as a subring of the
  endomorphism algebra. If the second entry is -1, then the first entry gives
  an index or a conductor norm in the case of a field if that applies. If 0
  or 1, then the first entry describes the index of the order and the second
  entry describes whether it is Eichler (1) or not (0).
* Fifth entry: The Sato-Tate group.
* The conventions above are also used in other fields.

* For splittings of the Jacobian, we return a subfield of smallest degree over
  which the splitting occurs, represented as above. We also return lists that
  represent defining equations for the corresponding elliptic curves over that
  field, or rather, a and b such that the corresponding factor is isomorphic to
  the curve with equation y^2 = x^3 + (-a/48) x + (-b/864). LMFDB labels for
  these curves is also return if they exist, and conductor norms are always
  given.


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
<td> _id </td>
<td> Mongo id </td>
<td> ObjectId </td>
<td> - </td>
<td> </td>
<td> assigned my Mongo; contains creation timestamp</td>
</tr>

<tr>
<td> factorsQQ_base </td>
<td> description of endomorphism algebra factors over the base field </td>
<td> list of lists </td>
<td> - </td>
<td> [[u'2.0.3.1', [1, -1, 1], -1]] </td>
<td> </td>
</tr>

<tr>
<td> factorsQQ_geom </td>
<td> description of endomorphism algebra factors over the algebraic closure </td>
<td> list of lists </td>
<td> - </td>
<td> [[u'1.1.1.1', [0, 1], 1]] </td>
<td> </td>
</tr>

<tr>
<td> factorsRR_base </td>
<td> endomorphism algebra factors over the base field tensored with RR </td>
<td> list of strings </td>
<td> - </td>
<td> [u'CC'] </td>
<td> </td>
</tr>

<tr>
<td> factorsRR_geom </td>
<td> endomorphism algebra factors over the algebraic closure tensored with RR
</td>
<td> list of strings </td>
<td> - </td>
<td> [u'M_2(RR)'] </td>
<td> </td>
</tr>

<tr>
<td> fod_coeffs </td>
<td> defining polynomial of the smallest field over which all endomorphisms
are defined </td>
<td> list of integers </td>
<td> - </td>
<td> [-1, -3, 6, 4, -5, -1, 1] </td>
<td> </td>
</tr>

<tr>
<td> fod_label </td>
<td> LMFDB label of the smallest field over which all endomorphisms are defined
</td>
<td> string </td>
<td> - </td>
<td> u'6.6.371293.1' </td>
<td> </td>
</tr>

<tr>
<td> is_simple_base </td>
<td> whether the curve is simple over the base field </td>
<td> boolean </td>
<td> - </td>
<td> True </td>
<td> </td>
</tr>

<tr>
<td> is_simple_geom </td>
<td> whether the curve is simple over the algebraic closure </td>
<td> boolean </td>
<td> - </td>
<td> False </td>
<td> </td>
</tr>

<tr>
<td> label </td>
<td> LMFDB label </td>
<td> string </td>
<td> - </td>
<td> u'169.a.169.1' </td>
<td> </td>
</tr>

<tr>
<td> lattice </td>
<td> endomorphism lattice </td>
<td> list of lists </td>
<td> - </td>
<td> [[[u'1.1.1.1', [0, 1], [u'0', u'0', u'0', u'0', u'0', u'0']],
[[u'2.0.3.1', [1, -1, 1], -1]], [u'CC'], [1, -1], u'E_6'], ...] </td>
<td> </td>
</tr>

<tr>
<td> ring_base </td>
<td> endomorphism ring over the base field as a subring of the endomorphism
algebra </td>
<td> list of integers </td>
<td> - </td>
<td> [1, -1] </td>
<td> </td>
</tr>

<tr>
<td> ring_geom </td>
<td> endomorphism ring over the algebraic closure as a subring of the
endomorphism algebra </td>
<td> list of integers </td>
<td> - </td>
<td> [3, 1] </td>
<td> </td>
</tr>

<tr>
<td> spl_facs_coeffs </td>
<td> defining coefficients of the elliptic curves obtained by splitting the
Jacobian </td>
<td> list of lists </td>
<td> - </td>
<td> [[[u'2644', u'9457', u'-8353', u'-15597', u'1720', u'3630'], [u'207207',
u'759759', u'-759759', u'-1342341', u'160160', u'316316']]] </td>
<td> </td>
</tr>

<tr>
<td> spl_facs_condnorms </td>
<td> conductor norms of the elliptic curves obtained by splitting the Jacobian
</td>
<td> list of integers </td>
<td> - </td>
<td> [1] </td>
<td> </td>
</tr>

<tr>
<td> spl_facs_labels </td>
<td> LMFDB labels of the elliptic curves obtained by splitting the Jacobian </td>
<td> list of strings </td>
<td> - </td>
<td> [1] </td>
<td> </td>
</tr>

<tr>
<td> spl_fod_coeffs </td>
<td> defining polynomial of a field of minimal degree over which a splitting of
the Jacobian is defined </td>
<td> list of integers </td>
<td> - </td>
<td> [-1, -3, 6, 4, -5, -1, 1] </td>
<td> </td>
</tr>

<tr>
<td> spl_fod_gen </td>
<td> generator of a field of minimal degree over which a splitting of
the Jacobian is defined, as a subfield of the smallest field over which all
endomorphisms are defined </td>
<td> list of strings </td>
<td> - </td>
<td> [u'0', u'1', u'0', u'0', u'0', u'0'] </td>
<td> </td>
</tr>

<tr>
<td> spl_fod_label </td>
<td> LMFDB label of a field of minimal degree over which a splitting of the
Jacobian is defined </td>
<td> string </td>
<td> - </td>
<td> u'6.6.371293.1' </td>
<td> </td>
</tr>

<tr>
<td> st_group_base </td>
<td> Sato-Tate group over the base field </td>
<td> string </td>
<td> - </td>
<td> E_6  </td>
<td> </td>
</tr>

<tr>
<td> st_group_geom </td>
<td> Sato-Tate group over the algebraic closure </td>
<td> string </td>
<td> - </td>
<td> E_1 </td>
<td> </td>
</tr>

</table>


## Collection isogeny-classes

* Content: Isogeny classes of genus 2 curves over QQ.
* Contributors: Andrew Sutherland.
* Origin: Code by Andrew Sutherland.
* Extent: Data known for all curves in the genus 2 curves database.


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
<td> _id </td>
<td> Mongo id </td>
<td> ObjectId </td>
<td> - </td>
<td> </td>
<td> assigned my Mongo; contains creation timestamp</td>
</tr>

<tr>
<td> analytic_rank </td>
<td> analytic rank of the curves in the isogeny class </td>
<td> integer </td>
<td> NN_0 </td>
<td> 0</td>
<td> </td>
</tr>

<tr>
<td> bad_lfactors </td>
<td> bad primes and the corresponding L-factors </td>
<td> list of lists </td>
<td> - </td>
<td> [[13, [1, 5, 13]]] </td>
<td> </td>
</tr>

<tr>
<td> cond </td>
<td> conductor </td>
<td> integer </td>
<td> NN </td>
<td> 169 </td>
<td> </td>
</tr>

<tr>
<td> hash </td>
<td> hash </td>
<td> hash </td>
<td> - </td>
<td> 1456780685049277288L </td>
<td> </td>
</tr>

<tr>
<td> is_gl2_type </td>
<td> whether the curves in the isogeny class are of GL2-type over its base
field </td>
<td> boolean </td>
<td> - </td>
<td> True </td>
<td> </td>
</tr>

<tr>
<td> label </td>
<td> LMFDB label of the isogeny class </td>
<td> string </td>
<td> - </td>
<td> u'169.a' </td>
<td> </td>
</tr>

<tr>
<td> real_geom_end_alg </td>
<td> endomorphism ring over base field tensored with RR </td>
<td> string </td>
<td> - </td>
<td> u'M_2(R)' </td>
<td> </td>
</tr>

<tr>
<td> root_number </td>
<td> root number </td>
<td> string </td>
<td> - </td>
<td> u'1' </td>
<td> </td>
</tr>

<tr>
<td> st_group </td>
<td> Sato-Tate group </td>
<td> string </td>
<td> - </td>
<td> u'E_6' </td>
<td> </td>
</tr>

</table>



## Collection Lfunctions

* Content: L-functions for genus 2 curves over QQ.
* Contributors: Andrew Booker.
* Origin: Code by Andrew Booker.
* Extent: Data known for all curves in the genus 2 curves database. First
  zeroes and L-factors (primes up to 100) known.


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
<td> _id </td>
<td> Mongo id </td>
<td> ObjectId </td>
<td> - </td>
<td> </td>
<td> assigned my Mongo; contains creation timestamp</td>
</tr>

<tr>
<td> algebraic </td>
<td> whether the L-function is algebraic or not </td>
<td> boolean </td>
<td> - </td>
<td> True </td>
<td> </td>
</tr>

<tr>
<td> analytic_normalization </td>
<td> translation needed to obtain the analytic normalization </td>
<td> string </td>
<td> - </td>
<td> u'1/2' </td>
<td> </td>
</tr>

<tr>
<td> bad_lfactors </td>
<td> bad primes and the corresponding L-factors </td>
<td> list of lists </td>
<td> - </td>
<td> [[13, [1, 5, 13]]] </td>
<td> </td>
</tr>

<tr>
<td> central_character </td>
<td> central character </td>
<td> string </td>
<td> - </td>
<td> u'169.1' </td>
<td> </td>
</tr>

<tr>
<td> coefficient_field </td>
<td> LMFDB label of the coefficient field </td>
<td> string </td>
<td> - </td>
<td> '1.1.1.1'' </td>
<td> </td>
</tr>

<tr>
<td> conductor </td>
<td> conductor </td>
<td> integer </td>
<td> NN </td>
<td> 169 </td>
<td> </td>
</tr>

<tr>
<td> degree </td>
<td> degree </td>
<td> integer </td>
<td> NN </td>
<td> 4 </td>
<td> </td>
</tr>

<tr>
<td> euler_factors </td>
<td> Euler factors for primes up to 100 </td>
<td> string </td>
<td> - </td>
<td> u'[[1, 3, 5, 6, 4], ... ] </td>
<td> </td>
</tr>

<tr>
<td> gamma_factors </td>
<td> Gamma factors </td>
<td> string </td>
<td> - </td>
<td> u'[[],[0,0]]' </td>
<td> </td>
</tr>

<tr>
<td> hash </td>
<td> hash </td>
<td> hash </td>
<td> - </td>
<td> 1456780685049277288L </td>
<td> </td>
</tr>

<tr>
<td> instances </td>
<td> where the L-function occurs </td>
<td> list of strings </td>
<td> - </td>
<td> [u'/L/Genus2Curve/Q/169/a'] </td>
<td> </td>
</tr>

<tr>
<td> motivic_weight </td>
<td> motivic weight </td>
<td> integer </td>
<td> NN_0 </td>
<td> 0 </td>
<td> </td>
</tr>

<tr>
<td> order_of_vanishing </td>
<td> order of vanishing at critical point </td>
<td> integer </td>
<td> NN_0 </td>
<td> 0 </td>
<td> </td>
</tr>

<tr>
<td> origin </td>
<td> a genus 2 isogeny that is the source of the L-function; note that not only
may there be other sources, but these are expected always to exist </td>
<td> string </td>
<td> - </td>
<td> u'/L/Genus2Curve/Q/169/a' </td>
<td> </td>
</tr>

<tr>
<td> plot </td>
<td> description of a plot of the curve </td>
<td> string </td>
<td> - </td>
<td> u'[[-30.0000,2.942647259768447], ... ] </td>
<td> </td>
</tr>

<tr>
<td> primitive </td>
<td> whether the L-function is primitive </td>
<td> boolean </td>
<td> - </td>
<td> False </td>
<td> </td>
</tr>

<tr>
<td> root_number </td>
<td> root number </td>
<td> string </td>
<td> - </td>
<td> u'1' </td>
<td> </td>
</tr>

<tr>
<td> self-dual </td>
<td> whether the L-function is self-dual </td>
<td> boolean </td>
<td> - </td>
<td> True </td>
<td> </td>
</tr>

<tr>
<td> special_values </td>
<td> special values of the L-function </td>
<td> string </td>
<td> - </td>
<td> u'[[1,0.09049039083242963]]' </td>
<td> </td>
</tr>

<tr>
<td> st_group </td>
<td> Sato-Tate group </td>
<td> string </td>
<td> - </td>
<td> u'E_6' </td>
<td> </td>
</tr>

<tr>
<td> zeroes </td>
<td> first zeroes (symmetric) </td>
<td> string </td>
<td> - </td>
<td> u'[-19.33846444803068, ... ] </td>
<td> </td>
</tr>

</table>
