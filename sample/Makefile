all: default.pdf antibes.beaver.pdf ponde.pdf ponde2.pdf Execushares.pdf pondering.pdf pondering.169.pdf

%.169.pdf: ../themes/%.tex
	pandoc -s -t beamer -V aspectratio=169 --template $^ -o tmp.tex sample.md
	platex -shell-escape tmp.tex
	platex -shell-escape tmp.tex
	dvipdfmx tmp
	mv tmp.pdf $@

%.pdf: ../themes/%.tex
	pandoc -s -t beamer --template $^ -o tmp.tex sample.md
	platex -shell-escape tmp.tex
	platex -shell-escape tmp.tex
	dvipdfmx tmp
	mv tmp.pdf $@

.PHONY: clean

clean:
	rm -f tmp.*
