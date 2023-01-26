clean: ## Delete all files dist and API
		-make stop
		-rm -rf dist
		-rm -rf awesome.log 2>&1 &
		-rm -rf awesome-api 2>&1 &
		-rm coverage-integrations.out
		-rm coverage-units.out

build: ## Created web and API
		make go-build
		make hugo-build

hugo-build : check ## Check an create the web site
		hugo

go-build: ## 
		go mod init github.com/ManuRodriguezC/awesome-api
		go build

post: ## Created a new post and update a title of the content
		hugo new ./content/posts/$(POST_NAME).md
		sed -i 's/title: .*/title: "$(POST_TITLE)"/' ./content/posts/$(POST_NAME).md

check: ## Check web static
		markdownlint ./content/posts/*.md
		markdown-link-check ./content/posts/*.md

validate: ## Should validate the file ./dist/index.html
		make build
		./w3c_validator.py ./dist/index.html || true

run: ## Run the application in background by executing
		./awesome-api >./awesome.log 2>&1 &

stop: ## Stop the application
		kill $(shell pgrep awesome-api) 2>&1 &

lint: ## Lint markdown
		golangci-lint run

unit-tests: ## Test using in go tests
		go test -v -short -coverprofile=coverage-units.out

integration-tests: ## Test using integration in go tests
		go test -v -coverprofile=coverage-integrations.out

test: ## Run unit test and integration test
		-make build
		make unit-tests
		make integration-tests

help: ## Print all commands of the makefile
	cat Makefile | grep '##' | tr -d '##' | head -n -1
	