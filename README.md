# Autogit: Simple Tutorial

This repository shows how you can use Combell Autogit to deploy a project.

## My Combell

Go to [https://my.combell.com/](https://my.combell.com/) and activate "Autogit".

Copy the displayed "Git repository", you'll need it later.

## Local repository

Open the terminal on your local computer and create a local git repository (by cloning the Combell repository):

    cd ~/Projects/
    git clone domainbe@ssh.domain.be:auto.git domain.be
    cd domain.be

## Repository structure

We need a "www" folder and a ".autogit.yml" file in the repository to be able to deploy:

    scp domainbe@ssh.domain.be:autogit.yml.example .autogit.yml
    git add .autogit.yml
    git commit -m "Add the default .autogit.yml template"
    mkdir www
    echo "<?php phpinfo();" > www/index.php
    git add www/index.php
    git commit -m "Add an index file to the required www folder (printing phpinfo)"

## Deploying

Deploying is as simple as pushing your local repository to the Combell remote:

    git push origin master
