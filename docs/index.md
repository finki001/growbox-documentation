# Overview
This is the collected knowledge for the Lodge 100 3 area grow setup

## Commands

* `docker compose up -d` - Serve the project.
* `docker run --rm -it -v ${PWD}:/docs squidfunk/mkdocs-material build` - Build the docs.
* `docker run --rm -it -v ~/.ssh:/root/.ssh:ro -v ~/.ssh/config.docker:/root/.ssh/config:ro -v ${PWD}:/docs squidfunk/mkdocs-material gh-deploy` - deploy docs to github pages
## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.

![420blazeit](img/420blazeit.jpeg)