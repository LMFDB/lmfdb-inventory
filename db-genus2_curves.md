# Database genus2_curves


| | |
|---|---|
|**Description**|Genus 2 curves over **Q**|
|**Status**|[production](http://www.lmfdb.org/Genus2Curve/Q/)|
|**Contact**|[Andrew Sutherland](https://github.com/AndrewVSutherland)|
|**Code**|[genus2_curves](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/genus2_curves/)|
|**Collections**|[curves](http://www.lmfdb.org/api/genus2_curves/curves), [endomorphisms](http://www.lmfdb.org/api/genus2_curves/endomorphisms)|

**Contributors**: Andrew Booker, Jeroen Sijsling, Andrew Sutherland, John Voight, and Dan Yasaki

**Todo**: Match all automorphic friends and move data in temporary Lfunctions.instances collection to Lfunctions database.


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
<td> assigned by Mongo; contains creation timestamp</td>
</tr>

<tr>
<td> aut_grp_id </td>
<td> automorphism group (specified by GAP id) </td>
<td> string encoding list of integers, no spaces </td>
<td> - </td>
<td> u;[6,2]' </td>
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
<td> abs_disc </td>
<td> absolute discriminant </td>
<td> integer </td>
<td> NN </td>
<td> 169 </td>
<td> </td>
</tr>

<tr>
<td> disc_key </td>
<td> representation of the discriminant D of the curve: the first three digits
are floor(log_10 (|D|)), which is followed by digits representing the absolute
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
<td> g2_inv </td>
<td> G2 invariants </td>
<td> string encoding list of strings representing rationals, no spaces </td>
<td> - </td>
<td> u"['-1/169','33/169','43/169']" </td>
<td> </td>
</tr>

<tr>
<td> geom_aut_grp_id </td>
<td> geometric automorphism group (shorthand) </td>
<td> string encoding list of 2 integers, no spaces </td>
<td> - </td>
<td> u'[12,4]' </td>
<td> </td>
</tr>

<tr>
<td> igusa_inv </td>
<td> Igusa invariants </td>
<td> string encoding list of strings representing integers, no spaces </td>
<td> - </td>
<td> u"['1','-33','-43','-283','-169']" </td>
<td> </td>
</tr>

<tr>
<td> igusa_clebsch_inv </td>
<td> Igusa-Clebsch invariants </td>
<td> string encoding list of strings representing integers </td>
<td> - </td>
<td> u"['8','3172','30056','-692224']" </td>
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
<td> eqn </td>
<td> coefficients of minimal equation y^2+h(x)y=f(x) </td>
<td> string representing list of 2 lists of integers, no spaces</td>
<td> - </td>
<td> u'[[0,0,0,0,1,1],[1,1,0,1]] </td>
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
<td> torsion_subgroup </td>
<td> rational torsion group of the Jacobian, represented by the invariant
factors [d_1, d_2, ...] for which this torsion group is isomorphic to ZZ / d_1
ZZ x ZZ / d_2 ZZ x ...  </td>
<td> string encoding list of integers, no spaces </td>
<td> - </td>
<td> u'[2,2,4]' </td>
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

<tr>
<td> analytic_rank </td>
<td> analytic rank upper bound that is believed to be tight (known for rank 0 or 1) </td>
<td> integer </td>
<td> NN_0 </td>
<td> 0 </td>
<td> </td>
</tr>

<tr>
<td> has_square_sha </td>
<td> assuming Sha is finite, true if the order of Sha is a square, false otherwise (in which case it is 2 times a square, by a result of Poonen-Stoll 1999) </td>
<td> boolean </td>
<td> - </td>
<td> True </td>
<td> </td>
</tr>

<tr>
<td> locally_solvable </td>
<td> true if the curve has rational points locally everywhere (i.e. over every completion of Q, including R) </td>
<td> boolean </td>
<td> - </td>
<td> True </td>
<td> </td>
</tr>

<tr>
<td> globally_solvable </td>
<td> 1 if known to have rational points, 0 if known to have no rational points, -1 if unknown </td>
<td> NN </td>
<td> 0 </td>
<td> True </td>
<td> </td>
</tr>

</table>

### Index information for curves collection

* abs_disc -- search/browse
* analytic_rank -- search/browse
* aut_grp_id -- search/browse
* class -- list curves in isogeny class
* cond -- search/browse
* cond/class/disc_key/label -- sort order (all ascending)
* disc_key -- search/browse
* g2_inv -- list twists
* geom_aut_grp_id -- search/browse
* has_square_sha -- search/browse
* is_gl2_type -- search/browse
* is_simple_geom -- search/browse
* label -- search
* locally_solvable -- search/browse
* real_geom_end_alg -- search/browse (ST^0)
* st_group -- search/browse
* torsion_order -- search_browse
* torsion_subgroup -- search/browse
* curves.rand (auxilliary collection used for random objection access)

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
<td> Sato-Tate group over the algebraic closure (equivalently, its identity component) </td>
<td> string </td>
<td> - </td>
<td> E_1 </td>
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
<td> bad_lfactors </td>
<td> bad primes and the corresponding L-factors </td>
<td> string encoding list of pairs [p,c] where p is a bad prime and c is a list of the coefficients of the Euler factor at p </td>
<td> - </td>
<td> [[13, [1, 5, 13]]] </td>
<td> </td>
</tr>

</table>

### Index information for endomorphisms collection:
* label -- lookup
