build: ## Created a new site
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

lint: ## should be updated to lint the files README.md and DEPLOY.md with markdownlint command line
	markdownlint "*.md"

unit-tests: ## run unit tests
	make POST_TITLE='TEST POST_NAME='this-is-a-test' post
	make package
	make clean

integration-tests: ## run integration-tests
	pwd

validate: ## run validate
	pwd
