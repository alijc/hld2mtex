# makefile for testing the fonts

all:	test.ps


# Produce a dvi file from the tex file
%.dvi:	%.tex 
	tex $<

# Produce a postscript score from the dvi file
%.ps:	%.dvi
	dvips $< -o $@

# Produce a gf file from an mf file
%.2602gf:	%.mf
		mf $<

# Produce a dvi file from a gf file
%.dvi:	%.2602gf
	gftodvi $<

clean:
	-rm --force *.ps *.dvi *.*gf *.*pk *.tfm *.log *~
