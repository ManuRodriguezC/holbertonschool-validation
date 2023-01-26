# Prerequisites

* Shell terminal basics, using command lines:
    <div>

    * Navigating in a Unix file-system

    * Understanding how stdin/stdout redirection and piping

    * Showing and searching the content of a text files

    * Defining and using Environment Variables

    * Adding command lines to your terminal using the apt-get package manager and/or with the PATH variable

    * Writing and executing a shell script
    </div>
* Git with the command line (and also a graphical interface)
    <div>

    * Retrieving or creating a repository

    * Manipulating changes locally with Git’s 3 steps process (workspace, staging, history)

    * Distributing changes history with remotes repositories
    </div>
* Make/Makefile usage:
    <div>
    
    * Executing tasks through make targets

    * Default target and PHONY target

    * Makefile’s variables and macro syntax
    </div>
# Lifecycle

Execute the commands make file for you help:

go-build:  Build the API binary
hugo-build:  Build a web site
build:   Create  a new site
check:  Lints and check the lint of markdown
validate:  Validates dist/index.html using W3C Hbtn validator
run:     Runs the built binary and send everything to awesome.log
stop:    Terminates the execution of awesome-api
clean:  Delete all files dist
post:  Created a new post and update a title of the content
package:  It should create a file named awesome-website.zip (not committed and deleted by make clean).
lint:  Check markdown files and flag style issues.
unit-tests:  run unit tests
integration-tests:  run integration-tests
test:  Tests API uses go test
build-docker:  Create the image in docker
docker-tests:  Test the henereted docker image using container
help:  Print all commands of the makefile