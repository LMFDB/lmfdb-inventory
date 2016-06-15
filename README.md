# LMFDB Database Inventory

## Layers
* Mongo DB (contains databases)
* Database (contains collections)
* Collection (contains documents, aka records)
* Document (contains fields aka attributes)
* Field (a string, integer, float, boolean, dictionary, list, ...)

## Databases

The table below summarizes the various mongo db databases in the LMFDB.  Click links for more detailed information.
Database status is indicated by one of:
* prod -- visible on [www.lmfdb.org](http://www.lmfdb.org)
* beta -- visible on [beta.lmfb.org](http://beta.lmfdb.org)
* alpha -- available on [beta.lmfdb.org](http://beta.lmfdb.org) via direct URL access but not visible
* future -- in developement but not currently loaded by [website.py](https://github.com/LMFDB/lmfdb/blob/master/lmfdb/website.py)

|database|status|contact|code|collections|
|---|---|---|---|---|
|[HTPicard](https://github.com/LMFDB/lmfdb-inventory/blob/master/db-HTPicard.md)|[future](https://github.com/LMFDB/lmfdb/issues/1431#issuecomment-225549206)|[David Farmer](https://github.com/davidfarmer)|[picard/](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/modular_forms/maass_forms/picard/)|[picard](http://beta.lmfdb.org/api/HTPicard/picard)|
|[lat](https://github.com/LMFDB/lmfdb-inventory/edit/master/db-Lattices.md)|[production](http://www.lmfdb.org/Lattice)|[Samuele Anni](https://github.com/sanni85)|[lattice](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/lattice/)|[lat](http://www.lmfdb.org/api/Lattices/lat)|
|[Lfunctions](https://github.com/LMFDB/lmfdb-inventory/edit/master/db-Lfunctions.md)|[production](http://www.lmfdb.org/L/)|[Jonathan Bober](https://github.com/jwbober), [David&nbsp;Farmer](https://github.com/davidfarmer)|[lfunctions](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/lfunctions)|[instances](http://www.lmfdb.org/api/Lfunctions/instances), [Lfunctions](http://www.lmfdb.org/api/Lfunctions/Lfunctions)|
|[MaassWaveForms](https://github.com/LMFDB/lmfdb-inventory/blob/master/db-MaassWaveForms.md)|[production](http://www.lmfdb.org/ModularForm/GL2/Q/Maass/)|[Stefan Lemurell](https://github.com/lemurell), [Fredrik&nbsp;Strömberg](https://github.com/fredstro)|[maass_waveforms](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/modular_forms/maass_forms/maass_waveforms/)|to be added|
|[SL2Zsubgroups](https://github.com/LMFDB/lmfdb-inventory/blob/master/db-SL2Zsubgroups.md)|[future](https://github.com/LMFDB/lmfdb/issues/1407)|[Stefan Ehlen](https://github.com/sehlen)|[emf_utils.py](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/modular_forms/elliptic_modular_forms/backend/emf_utils.py)|[groups](http://beta.lmfdb.org/api/SL2Zsubgroups/groups)|
|[abvar](https://github.com/LMFDB/lmfdb-inventory/blob/master/db-abvar.md)|[future](https://github.com/LMFDB/lmfdb/issues/1431#issuecomment-225533734)|[David Roe](https://github.com/roed314)|none|[fq_iosg](http://beta.lmfdb.org/api/abvar/fq_isog)|
|[artin](https://github.com/LMFDB/lmfdb-inventory/edit/master/db-artin.md)|[production](http://www.lmfdb.org/ArtinRepresentation/)|[John Jones](https://github.com/jwj61)|[artin_representations](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/artin_representations)|[representations](http://www.lmfdb.org/api/artin/representations), [field_data](http://www.lmfdb.org/api/artin/field_data)|
|[bmfs](https://github.com/LMFDB/lmfdb-inventory/edit/master/db-bmfs.md)|[future](https://github.com/LMFDB/lmfdb/issues/1431#issuecomment-225529987)|[John Cremona](https://github.com/JohnCremona)|none|[dimensions](http://beta.lmfdb.org/api/bmfs/dimensions)|
|[curve_automorphisms](https://github.com/LMFDB/lmfdb-inventory/edit/master/db-curve_automorphisms.md)|[alpha](http://beta.lmfdb.org/HigherGenus/C/aut/)|[Jen Paulhus](https://github.com/jenpaulhus)|[higher_genus_w_automorphisms](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/higher_genus_w_automorphisms)|[families](http://beta.lmfdb.org/api/curve_automorphisms/families)|
|[elliptic_curves](https://github.com/LMFDB/lmfdb-inventory/edit/master/db-elliptic_curves.md)|[production](http://www.lmfdb.org/EllipticCurve/)|[John Cremona](https://github.com/JohnCremona)|[elliptic_curves](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/elliptic_curves/)|[curves](http://www.lmfdb.org/api/elliptic_curves/curves), [nfcurves](http://www.lmfdb.org/api/elliptic_curves/nfcurves), [padic_db](http://www.lmfdb.org/api/elliptic_curves/padic_db)|
|[genus2_curves](https://github.com/LMFDB/lmfdb-inventory/edit/master/db-genus2_curves.md)|[production](http://www.lmfdb.org/Genus2Curve/Q/)|[Andrew Sutherland](https://github.com/AndrewVSutherland)|[genus2_curves](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/genus2_curves/)|[curves](http://www.lmfdb.org/api/genus2_curves/curves), [endomorphisms](http://www.lmfdb.org/api/genus2_curves/endomorphisms)|
|[halfintegralmf](https://github.com/LMFDB/lmfdb-inventory/edit/master/db-halfintegralmf.md)|[alpha](http://beta.lmfdb.org/ModularForm/GL2/Q/holomorphic/half/)|[Samuele Anni](https://github.com/sanni85)|[half_integral_weight_forms](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/half_integral_weight_forms)|[forms](http://beta.lmfdb.org/api/halfintegralmf/forms)|

