---
layout: page
title: "DOCKER"
permalink: /use/docker.html
--- 

## Create the docker container
(Requires you to have Docker installed)

1. Git clone open-publisher repo
  - `https://github.com/chrisanthropic/Open-Publisher.git`

2. Build the container
  - `docker build -t open-publisher .`

## Test run with our example book
Create example book (This will move the contents of 'skel' to 'Source'):

`docker run -v $PWD/input:/Open-Publisher/Source -it open-publisher rake skel`

## Bind example book
This will create two new directories (input & output) which are mounted inside the Docker container. input maps to Source and output maps to Books. Running this command will create all versions of the example book which you can see in output.

`docker run -v $PWD/input:/Open-Publisher/Source -v $PWD/output:/Open-Publisher/Books -it open-publisher rake all[all]`

You can replace `all[all]` with any of the commands on the [Rake](rake.html) page.
