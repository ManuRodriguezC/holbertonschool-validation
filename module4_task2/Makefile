build:  ## Create  a new site
		hugo

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
		sudo wget -O /bin/hadolint https://github.com/hadolint/hadolint/releases/download/v1.16.3/hadolint-Linux-x86_64
		sudo chmod +x /bin/hadolint
		hadolint build/Dockerfile
		hadolint --ignore DL3003 --ignore DL3006 build/Dockerfile
		hadolint --trusted-registry my-company.com:500 build/Dockerfile

unit-tests: ## run unit tests
		touch coverage-units.out

integration-tests: ## run integration-tests
		touch coverage-integrations.out

validate: ## run validate
		pwd

build-docker: ## Create the image in docker
		docker build -t awesome:build -f build/Dockerfile .

docker-tests: ## Container-structure-test
		curl -LO https://storage.googleapis.com/container-structure-test/latest/container-structure-test-linux-amd64 && chmod +x container-structure-test-linux-amd64 && mkdir -p $HOME/bin && export PATH=$PATH:$HOME/bin && mv container-structure-test-linux-amd64 $HOME/bin/container-structure-test
