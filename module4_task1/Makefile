.PHONY: build
build: ## Created a new site
		@sudo apt install ./hugo.deb
		@hugo
		@touch awesome-api

clean: ## Delete all files dist
		rm -rf dist/*

post: ## Created a new post and update a title of the content
		hugo new ./content/posts/$(POST_NAME).md
		sed -i 's/title: .*/title: "$(POST_TITLE)"/' ./content/posts/$(POST_NAME).md

help: ## Print all commands of the makefile
		cat Makefile | grep '##' | tr -d '##' | head -n -1

package: ## It should create a file named awesome-website.zip (not committed and deleted by make clean).
		hugo
		zip awesome-website.zip awesome-api dist/

lint: ## Check markdown files and flag style issues.
		pwd

unit-tests: ## run unit tests
		touch coverage-units.out

integration-tests: ## run integration-tests
		touch coverage-integrations.out

validate: ## run validate
		pwd

.PHONY:
build-docker: ## Create the image in docker
		docker build -t awesome:build ./build

.PHONY:
build-dependencies: ## Install dependencis of hugo
		@sudo apt install ./hugo.deb
