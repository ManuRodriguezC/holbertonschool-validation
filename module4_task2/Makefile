build:  ## Create  a new site
		hugo

clean: ## Delete all files dist
		rm -rf dist/*

post: ## Created a new post and update a title of the content
		hugo new ./content/posts/$(POST_NAME).md
		sed -i 's/title: .*/title: "$(POST_TITLE)"/' ./content/posts/$(POST_NAME).md

package: ## It should create a file named awesome-website.zip (not committed and deleted by make clean).
		hugo
		zip awesome-website.zip awesome-api dist/

lint: ## Check markdown files and flag style issues.
		docker run --rm -i hadolint/hadolint < duild/Dockerfile
		docker run --rm -i ghcr.io/hadolint/hadolint < build/Dockerfile

unit-tests: ## run unit tests
		touch coverage-units.out

integration-tests: ## run integration-tests
		touch coverage-integrations.out

validate: ## run validate
		pwd

build-docker: ## Create the image in docker
		docker build -t awesome:build -f build/Dockerfile .

docker-tests: ## Container-structure-test
		container-structure-test test --image awesome:build --config config.yaml

help: ## Print all commands of the makefile
		cat Makefile | grep '##' | tr -d '##' | head -n -1