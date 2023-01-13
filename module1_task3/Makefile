build: ## Created a new site
	hugo -s . -d dist/

clean: ## Delete all files dist
	rm -rf dist/*

post: ## Created a new post and update a title of the content
	hugo new ./content/posts/$(POST_NAME).md
	sed -i 's/title: .*/title: "$(POST_TITLE)"/' ./content/posts/$(POST_NAME).md

help: ## Print all commands of the makefile
	cat Makefile | grep '##' | tr -d '##' | head -n -1