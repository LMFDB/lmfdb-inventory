# Database hmfs

|||
|---|---|
|**Description**|Hilbert modular forms|
|**Status**|[production](http://www.lmfdb.org/ModularForm/GL2/TotallyReal/)|
|**Contact**|[John Voight](https://github.com/jvoight)|
|**Code**|[hilbert_modular_forms](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/hilbert_modular_forms)|
|**Collections**|[fields](http://www.lmfdb.org/api/hmfs/fields), [forms](http://www.lmfdb.org/api/hmfs/forms)|

**Notes**: In good shape, but there are many remaining feature requests.

**Todo**: See issues

## Collection fields

* Content: Totally real fields, for Hilbert modular forms
* Contributors: John Cremona, Lassina Dembele, Steve Donnelly, Aurel Page, and John Voight
* Origin: see arxiv:1605.02637
* Extent: The database contains 368,356 Hilbert newforms over 400 totally real number fields of degree up to 6.

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
<td> label </td><td> field label </td><td> string </td><td> -
</td><td> '3.3.49.1' </td>
<td>&nbsp;</td></tr>

<tr>
<td> degree </td><td> field degree </td><td> int </td><td> -
</td><td> 2 </td>
<td>&nbsp;</td></tr>

<tr>
<td> discriminant </td><td> field discriminant </td><td> int </td><td> -
</td><td> 49 </td>
<td>&nbsp;</td></tr>

<tr>
<td> narrow_class_no </td><td> narrow class number </td><td> int </td><td> -
</td><td> 2 </td>
<td>&nbsp;</td></tr>

<tr>
<td> primes </td><td> fixed ordered list of primes </td><td> list of strings representing prime ideals [norm, integer generator, extra generator]</td><td> -
</td><td> [u'[7, 7, 2*w^2 - w - 3]', u'[8, 2, 2]', ...] </td>
<td>&nbsp;</td></tr>

<tr>
<td> ideals </td><td> fixed ordered list of ideals </td><td> list of strings representing prime ideals [norm, integer generator, extra generator]</td><td> -
</td><td> [u'[1, 1, 1]', u'[7, 7, 2*w^2 - w - 3]', ...] </td>
<td>&nbsp;</td></tr>

</table>

Index information on collection fields:

-  Not intended for searching

## Collection forms

* Content: Hilbert modular forms over totally real fields
* Contributors: John Cremona, Lassina Dembele, Steve Donnelly, Aurel Page, and John Voight
* Origin: see arxiv:1605.02637
* Extent: The database contains 368,356 Hilbert newforms over 400 totally real number fields of degree up to 6.

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
<td> field_label </td><td> base field label </td><td> string </td><td> -
</td><td> u'3.3.49.1' </td>
<td>&nbsp;</td></tr>

<tr>
<td> deg </td><td> base field degree </td><td> int </td><td> -
</td><td> 3 </td>
<td>&nbsp;</td></tr>

<tr>
<td> disc </td><td> base field discriminant </td><td> int </td><td> -
</td><td> 49 </td>
<td>&nbsp;</td></tr>

<tr>
<td> label </td><td> form label </td><td> string </td><td> -
</td><td> u'3.3.49.1-27.1-a' </td>
<td>&nbsp;</td></tr>

<tr>
<td> short_label </td><td> form short label </td><td> string </td><td> -
</td><td> u'27.1-a' </td>
<td>&nbsp;</td></tr>

<tr>
<td> label_nsuffix </td><td> label numerical suffix </td><td> int </td><td> -
</td><td> 0 </td>
<td>&nbsp;</td></tr>

<tr>
<td> label_suffix </td><td> label (alpha) suffix </td><td> string </td><td> -
</td><td> u'a' </td>
<td>&nbsp;</td></tr>

<tr>
<td> level_ideal </td><td> level ideal definition </td><td> string </td><td> -
</td><td> u'[27, 3, 3]' </td>
<td>&nbsp;</td></tr>

<tr>
<td> level_label </td><td> level ideal label </td><td> string </td><td> -
</td><td> u'27.1' </td>
<td>&nbsp;</td></tr>

<tr>
<td> level_norm </td><td> level ideal norm  </td><td> int </td><td> -
</td><td> 27 </td>
<td>&nbsp;</td></tr>

<tr>
<td> weight </td><td> weight </td><td> string </td><td> -
</td><td> u'[2, 2, 2]' </td>
<td>&nbsp;</td></tr>

<tr>
<td> parallel_weight </td><td> parallel weight </td><td> int </td><td> -
</td><td> 2 </td>
<td>&nbsp;</td></tr>

<tr>
<td> dimension </td><td> dimension of Hecke constituent space </td><td> int </td><td> -
</td><td> 1 </td>
<td>&nbsp;</td></tr>

<tr>
<td> is_CM </td><td> is a CM form? </td><td> string </td><td> -
</td><td> u'no' </td>
<td>&nbsp;</td></tr>

<tr>
<td> is_base_change </td><td> is a base change form? </td><td> string </td><td> -
</td><td> u'yes' </td>
<td>&nbsp;</td></tr>

<tr>
<td> hecke_polynomial </td><td> defining polynomial for Hecke field </td><td> string representing a polynomial in x </td><td> -
</td><td> u'x^2 - 5' </td>
<td>&nbsp;</td></tr>

<tr>
<td> hecke_eigenvalues </td><td> Hecke eigenvalues </td><td> list of strings representing polynomials in x </td><td> -
</td><td> [u'-5', u'-4', u'1', u'1', ...] </td>
<td>&nbsp;</td></tr>

<tr>
<td> AL_eigenvalues </td><td> Atkin-Lehner eigenvalues </td><td> list of lists of strings, a pair [ideal definition, eigenvalue] for each Atkin-Lehner prime </td><td> -
</td><td> [[u'[27, 3, 3]', u'-1']] </td>
<td>&nbsp;</td></tr>

<tr>
<td> AL_eigenvalues_fixed </td><td> are Atkin-Lehner eigenvalues fixed? </td><td>  </td><td> -
</td><td> u'done' </td>
<td>&nbsp;</td></tr>

</table>
