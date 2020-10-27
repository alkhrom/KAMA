docname = ../80102-01_31
MAIN = main

all: clean $(docname).pdf

pdf: $(docname).pdf

$(docname).pdf: $(MAIN).tex
	# make bibl
	#pdflatex $(MAIN).tex
	#bibtex $(MAIN).aux
	
	# make other
	pdflatex $(MAIN).tex
	latex_count=5 ; \
	while egrep -s 'Rerun (LaTeX|to get cross-references right)' $(MAIN).log && [ $$latex_count -gt 0 ] ;\
	    do \
	      echo "Rerunning latex...." ;\
	      pdflatex $(MAIN).tex ;\
	      latex_count=`expr $$latex_count - 1` ;\
	    done
	 mv $(MAIN).pdf $(docname).pdf


clean:
	rm -f *.ps *.dvi *.aux *.toc *.idx *.ind *.ilg *.log *.out $(docname).pdf $(MAIN).pdf
