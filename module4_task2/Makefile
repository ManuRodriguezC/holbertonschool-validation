.PHONY: build

go-build: ## Build the API binary
		docker run --rm --volume=$(shell pwd):/app --workdir=/app awesome:build /bin/bash -c "go mod init github.com/ManuRodriguezC/awesome-api && go get github.com/gorilla/mux && go build"

hugo-build: ## Build a web site
		docker run --rm --volume=$(shell pwd):/app --workdir=/app awesome:build hugo

build:  ## Create  a new site
		-make go-build
		make hugo-build

check: ## Lints and check the lint of markdown
		docker run --rm --volume=$(shell pwd):/app --workdir=/app awesome:build markdownlint ./content/posts/*.md
		docker run --rm --volume=$(shell pwd):/app --workdir=/app awesome:build markdown-link-check ./content/posts/*.md

validate: ## Validates dist/index.html using W3C Hbtn validator
		-make build
		-git clone https://github.com/holbertonschool/W3C-Validator.git
		-./W3C-Validator/w3c_validator.py ./dist/index.html
		-rm -rf ./W3C-Validator

run:	## Runs the built binary and send everything to awesome.log
		./awesome-api >./awesome.log 2>&1 &

stop:	## Terminates the execution of awesome-api
		kill $(shell pgrep awesome-api)

clean: ## Delete all files dist
		rm -rf dist/*

post: ## Created a new post and update a title of the content
		hugo new ./content/posts/$(POST_NAME).md
		sed -i 's/title: .*/title: "$(POST_TITLE)"/' ./content/posts/$(POST_NAME).md

package: ## It should create a file named awesome-website.zip (not committed and deleted by make clean).
		-make build
		zip awesome-website.zip awesome-api dist/

lint: ## Check markdown files and flag style issues.
		pwd

unit-tests: ## run unit tests
		docker run --rm --volume=$(shell pwd):/app --workdir=/app awesome:build go test -v -short -coverprofile=coverage-units.out

integration-tests: ## run integration-tests
		docker run --rm --volume=$(shell pwd):/app --workdir=/app awesome:build go test -v -coverprofile=coverage-integrations.out

test: ## Tests API uses go test
		-make build
		make unit-tests
		make integration-tests

build-docker: ## Create the image in docker
		docker build -t awesome:build ./build

docker-tests: ## Test the henereted docker image using container
		-make build-docker
		container-structure-test test --image awesome:build --config build/cst.yml

help: ## Print all commands of the makefile
		cat Makefile | grep '##' | tr -d '##' | head -n -1