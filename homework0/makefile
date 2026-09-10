HWID=0
TEXFILE = hw$(HWID).tex
PDF = hw$(HWID).pdf
DIST_DIR = dist

-include ../.env
STUDENT_ID ?= unknown
NAME ?= unknown

all: $(PDF)

$(PDF): $(TEXFILE)
	rm -f $(PDF)
	xelatex -shell-escape $(TEXFILE)
	xelatex -shell-escape $(TEXFILE)

archive: 
	mkdir -p $(DIST_DIR)
	cp $(PDF) $(DIST_DIR)/$(STUDENT_ID)_$(NAME)_HW$(HWID).pdf

clean:
	rm -f ./*.aux ./*.log ./*.bbl ./*.blg ./*.toc ./*.out ./*.lof ./*.lot ./*fls ./*.fdb_latexmk ./*.synctex.gz
	rm -rf _minted

distclean: clean
	rm -f $(PDF)
	rm -rf $(DIST_DIR)

.PHONY: all clean