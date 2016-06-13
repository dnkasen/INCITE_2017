CV_SOURCES := $(wildcard *.tex)

ALL: $(CV_SOURCES:.tex=.pdf)


%.pdf: %.tex
	pdflatex $<	
	pdflatex $<
	pdflatex $<


print-%: ; @echo $* is $($*)

clean: 
	$(RM) *.aux *.log *.blg *.out

realclean: clean
	$(RM) *.pdf

