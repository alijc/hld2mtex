# makefile for creating scores (postscript and pdf) and from hld files

hldfiles  = $(wildcard *.hld)
srcfiles  = $(hldfiles) Makefile 
texfiles  = $(patsubst %.hld,%.tex,  $(wildcard *.hld))
dvifiles  = $(patsubst %.hld,%.dvi,  $(wildcard *.hld))
psfiles   = $(patsubst %.hld,%.ps,   $(wildcard *.hld))
pdffiles  = $(patsubst %.hld,%.pdf,  $(wildcard *.hld))
pngfiles  = $(patsubst %.hld,%1.png, $(wildcard *.hld))
giffiles  = $(patsubst %.hld,%1.gif, $(wildcard *.hld))

##all:	$(psfiles) $(pdffiles) $(pngfiles) $(giffiles)
all:	$(psfiles) $(pdffiles) 

# Produce a tex file from the hld file
%.tex:	%.hld 
	hld2mtex $<
	chmod 644 $@

# Produce a dvi file from the tex file
%.dvi:	%.tex 
	tex $<
	chmod 644 $@

# Produce a postscript score from the dvi file
%.ps:	%.dvi
	dvips $< -o $@
	chmod 644 $@

# Produce a pdf score from the postscript score 
%.pdf:	%.ps
	ps2pdf $< $@
	chmod 644 $@

#%1.png:	%.ps
#	gs -q -dNOPAUSE -dBATCH -sDEVICE=pnggray -sOutputFile=$*%d.png $<
#	chmod 644 $@

# Convert each of the .png files to a gif file
#%1.gif:	%1.png
#	./makegifs  $(wildcard $**png)
#	chmod 644 $@


# targets not included in 'all'
#backup: $(srcfiles)
#	rsync -e ssh --archive --update --compress --verbose $(srcfiles) \
#		zaphod.axian.com:public_html_bcs/music/adam/motets/

clean:
	-rm --force *.ps *.pdf *~

cleanup:
	-rm --force *log *mx1
