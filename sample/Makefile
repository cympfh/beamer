all: default.pdf antibes.beaver.pdf ponde.pdf ponde2.pdf Execushares.pdf ponde3.pdf

%.pdf: ../themes/%.tex
	pandoc -s -t beamer --template $^ -o tmp.tex sample.md
	platex -shell-escape tmp.tex
	platex -shell-escape tmp.tex
	dvipdfmx tmp
	mv tmp.pdf $@

antibes.beaver.pdf: sample.md
	pandoc -s -t beamer -V theme:Antibes -V colortheme:beaver -o tmp.tex sample.md
	platex -shell-escape tmp.tex
	platex -shell-escape tmp.tex
	dvipdfmx tmp
	mv tmp.pdf $@

default.pdf: sample.md
	pandoc -s -t beamer -o tmp.tex sample.md
	platex -shell-escape tmp.tex
	platex -shell-escape tmp.tex
	dvipdfmx tmp
	mv tmp.pdf $@

.PHONY: clean

clean:
	rm tmp.*
