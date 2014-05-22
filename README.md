latexmk-config
==============

This is a configuration for latexmk, a  tool to build latex documents.
It contains custom dependencies for automatic conversion of many types of graphics, so you only have to add the graphic sources to your document. The conversion to eps (for latex) or pdf (for pdflatex) it done automatically.
Furthermore a handy wrapper makefile is provided to start latexmk.
(pdf)latex is called with the synctex option, so backward (or inverse) search will work.

##Custom dependencies
These are the files that can be converted automatically at the moment. The required tools are given.

### Adobe Illustrator (*.ai)
Requirements: pdf2ps

### Asymtote (*.asy)
Requirements: asymtote

### Bitmaps (*.jpg, *.png, *.gif)
Requirements: convert (part of imagemagick)

### Cirkuit
*Warning*: Not yet working
Requirements: cirkuit and dpic

### Dia (*.dia)
Requirements: dia

### Glossaries
Requirements: makeglossaries (part of LaTeX package glossaries)

###Gnuplot (*.gp)
Conversion to eps using the postscript terminal. The terminal and the output filename are set automatically, so you don't need to set it in your *.gp file. Dependencies from external data files are handled if they are named *.dat or *.csv.
Requirements: gnuplot


### SVG (*.svg)
Requirements: inkscape

### XFig (*.fig)
Requirements: fig2dev


##Makefile Targets
Target | Action|
------ | -------
make pdf | Build documents as pdf, all dependencies are generated, eps files are converted to pdf by newer pdflatex versions|
make ps | Build documents as postscript, all dependencies are generated |
make dvi | Build documents as dvi, all dependencies are generated |
make clean | Removes all files generated by latex runs (including bibtex), files generated from custom dependencies, files named *-eps-converted-to.pdf generated by eps to pdf-conversion of pdflatex and internal latexmk files |
make view | Build pdf and show it with evince |







