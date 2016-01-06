BUILDDIR = build
OUTDIR = pdf
TEXDIR = summary
TEXFILE = summary.tex
PDFFILE = $(addsuffix .pdf,$(basename $(TEXFILE)))
CHAPTERS = $(shell find $(TEXDIR)/chapters -name "*.tex")
IMAGES = $(shell find $(TEXDIR)/img -name "*.png")

$(TEXDIR)/$(OUTDIR)/$(PDFFILE): $(TEXDIR)/$(TEXFILE) $(CHAPTERS) $(IMAGES)
	cd $(dir $<) ; mkdir -p $(BUILDDIR)
	cd $(dir $<) ; pdflatex -halt-on-error -output-directory=$(BUILDDIR) $(notdir $<)
	cd $(dir $<) ; pdflatex -halt-on-error -output-directory=$(BUILDDIR) $(notdir $<)
	cd $(dir $<) ; mkdir -p $(OUTDIR)
	cd $(dir $<) ; mv $(BUILDDIR)/$(PDFFILE) $(OUTDIR)

.PHONY: clean
clean:
	rm -rf $(TEXDIR)/$(BUILDDIR)
	rm -rf $(TEXDIR)/$(OUTDIR)
