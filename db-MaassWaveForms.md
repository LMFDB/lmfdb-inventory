# Database MaassWaveForms

| | |
|---|---|
|**Description**|Maass wave forms|
|**Status**|[production](http://www.lmfdb.org/ModularForm/GL2/Q/Maass/)|
|**Contact**|[Stefan Lemurell](https://github.com/lemurell), [Fredrik Strömberg](https://github.com/fredstro)|
|**Code**|[modular_forms/maass_forms/maass_waveforms](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/modular_forms/maass_forms/maass_waveforms/)|
|**Collections**|to be added|

**Todo**: Document or delete the collections below, identify which are actually needed on www.lmfdb.org, and put in links to them in the table above.

## Collection Coefficients
* Field 1: ...
* Field 2: ...

## Collection Coefficients.chunks
* Field 1: ...
* Field 2: ...

## Collection Coefficients.files
* Field 1: ...
* Field 2: ...

## Collection DirChars
* Field 1: ...
* Field 2: ...

## Collection DirCharsConrey
* Field 1: ...
* Field 2: ...

## Collection DirCharsSage
* Field 1: ...
* Field 2: ...

## Collection FS
    Description: Maassform data.
| Field | type | Example| Description |
|-------|------|--------|---------------|
|`Character` | integer  | 1 | character number in Conrey numbering if `Conrey` is set to 1 else in Sage ordering,
|`Coefficient` | list | [1.0, 1.5493044779412872,  0.24689977245382455, 1.400344365368927] | A short list of Fourier coefficients c(1),c(2),...|
| `Conrey` | integer | 1 | 1 if Conrey character numbers are used, else 0|
| `Contributor` | string | 'HT' | identifier of person who originally submitted  this data, e.g. 'HT' is Holger Then, FS is Fredrik Stromberg etc. (coefficients may have been added later by other contributors, identified in the corresponding coefficient record)|
| `Cusp_evs` | list | [1] | list of (complex) numbers such that the Fourier coefficients at that cusp are proportional to the ones at infinity with this constant.  Such constants exists if the corresponding Atkin-Lehner operators are cusp normalisers. The first '1' corresponds to the cusp at infinity. |
| `Dim` | integer | 1 | dimension of the eigenspace containing this Maass form (estimated heuristically / numerically) 
| `Dimension` | integer | 1 | probably a duplicate of `Dim`|
| `Eigenvalue` | float | 13.7797513518907 | Spectral parameter R corresponding to this Maass form, s.t. the actual eigenvalue is lambda=1/4+R^2 |
| `Error` | float | 6.050715484207103e-15 | estimate of the error in the eigenvalue}
| `Level` | integer | 1 | level|
| `M0` | integer | 0 | the M0 which was used as input to the algorithm for computing the eigenvalue (if set correctly it should be > 0)|
| `Norm` | float | 1.0 | describes the normalisation used for the coefficients, 1.0 means Hecke normalisation so c(1)=1, other} alternatives (not used currently) would be L2-normalisation}
| `Numc` | inte | 5000 | number of coefficients available for this form |
| `Symmetry` | integer | 0 | 1 if this Maass form is even and 0 if it is odd|
| `Weight` | float | 0.0 | the weight of the Maass form|
| `Y` | float | 0 | the Y which was used as input to the algorithm for computing the eigenvalue (if set correctly it should be > 0)}
| `coeff_id` | objectid | ObjectId(`4f87f0f388aece21410000e8`) | id of the corresponding coefficient record|
| `dim` | integer | 1 | probably a third duplicate of 'Dim' and 'Dimension'|

## Collection Table.chunks
* Field 1: ...
* Field 2: ...

## Collection Table.files
* Field 1: ...
* Field 2: ...

## Collection metadata
* Field 1: ...
* Field 2: ...

## Collection maassform_plots
    Description: contains plots of Maassforms in the corresponding fundamental domain
* Field 1: ...
* Field 2: ...

