# Database halfintegralmf

| | |
|---|---|
|**Description**|Half integral weight cuspforms spaces and Shimura decomposition|
|**Status**|[alpha](http://beta.lmfdb.org/ModularForm/GL2/Q/holomorphic/half/)|
|**Contact**|[Samuele Anni](https://github.com/sanni85)|
|**Code**|[half_integral_weight_forms](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/half_integral_weight_forms)|
|**Collections**|[forms](http://beta.lmfdb.org/api/halfintegralmf/forms)|

**Comments**:  Work in progress, check the branch half_integral on https://github.com/sanni85/lmfdb.git for the latest.  Data will be uploaded from [here](https://github.com/sanni85/half_integral_mf).

**Todo**:
* add index information for forms
* correct all the labels of classical newforms stored (since they changed in the last update)

## Collection forms

* **character** (string): character label in the LMFDB notation
* **dim** (int): dimension of the space
* **dimtheta** (int): dimension of the S0 subspace (see the shimura decomposition knowl [here](http://beta.lmfdb.org/knowledge/show/mf.half_integral_weight.shimura_decomposition))
* **label** (string): LMFDB label
* **level** (int): Level
* **newpart** (list of dictionaries): description of the subspace corresponding to the image of the shimura map. The entries of the dictionary contain the following fields: **dim_image** (int) the dimension of the subspace given by the image, **half_forms** (list of lists of strings) the coefficients (algebraic integers) of the q-expansions of the half integral weight newforms in the image, **mf_label**(string) the label of the classical newform which is mapped into this space of half integral weight cuspforms, **nf_label** (string) the label of the number field where the coefficients of the q-expansion belong to (this will be changed into the list of coefficients of a polynomial)
* **thetas** (list of strings): label of the characters appearing in the S0 subspace
* **weight** (int): double of the weight of the forms
 

## LMFDB label of an Half Integral Weight Cuspforms spaces

The LMFDB label has the following structure:

    level.weight_2.character_label


 ### One example of forms
 
 ```
{u'_id': ObjectId('55b9c5f7ffe9794ba58d8925'),
 u'character': u'1.1',
 u'dim': 5,
 u'dimtheta': 1,
 u'label': u'108.3_2.1.1',
 u'level': 108,
 u'newpart': [{u'dim_image': 2,
   u'half_forms': [[u'1',
     u'0',
     u'0',
     u'0',
     u'0',
     u'0',
     u'1',
     u'0',
     u'0',
     u'-2',
     u'0'],
    [u'0', u'0', u'0', u'1', u'0', u'0', u'-1', u'0', u'0', u'0', u'0']],
   u'mf_label': u'27.2a',
   u'nf_label': u'1.1.1.1'},
  {u'dim_image': 1,
   u'half_forms': [[u'1',
     u'-1',
     u'0',
     u'1',
     u'3',
     u'0',
     u'-1',
     u'-1',
     u'0',
     u'-3',
     u'-3']],
   u'mf_label': u'54.2a',
   u'nf_label': u'1.1.1.1'},
  {u'dim_image': 1,
   u'half_forms': [[u'0',
     u'0',
     u'1',
     u'0',
     u'0',
     u'-1',
     u'0',
     u'0',
     u'1',
     u'0',
     u'0',
     u'-1']],
   u'mf_label': u'54.2b',
   u'nf_label': u'1.1.1.1'}],
 u'thetas': [[u'3.2']],
 u'weight': 3}
 ```
