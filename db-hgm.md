# Database hgm

| | |
|---|---|
|**Description**|Hypergeometric motives|
|**Status**|[beta](http://beta.lmfdb.org/Motive/Hypergeometric/Q/)|
|**Contact**|[John Jones](https://github.com/jwj61)|
|**Code**|[motives](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/motives)|
|**Collections**|[families](http://beta.lmfdb.org/api/hgm/families), [motives](http://beta.lmfdb.org/api/hgm/motives)|

**Todo**:
* expand the range of the data

## Collection families
 * **_id** (ObjectId): object id created by mongo
<p>**Example**: ObjectId('5230a4330e74fe21b086363f')</p>
 * **A** (list of ints):
<p>**Example**: [2]</p>
 * **B** (list of ints):
<p>**Example**: [1]</p>
 * **degree** (int):
<p>**Example**: 1</p>
 * **gal2** (string):
<p>**Example**: O(1,2)</p>
 * **gal3** (string):
<p>**Example**: 2</p>
 * **gal5** (string):
<p>**Example**: 2</p>
 * **gal7** (string):
<p>**Example**: 2</p>
 * **hodge** (list of ints):
<p>**Example**: [1]</p>
 * **label** (string):
<p>**Example**: A2_B1</p>
 * **weight** (int):
<p>**Example**: 0</p>

## Indexes families
 * {'**A**': 1}: 
 * {'**B**': 1}: 
 * {'**degree**': 1}: 
 * {'**hodge**': 1}: 
 * {'**label**': 1}: 
 * {'**weight**': 1}: 

## Collection motives
 * **_id** (): object id created by mongo
<p>**Example**: ObjectID('540f1835214ebc5af7a7f76c')</p>
 * **A** (list of ints):
<p>**Example**: [4, 4, 4]</p>
 * **B** (list of ints):
<p>**Example**: [1, 2, 6, 6]</p>
 * **a2** (list of ints):
<p>**Example**: [2, 2, 2, 2, 2, 2]</p>
 * **a3** (list of ints):
<p>**Example**: [1, 1, 1, 1, 1, 1]</p>
 * **a5** (list of ints):
<p>**Example**: [1, 1, 1, 1, 1, 1]</p>
 * **a7** (list of ints):
<p>**Example**: [1, 1, 1, 1, 1, 1]</p>
 * **ae2** (list of ints):
<p>**Example**: [1, 1, 1, 1, 1, 1]</p>
 * **ae3** (list of ints):
<p>**Example**: [2, 2, 2, 2, 2, 2]</p>
 * **ae5** (list of ints):
<p>**Example**: [2, 2, 2, 2, 2, 2]</p>
 * **ae7** (list of ints):
<p>**Example**: [2, 2, 2, 2, 2, 2]</p>
 * **b2** (list of ints):
<p>**Example**: [1, 2, 2, 2, 2, 2]</p>
 * **b3** (list of ints):
<p>**Example**: [1, 1, 3, 3]</p>
 * **b5** (list of ints):
<p>**Example**: [1, 1, 1, 1, 1, 1]</p>
 * **b7** (list of ints):
<p>**Example**: [1, 1, 1, 1, 1, 1]</p>
 * **be2** (list of ints):
<p>**Example**: [1, 1, 3, 3]</p>
 * **be3** (list of ints):
<p>**Example**: [1, 2, 2, 2, 2, 2]</p>
 * **be5** (list of ints):
<p>**Example**: [1, 2, 6, 6]</p>
 * **be7** (list of ints):
<p>**Example**: [1, 2, 6, 6]</p>
 * **centralval** (string):
<p>**Example**: noncrit</p>
 * **coeffs** (list of ints):
<p>**Example**: [1, 0, 18, 0, -14, 0, -60, 0, 243, 0, 16, 0, 203, 0, -252, 0, -111, 0, 75, 0, -1080, 0, 113, 0, -109, 0, 2916, 0, 967, 0, -76, 0, 288, 0, 840, 0, 1291, 0, 3654, 0, -1967, 0, -3173, 0, -3402, 0, -3855, 0, 2361, 0, -1998, 0, 2434, 0, -224, 0, 1350, 0, -5893, 0, 4859, 0, -14580, 0, -2842, 0, 5275, 0, 2034, 0, 2657, 0, -3230, 0, -1962, 0, -960, 0, -975, 0, 32805, 0, 8160, 0, 1554, 0, 17406, 0, -9455, 0, -12180, 0, -1368, 0, -1050, 0, -382, 0, 3888, 0]</p>
 * **cond** (int):
<p>**Example**: 165888</p>
 * **degree** (int):
<p>**Example**: 6</p>
 * **hodge** (list of ints):
<p>**Example**: [1, 1, 2, 1, 1]</p>
 * **label** (string):
<p>**Example**: A4.4.4_B1.2.6.6_t1.1</p>
 * **locinfo** ():
<p>**Example**: [[11, ['1'], 1, 1, 1, 1], [4, ['1', '-18', '81'], 1, 1, 2, 3], [0, ['1', '14', '305', '7625', '218750', '9765625'], 3, 10, 1, 24], [0, ['1', '60', '1239', '-60711', '-7058940', '-282475249'], 3, 5, 6, 6], [0, ['1', '-16', '-9889', '-1196569', '-28344976', '25937424601'], 3, 10, 6, 24], [0, ['1', '-203', '6578', '1111682', '-979842227', '137858491849'], 1, 4, 26, 48], [0, ['1', '111', '27166', '-7850974', '-2679270159', '-2015993900449'], 1, 4, 6, 24], [0, ['1', '-75', '18354', '6625794', '-3528441075', '6131066257801'], 1, 10, 6, 6], [0, ['1', '-113', '-256818', '135856722', '16728055457', '-41426511213649'], 1, 4, 2, 75], [0, ['1', '-967', '113390', '95360990', '-575194151407', '420707233300201'], 1, 10, 6, 24]]</p>
 * **req** (int):
<p>**Example**: 2350</p>
 * **sig** (int):
<p>**Example**: -1</p>
 * **sign** (int):
<p>**Example**: 1</p>
 * **t** (rational stored as list of 2 ints):
<p>**Example**: [1, 1]</p>
 * **weight** (int):
<p>**Example**: 4</p>

## Indexes motives
 * {'**A**': 1}: 
 * {'**B**': 1}: 
 * {'**a2**': 1}: 
 * {'**a3**': 1}: 
 * {'**a5**': 1}: 
 * {'**a7**': 1}: 
 * {'**b2**': 1}: 
 * {'**b3**': 1}: 
 * {'**b5**': 1}: 
 * {'**b7**': 1}: 
 * {'**cond**': 1, '**label**': 1}: 
 * {'**degree**': 1}: 
 * {'**hodge**': 1}: 
 * {'**label**': 1}: 
 * {'**sign**': 1}: 
 * {'**t**': 1}: 
 * {'**weight**': 1}: 
