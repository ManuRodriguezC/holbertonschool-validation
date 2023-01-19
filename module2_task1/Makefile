build: ## Compile the source code of the application
		go mod init github.com/ManuRodriguezC/awesome-api
		make lint && go build || exit -1

run: ## un the application in background by executing
		./awesome-api >./awesome.log 2>&1 &

stop: ## Stop the application
		kill $(shell pgrep awesome-api) 2>&1 &

clean: ## Delete the binaty awesome-api
		rm -r awesome.log 2>&1 &
		rm -r awesome-api 2>&1 &
		rm go.mod 2>&1 &
		rm go.sum 2>&1 &

test: ## Test the application
		curl http://localhost:9999
		curl http://localhost:9999/health

lint: ## Implemented and should fail when the linter catches and error
		golangci-lint run

help: ## Print the differents commands
		cat Makefile | grep '##' | tr -d '##' | head -n -1
