DESTDIR=public
OPTIMIZE = find $(DESTDIR) -not -path "*/static/*" \( -name '*.png' -o -name '*.jpg' -o -name '*.jpeg' \) -print0 | xargs -0 -P8 -n2 mogrify -strip -thumbnail '1000>'

clean:
	@echo "? Cleaning old build"
	cd $(DESTDIR) && rm -rf *

devserve:
	@echo "? Running local DEV server"
	hugo server -D

buildpdf:
	@echo "? CV to pdf"
	libreoffice --headless --convert-to pdf ../assets/CV_DiegoSoutoCatoira.odt
	cp ../assets/CV_DiegoSoutoCatoira.pdf ./static/media/

build: 
	@echo "? Generating site"
	hugo --gc --minify -d $(DESTDIR)

optimize:
	@echo "? Optimizing images"
	$(OPTIMIZE)

