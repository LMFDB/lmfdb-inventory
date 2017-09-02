# Database Lfunctions

| | |
|---|---|
|**Description**|L-functions|
|**Status**|[production](http://www.lmfdb.org/L/)|
|**Contact**|[Jonathan Bober](https://github.com/jwbober), [David Farmer](https://github.com/davidfarmer)|
|**Code**|[lfunctions](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/lfunctions)|
|**Collections**|[instances](http://www.lmfdb.org/api/Lfunctions/instances), [Lfunctions](http://www.lmfdb.org/api/Lfunctions/Lfunctions)|

**Todo**: Document indexes for Lfunctions (some appear to be obsolete or never used)

## Collection instances

| Field | type | Example|
|----------|    ------     | -----   |
|`url`| string | 'EllipticCurve/Q/162/d'|
|`Lhash`| string |    | 
|`type`| string | 'ECQ' or 'G2Q' or 'DIR' or ...|

Indexes for instances collection:
* **Lhash**: lookup by L-function hash (used to find all objects with the same L-function)
* **url**: lookup by object homepage URL
* **type**: used to filter instances by type

## Collection Lfunctions

<table border=2>
    <tr>
        <th>Field</th>
        <th>Description</th>
        <th>Type </th>
        <th>Example of stored data</th>
        <th>Remarks</th>
    </tr>
    <tr>
        <th> _id </th>
        <td> Mongo id </td>
        <td> ObjectId </td>
        <td> - </td>
        <td> assigned by Mongo; contains creation timestamp</td>
    </tr>
    <tr>
        <th> origin </th>
        <td> an LMFDB url from which we have derived this data</td>
        <td> string </td>
        <td> u'EllipticCurve/Q/162/d' </td>
        <td> Not every object has this attribute </td>
    </tr>
    <tr>
        <th>load_key</th>
        <td> 
            a string identifying who uploaded the entry</td>
        </td>
        <td>
            string
        </td>
        <td>
            u'Cremona'               
            <br>
            u'costa'
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <th>
            Lhash          
        </th>
        <td>
            A string that is used to connect the collection instances and this collection.
            See below
            </td>
            <td>
            string      
        </td>
        <td>
            <ul>
                <li>
                    u'/ModularForm/GL3/Q/Maass/1/1/-13.5965_-4.76468/1.04846245/'
                </li>
                <li>
                    u'12896406231020588'
                </li>
                <li>
                    u'12896406231020588,1261421830691399758'
                </li>
                <li>
                    u''_3835819448407117806631286663382'
                </li>
            </ul>
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <th>
            `conductor`      
        </th>
        <td>
            The conductor of the L-function
        </td>
        <td>
            integer     
        </td>
        <td>
            162                   
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <th>
            degree
        </th>
        <td>
            The degree of the L-function
        </td>
        <td>
            integer     
        </td>
        <td>
            2 
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <th>
            motivic_weight
        </th>
        <td>
            the motivic weight of the L-function
        </td>
        <td>
            integer     
        </td>
        <td>
            1 
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <th>`gamma_factors`  
        </th>
        <td>
            a pair of lists of numbers the first list being the `Gamma_R` shifts, and the second list being the `Gamma_C` shifts. stored, e.g., '1/2' if exact. 
        </td>
        <td>
            list of integers or string representing rational numbers
        </td>
        <td>
            [[],[0]] 
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <th>
            primitive
        </th>
        <td>
            True iff the L-function is primitive
        </td>
        <td>
            boolean     
        </td>
        <td>
            True  
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <th>
            root_number
        </th>
        <td>
            the root number of the L-function
        </td>
        <td>
            string or an integer or a floating point number 
        </td>
        <td>
            1
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <td>
            sign_arg
        </td>
        <td>
            the argument of the root number
        </td>
        <td>
            floating point number      
        </td>
        <td>
            0     
        </td>
        <td>
    </tr>
    <tr>
        <th>
            central_character 
        </th>
        <td>
            the central character of the L-function using the conrey label
        </td>
        <td>
            conrey label stored as a string
        </td>
        <td>
            '162.1' 
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <th>
            self_dual
        </th>
        <td>
            a boolean identifying if the L-function is self dual
        </td>
        <td>
            bool        
        </td>
        <td>
            True 
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <td>`conjugate`      
        </td>
        <td>
            The Lhash string of the conjugate
        </td>
        <td>
            string
        </td>
        <td>
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <th>
            symmetry_type
        </th>
        <td>
            identifies the symmetry type of the Galois representation associated to L-function
        </td>
        <td>
            string      
        </td>
        <td>
            'unitary' or 'orthogonal' or 'symplectic' 
        </td>
        <td>
    </tr>
    <tr>
        <th>
            algebraic      
        </th>
        <td>
            identifies if the L-function is of an algebraic nature
        </td>
        <td>
            boolean      
        </td>
        <td>
            True
        </td>
    </tr>
    <tr>
        <th>
            leading_term
        </th>
        <td>
            Leading term of the Taylor expansion of the L-function centered at t = 0 on the critical line
        </td>
        <td>
            floating point number      
        </td>
        <td>
            1.736780166943524 
        </td>
        <td>
            Not every object will have this attribute
        </td>
    </tr>
    <tr>
        <th>
            values
        </th>
        <td>
            ?????
        </td>
        <td>
            list of pairs of numbers
        </td>
        <td>
            [] 
        </td>
        <td>
            Optional
        </td>
    </tr>
    <tr>
        <th>
            euler_factors
        </th>
        <td>
            All the euler factors up to some prime
        </td>
        <td>
            list of lists (little endian polynomials) 
        </td>
        <td>
            [[1, -1], [1], [1, -3, 5], [1, 4, 7], ...] 
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <th>
            bad_lfactors
        </th>
        <td>
            list all the bad euler factors
        </td>
        <td>
            list of pairs pairs (prime, list(polynomial))  
        </td>
        <td>
            [[2, [1, -1]], [3, [1]]] 
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <th>
            dirichlet_coefficients
        </th>
        <td>
            lists of dirichlet coefficients
        </td>
        <td>
            list of numbers 
        </td>
        <td>
            ???
        </td>
        <td>
            Optional
        </td>
    </tr>
    <tr>
        <th>
            st_group
        </th>
        <td>
            a string representing the Sato-Tate group of to the Galois representation associate to this L-function
        </td>
        <td>
            'SU(2)' 
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <th>
            types
        </th>
        <td>
            ??
        </td>
        <td>
            list of strings ('EC', 'MF', 'DIR', 'G2'...?) 
        </td>
        <td>
            ['EC', 'MF'] 
        </td>
        <td>
            Optional??
        </td>
    </tr>
    <tr>
        <th>
            order_of_vanishing
        </th>
        <td>
            Order of vanishing of the L-function
        </td>
        <td>
            integer 
        </td>
        <td>
            0 
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <th>
            coefficient_field
        </th>
        <td>
            The field of coefficients of the Dirichlet coefficients
        </td>
        <td>
            string (a field label or description)     
        </td>
        <td>
            '1.1.1.1' 
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <th>
            analytic_normalization
        </th>
        <td>
            a floating point number representing how to from the algebraic normalization to analytic normalization
        </td>
        <td>
            floating point number                                
        </td>
        <td>
            .5 
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <th>
            accuracy
        </th>
        <td>
            bit accuracy (after the decimal point) of the nontrivial zeros
        </td>
        <td>
            integer
        </td>
        <td>
            100
        </td>
        <td>
            Not optional! However, not all entries in the DB have it at the moment
        </td>
    </tr>
    <tr>
        <th>
            positive_zeros
        </th>
        <td>
            List of strictly positive zeros stored as strings
        </td>
        <td>
            list of floats
        </td>
        <td>
            [u'2.583212561785407', u'3.900749965053077', u'5.857403178467226', u'7.384090002225106', u'8.414042470938793', u'9.493169657561115', u'10.36534498208387', u'12.03947269145467', u'12.92148359796848', u'14.10055486094281', u'14.62109083140550', u'15.77984643452670', u'16.67808032918220', u'17.84322890580079', u'19.23339240606807', u'19.37702400620986']
        </td>
        <td>
            Not all digits need to be correct.
            See accuracy, to get the right number of bits
        </td>
    </tr>
    <tr>
        <th>
            plot_values
        </th>
        <td>
            list of numbers (floats expected), which are values of Z(k * plot_delta) for k = 0, 1, 2, ... 
        </td>
        <td>
            list of floats
        </td>
        <td>
            [1.263098962276239, ...., 0.5305687471043774]
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <th>
            plot_delta
        </th>
        <td>
            the spacing on the x
        </td>
        <td>
            number (float expected) 
        </td>
        <td>
            0.25
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <th>
            z1, z2, z3
        </th>
        <td>
            imaginary part of the kth positive zero
        </td>
        <td>
            string representing a floating point
        </td>
        <td>
            5.85740317846722
        </td>
        <td>
        </td>
    </tr>
    <tr>
        <th>
            a2, a3, ..., a10             
        </th>
        <td>
            pair of floats (a complex number), the embedding of the kth Dirichlet coefficient in analytic normalization
            as a complex number
        </td>
        <td>
           pair of floats 
        </td>
        <td>
            u'[0.0, 0,5]'
        </td>
        <td></td>
    </tr>
    <tr>
        <th>
            A2, A3, ..., A10             
        </th>
        <td>
            string representing the kth Dirichlet coefficient in arithmetic normalization
        </td>
        <td>
            string
        </td>
        <td>
            u'2'
        </td>
        <td></td>
    </tr>
</table>

### Lhash description

#### Modular forms
 it matches the url of the origin object

#### genus 2 curves and elliptic curves over QQ
it's an integer stored as a string, the integer is obtained by the Hash function described in Section 4.3 of <a href="https://arxiv.org/abs/1602.03715">arXiv 1602.03715</a>

####  elliptic curves over a numberfield
* For a primitive L-function we use `str(<first zero of L_0> * 2^100).round())`.

* If we do not have enough precision for the integer above to be correct we prepend an underscore.

* For the nonprimitive case, if the factors are on the database, it's the Lhash of the factors separated by a comma, with no spaces.

* For last, if one of the primitive factors is not in the database we use
`str(<first zero of L_0> * 2^100).round())` prepended with an underscore.



