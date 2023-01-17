filename := 2023-rti-curriculum-spec
md := $(filename).md
docx := $(filename).docx
html := $(filename).html
pdf := $(filename).pdf


.DEFAULT_GOAL := all

.PHONY: all
all: $(docx) $(html) $(pdf)

pandoc_markdown_extensions := +fenced_divs+header_attributes
pandoc_convert = pandoc \
	--number-sections \
	--standalone \
	--table-of-contents \
	--toc-depth 2 \
	--from markdown$(pandoc_markdown_extensions) \
	$< -o $@

%.docx: %.md
	$(pandoc_convert)

%.html: %.md
	$(pandoc_convert)

%.pdf: %.md
	$(pandoc_convert)

.PHONY: format
format:
	prettier -w $(md)

.PHONY: clean
clean:
	rm -f *.docx *.html *.pdf
