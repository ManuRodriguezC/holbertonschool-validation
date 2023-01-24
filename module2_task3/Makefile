build: ## Compile the source code of the application
		go mod init github.com/ManuRodriguezC/awesome-api
		go build

run: ## un the application in background by executing
		./awesome-api >./awesome.log 2>&1 &

stop: ## Stop the application
		kill $(shell pgrep awesome-api) 2>&1 &

clean: ## Delete the binaty awesome-api
		-rm -r awesome.log 2>&1 &
		-rm -r awesome-api 2>&1 &
		-rm go.mod 2>&1 &
		-rm go.sum 2>&1 &
		-rm coverage-integrations.out
		-rm coverage-units.out

test: ## Test the application
		make unit-tests &
		make integration-tests

lint: ## Implemented and should fail when the linter catches and error
		golangci-lint run

unit-tests: ## Test using in go tests
		go test -v -short -coverprofile=coverage-units.out || echo $1

integration-tests: ## Tests of the integrations tests
		go test -v -coverprofile=coverage-integrations.out || echo $1

help: ## Print the differents commands
		cat Makefile | grep '##' | tr -d '##' | head -n -1
