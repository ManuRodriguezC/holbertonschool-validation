clean: ## Delete dist file
		rm -r dist

build: ## Create a new web site
		hugo

post: ## Create a new post whose filename and title
		hugo new ./content/posts/$(POST_NAME).md
		sed -i 's/title: .*/title: "$(POST_TITLE)"/' ./content/posts/$(POST_NAME).md