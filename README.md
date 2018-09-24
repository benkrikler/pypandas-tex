pypandas
===========
Directly include pandas dataframes into latex documents.
Since pandas can read in excel files, csv, whitespace seprated plain text and many binary formats, this plugin allows data to be nicely included as table format.

This is a fairly simple bridge between latex and pandas exploiting the fact that pythontex has added support to run python code within latex, and that pandas can already dump out latex code.
But by being able to run this directly from the latex document should (once fully implemented) allow for easier control and coherence of the resulting table with the rest of the document.

## Requirements
The following latex packages are required:
- [pythontex](https://www.ctan.org/pkg/pythontex)
- [booktabs](https://www.ctan.org/pkg/booktabs) -- needed by Pandas `to_latex`

The following python packages are also needed:
- [Pandas](https://pandas.pydata.org/) v0.20 or greater, when the `to_latex` function was added.

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
