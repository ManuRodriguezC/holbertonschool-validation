# Learning Objectives

This project aims at showing use cases where a DevOps mindset is bringing value to a software project by automating it, which decreases the amount of manual work and increases the development speed. It focuses on why automation is useful and helps speeding a development lifecycle.

After this project, you should be able to:

Understand the value of automating tedious tasks

Define a development lifecycle

Automate shell-like tasks with Make, and/or shell script

Be aware of tools dependencies and the value of reproducing environment

Build static HTML website from Markdown code using Go-Hugo

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