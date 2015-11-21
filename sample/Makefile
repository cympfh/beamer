all: default.pdf antibes.beaver.pdf ponde.pdf Execushares.pdf

Execushares.pdf: sample.md
	pandoc -s -t beamer --template ../themes/Execushares.tex -o tmp.tex sample.md
	platex -shell-escape tmp.tex
	platex -shell-escape tmp.tex
	dvipdfmx tmp
	mv tmp.pdf $@

ponde.pdf: sample.md
	pandoc -s -t beamer --template ../themes/ponde.tex -o tmp.tex sample.md
	platex -shell-escape tmp.tex
	platex -shell-escape tmp.tex
	dvipdfmx tmp
	mv tmp.pdf $@

antibes.beaver.pdf: sample.md
	pandoc -s -t beamer -V theme:Antibes -V colortheme:beaver -o tmp.tex sample.md
	platex tmp.tex
	dvipdfmx tmp
	mv tmp.pdf $@

default.pdf: sample.md
	pandoc -s -t beamer -o /tmp/tmp.tex sample.md
	platex /tmp/tmp
	dvipdfmx tmp
	mv tmp.pdf $@

.PHONY: clean

clean:
	rm tmp.*
