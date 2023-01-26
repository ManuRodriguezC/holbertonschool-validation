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

* <b>build</b>: Generate the website from the markdown and configuration files in the directory dist/.

* <b>clean</b>: Cleanup the content of the directory dist/

* <b>post</b>: Create a new blog post whose filename and title come from the environment variables POST_TITLE and POST_NAME.

* <b>help</b>: Ideally the usage should be the comment associated with each target