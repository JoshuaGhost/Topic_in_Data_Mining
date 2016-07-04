TEX = pdflatex -shell-escape -interaction=nonstopmode -file-line-error
BIB = bibtex
FILE = report

.PHONY: all view

all: $(FILE).pdf

$(FILE).pdf: $(FILE).tex $(FILE).bbl $(FILE).blg
	$(TEX) $(FILE).tex

$(FILE).bbl $(FILE).blg: $(FILE).bib $(FILE).aux
	$(TEX) $(FILE).tex
	$(BIB) $(FILE)

$(FILE).aux: $(FILE).tex
	$(TEX) $(FILE).tex

$(FILE).bib: $(FILE).tex
	$(TEX) $(FILE).tex

clean: 
	rm $(FILE).aux $(FILE).bbl $(FILE).blg $(FILE).log $(FILE).pdf
