# Chart Sheet Properties

This repository holds meta-information required to generate charts (e.g. adopted from the [IHO's INT Charts](http://www.iho.int/srv1/index.php?option=com_content&view=article&id=312&lang=en)) from the various OpenSeaMap data sources.

Upon the first discussion, this would be something like:

* INT number
* INT name
* min + max / lat + lon
* published scale
* National number (prefixed by country code?)
* National name

More details on the related wiki page: [Catalogue of INT Charts](http://wiki.openseamap.org/wiki/OpenSeaMap-dev:Catalogue_of_INT_Charts)

# IHO Publication S-11 and structure

Many (all?) of the above details can be found as PDF documents provided by the
IHO as [PUB S-11](http://www.iho.int/iho_pubs/standard/S-11/S-11.htm) in *Part
B*. The structure of this repository therefore reflects the one currently given
by the IHO.

## Structure of `IHO_PUB_S-11`

This is the top-level directory containing all the chart information. Its
contents are described in the file `0_INDEX.csv` that corresponds to the table
on the IHO website. It therefore contains exactly three columns:

* `File` - the region name (e.g. *Region F*).
  * Each entry reflects the name of a sub-directory that is located within
  the top-level directory. Those will be referred to as the "*Region
  directories*" below.
* `Area` - the region's description (e.g. *Mediterranean & Black Seas*).
* `Comment` - the last update (e.g. *Edition 2.0.4 - December 2012*).

## Structure of *Region* directories

Each directory is required to have a `0_INDEX.csv` file of its own. They have
exactly two columns:
* The index number:
  * An internal number assigned by the OpenSeaMap project that corresponds to
  the sequence of sections listed in the different Region PDF files.
  * The number corresponds to a file of the same name (appended by the suffix
  `.csv`), further down referred to as the "*Section*" files.
* The section name:
  * The (english!) name of the section as given in the PDF. Examples:
    * *FROM COASTS OF THE CHANNEL AND OF THE NORTH SEA TO ICELAND*
    * *WESTERN ENGLISH CHANNEL*
  * This is purely descriptive (a "human readable name") and not reflected in
  any file or directory name.

## Structure of *Section* files

The *Section* CSV files directly correspond to the tables in the various
*Region* PDF files. They contain 11 columns with the content as follows:

* INT No.
* Prod.
* National No.
* Title
* Southern limit
* Northern limit
* Western limit
* Eastern limit
* Date
* Scale
* Lat
* 
