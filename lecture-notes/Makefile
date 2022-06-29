# Generate PDFs from the Markdown source files
#
# In order to use this makefile, you need some tools:
# - GNU make
# - Pandoc

# original en https://gist.github.com/bertvv/e77e3a5d24d8c2a9bcc4

# Directory containing source (Markdown) files
source := src

# Directory containing pdf files
output := print

# All markdown files in src/ are considered sources
sources := $(wildcard $(source)/*.md)

# Convert the list of source files (Markdown files in directory src/)
# into a list of output files (PDFs in directory print/).
objects := $(patsubst %.md,%.pdf,$(subst $(source),$(output),$(sources)))

all: $(objects)

# Recipe for converting a Markdown file into PDF using Pandoc
$(output)/%.pdf: $(source)/%.md
	pandoc \
		-f markdown  $< \
		--template=config/template.tex \
		--metadata-file=metadata.yaml \
		--include-in-header config/preamble.tex \
		--highlight-style config/pygments.theme \
		--pdf-engine=xelatex \
		-o $@

# '$<' represents the source file on which make is currently operating 
# (makefile)
# '$@' represents the target file on which make is currently operating 
# (makefile)

.PHONY : clean

clean:
	rm -f $(output)/*.pdf
