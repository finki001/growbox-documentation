# Overview

This is the collected knowledge for the Lodge 100 3 area grow setup

## Commands

* `docker compose up -d` - Serve the project.
* `docker run --rm -it -v ${PWD}:/docs squidfunk/mkdocs-material build` - Build the docs.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.
