MKFILE_DIR := $(dir $(abspath $(lastword $(MAKEFILE_LIST))))
DIR_NAME := $(notdir $(CURDIR))

PDFLATEX_FLAGS += -interaction=nonstopmode

all: $(DIR_NAME).pdf

# TLIN:
#	Just rebuild the whole thing for now... (lazy)
#	TODO: Can use latexmk to optimize later
$(DIR_NAME).pdf: $(DIR_NAME).tex
	rm -f *.aux *.out *.log *.pdf
# Requires two passes to get page #'s right
	pdflatex $(PDFLATEX_FLAGS) $(DIR_NAME).tex
	pdflatex $(PDFLATEX_FLAGS) $(DIR_NAME).tex

clean:
	rm -f *.aux *.out *.log *.pdf

