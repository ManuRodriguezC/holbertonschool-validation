build: ## Created a new site
	hugo

clean: ## Delete all files dist
	rm -r dist

post: ## Created a new post and update a title of the content
	hugo new ./content/posts/$(POST_NAME).md
	sed -i 's/title: .*/title: "$(POST_TITLE)"/' ./content/posts/$(POST_NAME).md

check: ## Check web static
	markdownlint ./content/posts/*.md
	markdown-lint-check ./content/posts/*.md

validate: ## Should validate the file ./dist/index.html
	make build
	./w3c_validator.py ./dist/index.html

help: ## Print all commands of the makefile
	cat Makefile | grep '##' | tr -d '##' | head -n -1