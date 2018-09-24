pypandas
===========
Directly include pandas dataframes into latex documents.
Since pandas can read in excel files, csv, whitespace seprated plain text and many binary formats, this plugin allows data to be nicely included as table format.

## Requirements
The following latex packages are required:
- pythontex
- booktabs

The following python packages are also needed:
- pandas

## Installation
The simplest is to just copy the pypandas.sty file into your project's directory.  Instructions can be found online for how to install a package as part of a system-wide installation.
Yeah, I'm being very lazy there...

## Usage
To include a dataframe as a table, just do:

```latex
\includepandastable{my_dataframe.txt}
```
or

```latex
\includepandascsv{my_dataframe.csv}
```
if the file is CSV.

You can pass options through to the underlying pandas `read_*` functions, although at this time the interface is pretty nasty.  
You need to pass through a python-like dictionary of keyword arguments:
```
\includepandastable["nrows":6, "usecols":\["n", "nvar"\]]{my_dataframe.txt}
```
I'll be trying to improve that in the future once I can work out how...
