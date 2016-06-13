SOURCES := summary.tex \
           narrative.tex \
           milestones.tex \
           personnel.tex \
           publications.tex \
           management.tex \


PDFs := $(SOURCES:.tex=.pdf)
ALL: $(PDFs) merged.pdf


narrative.pdf: narrative.tex refs.bib newcommands.tex
	pdflatex $<
	bibtex narrative
	pdflatex $<
	pdflatex $<

%.pdf: %.tex
	pdflatex $<	
	pdflatex $<
	pdflatex $<

merged.pdf: $(PDFs)
	gs -dNOPAUSE -sDEVICE=pdfwrite -sOUTPUTFILE=merged.pdf -dBATCH $(PDFs) $(wildcard CVs/*.pdf)


print-%: ; @echo $* is $($*)

clean: 
	$(RM) *.aux *.log *.blg *.bbl *.out

realclean: clean
	$(RM) $(SOURCES:.tex=.pdf)
	$(RM) *-eps-converted-to.pdf


