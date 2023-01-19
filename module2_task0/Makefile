build: ## Compile the source code of the application
		go mod init github.com/ManuRodriguezC/awesome-api
		go build

run: ## un the application in background by executing
		./awesome-api >./awesome.log 2>&1 &

stop: ## Stop the application
		kill $(shell pgrep awesome-api)

clean: ## Delete the binaty awesome-api
		make stop
		rm -r awesome-api.log
		rmdir awesome-api

test: ## Test the application
		curl http://localhost:9999
		curl http://localhost:9999/health

help: ## Print the differents commands
		cat Makefile | grep '##' | tr -d '##' | head -n -1
