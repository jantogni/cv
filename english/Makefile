# Makefile
TEXFILES = $(wildcard *.tex)
PDFFILES = $(TEXFILES:.tex=.pdf)

all: pdflatex clean

pdf: $(PDFFILES)

pdflatex: $(TEXFILES)
	@pdflatex $(TEXFILES:.tex=)
	#@TEXMFOUTPUT=`pwd` bibtex `pwd`/$(TEXFILES:.tex=)
	#@pdflatex $(TEXFILES:.tex=)
	@pdflatex $(TEXFILES:.tex=)
	@if [ -d publish ];then mv *.pdf publish; else mkdir publish; mv *.pdf publish/;fi

clean:
	@rm -f *.log *.bak *.aux *.bbl *.blg *.idx *.toc *.out *~

distclean: clean
	@rm -rf publish

x:
	@open publish/$(PDFFILES) &> /dev/null &
