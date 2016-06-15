# LMFDB Database Inventory

## Layers

* Database (contains collections)
* Collection (contains documents, aka records)
* Document: (contains fields)
* Field: (an attribute of a document, need not exist in every document)
   * associations (dictionary), and nested dictionaries
   * string
   * integer
   * double
   * list of integer, list of strings, list of doubles, ...
   * boolean

## Databases

The following table summarizes the database that currently make up the LMFDB.  Click on the link for a database to see more detailed information about the database and the collections it contains.

|database|status|contact|code|collections|
|---|---|---|---|---|
|[HTPicard](https://github.com/LMFDB/lmfdb-inventory/blob/master/db-HTPicard.md)|future|[David Farmer](https://github.com/davidfarmer)|[modular_forms/maass_forms/picard/](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/modular_forms/maass_forms/picard/)|[picard](http://beta.lmfdb.org/api/HTPicard/picard)|
|[lat](https://github.com/LMFDB/lmfdb-inventory/edit/master/db-Lattices.md)|[production](http://www.lmfdb.org/Lattice)|[Samuele Anni](https://github.com/sanni85)|[lattice](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/lattice/)|[lat](http://www.lmfdb.org/api/Lattices/lat)|
|[Lfunctions](https://github.com/LMFDB/lmfdb-inventory/edit/master/db-Lfunctions.md)|[production](http://www.lmfdb.org/L/)|[Jonathan Bober](https://github.com/jwbober), [David&nbsp;Farmer](https://github.com/davidfarmer)|[lfunctions](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/lfunctions)|[instances](http://www.lmfdb.org/api/Lfunctions/instances), [Lfunctions](http://www.lmfdb.org/api/Lfunctions/Lfunctions)|
|[MaassWaveForms](https://github.com/LMFDB/lmfdb-inventory/blob/master/db-MaassWaveForms.md)|[production](http://www.lmfdb.org/ModularForm/GL2/Q/Maass/)|[Stefan Lemurell](https://github.com/lemurell), [Fredrik&nbsp;Strömberg](https://github.com/fredstro)|[modular_forms/maass_forms/maass_waveforms](https://github.com/LMFDB/lmfdb/tree/master/lmfdb/modular_forms/maass_forms/maass_waveforms/)|to be added|
