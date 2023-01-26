build: ## Compile the source code of the application
		make lint
		go build

run: ## un the application in background by executing
		./awesome-api >./awesome.log 2>&1 &

stop: ## Stop the application
		kill $(shell pgrep awesome-api) 2>&1 &

clean: ## Delete the binaty awesome-api
		-make stop
		-rm -r awesome.log 2>&1 &
		-rm -r awesome-api 2>&1 &
		-rm coverage-integrations.out
		-rm coverage-units.out

lint: ## Implemented and should fail when the linter catches and error
		golangci-lint run

unit-tests: ## Test using in go tests
		go test -v -short -coverprofile=coverage-units.out

integration-tests: ## Test using integration in go tests
		go test -v -coverprofile=coverage-integrations.out

test: ## Run unit test and integration test
		make unit-tests & make integration-tests

help: ## Print the differents commands
		cat Makefile | grep '##' | tr -d '##' | head -n -1
