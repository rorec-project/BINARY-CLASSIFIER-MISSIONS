PANDOC ?= pandoc
CHROMIUM ?= chromium

COMMON = --citeproc --standalone --resource-path=.:../../data/processed/figures

.PHONY: all html pdf clean

all: html pdf

html:
	$(PANDOC) paper.md $(COMMON) --css=paper.css -o paper.html

pdf: html
	$(CHROMIUM) --headless --no-sandbox --disable-gpu --no-pdf-header-footer --print-to-pdf=paper.pdf file://$(CURDIR)/paper.html

clean:
	rm -f paper.html paper.pdf
