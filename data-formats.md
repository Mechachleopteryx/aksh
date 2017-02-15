+ [CSV](#csv)
+ [ELAN](#elan)
+ [Encoding](#encoding)
+ [JSON](#json)
+ [LaTeX](#latex)
+ [Markdown](#markdown)
+ [MAT](#mat)
+ [MetaData](#metadata)
+ [Pandoc](#pandoc)
+ [RDF](#rdf)
+ [XML](#xml)
+ [Standards](#standards)
    + [MetaData](#metadata)
+ [YAML](#yaml)

----

+ Research paper: Against a universal definition of ‘#type', http://tomasp.net/academic/papers/against-types/against-types.pdf
+ https://en.wikipedia.org/wiki/Comparison_of_data_serialization_formats
+ https://en.wikipedia.org/wiki/Category:Open_formats
+ [Markup Languages](https://en.wikipedia.org/wiki/Category:Markup_languages)
+ DTD : A [document type definition](https://en.wikipedia.org/wiki/Document_type_definition) is a set of markup declarations that define a document type for an SGML-family markup language (SGML, XML, HTML).

#### Compare Data Formats
+ http://www.yegor256.com/2015/11/16/json-vs-xml.html
+ http://www.cs.tufts.edu/comp/150IDS/final_papers/tstras01.1/FinalReport/FinalReport.html
+ https://blog.udemy.com/json-vs-xml/
+ http://stackoverflow.com/questions/4862310/json-and-xml-comparison
+ http://programmers.stackexchange.com/questions/224929/is-csv-a-good-alternative-to-xml-and-json
+ http://stackoverflow.com/questions/1820129/when-and-why-is-xml-preferable-to-csv

----

# CSV
+ http://petl.readthedocs.io/en/latest/
+ http://stackoverflow.com/questions/34338693/how-to-parse-csv-file-and-compute-stats-based-on-that-data/34339089
+ http://specs.frictionlessdata.io/csv-dialect/
+ [CSV Validation Research](https://github.com/theodi/csv-validation-research) :: This repository contains some sample files that show how different tools and data formats can be used to support the validation and description of CSV files.


### Schema
+ http://fileformats.archiveteam.org/wiki/CSV_Schema 
+ http://digital-preservation.github.io/csv-validator/

### NaN / NA 
+ http://pandas.pydata.org/pandas-docs/stable/missing_data.html
+ http://stackoverflow.com/questions/29530232/python-pandas-check-if-any-value-is-nan-in-dataframe

### statistics on tabular data (CSV)
+ https://docs.python.org/3/library/statistics.html
+ http://docs.scipy.org/doc/numpy/reference/generated/numpy.nanmin.html#numpy.nanmin

### Diff Binary files: Libreoffice and DVCS 
+ http://www-verimag.imag.fr/~moy/opendocument/
+ http://blog.riemann.cc/2013/04/23/versioning-of-openoffice-libreoffice-documents-using-git/
+ http://stackoverflow.com/questions/8795538/how-to-share-odt-doc-documents-over-git
+ http://stackoverflow.com/questions/8795538/how-to-share-odt-doc-documents-over-git

##### http://locallost.net/?p=278 

To resolve conflits on binary files, you can checkout the remote version and your version with the `–theirs’ and `–ours’ checkout flags. This allows you to inspect both version, then write back the correct resulting file.

```
$ git checkout --theirs -- doc/manual.odt
$ mv doc/manual.odt doc/theirs.manual.odt

$ git checkout --ours -- doc/manual.odt
$ mv doc/manual.odt doc/ours.manual.odt
```

Open and compare `theirs.manual.odt’ with `ours.manual.odt’, and save back the result into `manual.odt’.
```
$ git add doc/manual.odt
$ git commit
```


----

# ELAN
+ https://tla.mpi.nl/tools/tla-tools/elan/
Python tools:
+ Pympi, https://github.com/dopefishh/pympi
   + http://dopefishh.github.io/pympi/Elan.html
+ https://github.com/cidles/poio-api   

* ramin yaghoubzadeh python ELAN library
 

----

# [Encoding](https://en.wikipedia.org/wiki/Character_encoding)
+ https://en.wikipedia.org/wiki/Category:Natural_language_and_computing
+ https://en.wikipedia.org/wiki/Category:Character_encoding
+ Ascii : https://en.wikipedia.org/wiki/ASCII
+ https://en.wikipedia.org/wiki/Glyph

----

# [JSON](https://en.wikipedia.org/wiki/JSON)
+ http://json-ld.org/

----

# [LaTeX](https://en.wikipedia.org/wiki/LaTeX)
+ http://robjhyndman.com/hyndsight/latex/
+ Prof. Edward R. Scheinerman's resources to "[Learn LaTeX](http://www.ams.jhu.edu/~ers/learn-latex/)".
+ http://tex.stackexchange.com/questions/8374/the-key-to-understanding-the-latex-syntax
+ latex for MATH: http://en.wikibooks.org/wiki/LaTeX/Mathematics
+ LaTeX tutorial : http://www.pages.drexel.edu/~pyo22/students/latexRelated/latexTutorial.html
+ http://latex-project.org/intro.html
+ https://github.com/higham/latex-tips
+ Tables in LaTeX: http://robjhyndman.com/hyndsight/tables-in-latex/

### LaTex2PDF
+ http://robjhyndman.com/hyndsight/xelatex/
+ http://www.latex-community.org/forum/viewtopic.php?f=5&t=22560
+ https://math.berkeley.edu/~vojta/tex/pdf.html
+ http://www.mathstat.dal.ca/~selinger/pdfa/
+ http://www-rohan.sdsu.edu/~aty/bibliog/latex/LaTeXtoPDF.html
+ http://askubuntu.com/questions/166679/how-can-i-convert-a-tex-file-to-pdf-on-via-the-command-line
+ http://tex.stackexchange.com/questions/21405/how-to-create-pdf-with-command-line-using-miktex

### Automate LaTeX
+ [arara](https://github.com/cereda/arara) is a TeX automation tool based on rules and directives to help you enhance your TeX experience.
+ https://github.com/cmhughes/latexindent.pl

### Paper Writing
+ https://github.com/sympy/sympy-paper

----

# MAT
+ http://www.mathworks.com/help/pdf_doc/matlab/matfile_format.pdf

----

# Markdown
+ http://ericholscher.com/blog/2016/mar/15/dont-use-markdown-for-technical-docs/

----

# [MetaData](https://en.wikipedia.org/wiki/Metadata)
+ [Tag](https://en.wikipedia.org/wiki/Tag_(metadata))

----

# Pandoc 
+ http://pandoc.org/demos.html
+ http://pandoc.org/
+ http://writers.stackexchange.com/questions/9056/from-markdown-to-odt-and-vice-versa-a-possible-distraction-free-writing-workfl

----

# RDF 
RDF == Resource Description Framework
+ How do I create a RDF database? https://www.quora.com/How-do-I-create-a-RDF-database

----

# [XML](https://en.wikipedia.org/wiki/XML)
+ Python docs: https://docs.python.org/3/library/xml.etree.elementtree.html
+ http://www.tutorialspoint.com/python/python_xml_processing.htm
+ http://stackoverflow.com/questions/12322345/python-lxml-how-to-validate-file-using-xml-schema-file-defined-in-the-xml-file?rq=1
+ https://www2.informatik.hu-berlin.de/~xing/Lib/Docs/jaxp/docs/tutorial/sax/1_write.html

## Python with XML
+ https://docs.python.org/3/library/xml.etree.elementtree.html
+ https://www.google.de/#q=how+to+read+xml+file+in+python

----

# Standards

## MetaData
+ https://en.wikipedia.org/wiki/Category:Metadata_standards
+ https://en.wikipedia.org/wiki/Metadata_standard
+ https://en.wikipedia.org/wiki/Preservation_metadata  
+ http://pkiraly.github.io/metadata-quality-project-plan.pdf

----

# YAML
+ http://pyyaml.org/wiki/PyYAMLDocumentation#FrequentlyAskedQuestions

----
