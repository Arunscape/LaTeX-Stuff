# Makefile

.PHONY: all

all: report.pdf

%.pdf: %.tex 
		tectonic --reruns 0 $<
		# Run biber if we find a .bcf file in the output
		if [ -f $(notdir $(<:.tex=.bcf)) ]; then \
				biber $(notdir $(<:.tex=)); \
		fi
		tectonic --reruns 0 $<
		rm $(basename $<).bbl $(basename $<).bcf $(basename $<).blg