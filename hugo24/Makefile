DESTDIR=public
OPTIMIZE = find $(DESTDIR) -not -path "*/static/*" \( -name '*.png' -o -name '*.jpg' -o -name '*.jpeg' \) -print0 | xargs -0 -P8 -n2 mogrify -strip -thumbnail '1000>'
DOCKER_IMAGE ?= ponte124/cvweb
DOCKER_TAG ?= 25.12.27

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

dockerbuild:
	@echo "? Building and pushing multi-arch image (amd64, arm64)"
	docker buildx build --platform linux/amd64,linux/arm64 -t "$(DOCKER_IMAGE):$(DOCKER_TAG)" --push .

optimize:
	@echo "? Optimizing images"
	$(OPTIMIZE)

