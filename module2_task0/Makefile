build: ## Compile the source code of the application
		go build

run: ## un the application in background by executing
		chmod u+x awesome-api
		./awesome-api
		./awesome-api >./awesome.log 2>&1 &

stop: ## Stop the application
		kill XXXXX or XXXXX
		kill "$(pgrep awesome-api)"

clean: ## Delete the binaty awesome-api
		rm awesome-api.log
		rmdir awesome-api

test: ##
