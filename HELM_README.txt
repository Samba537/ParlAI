
CI Process

Using the Github actions for CI process. Here is the workflow file .github/workflows/main.yml. 
Basically this workflow include the following steps:
    --> Setup the trigger when to build the branch (PR, Every new commit, All branches)
    --> Spin the ubuntu container to run as a github actions agent where build need to be perform
    --> Semver for the bump the version
    --> Setup the Python Env
    --> Run the Pytests
    --> Install and setup the docker
    --> Run the docker build by using the Dockerfile.Helm
    --> Push the docker to respective DTR by using the Github actions module
    --> Tag the release back to github if its master branch


Dockerise the Appp

Using the python3.9 image as base image and Add the python scripts and required files under Home directory and modified the permissions to access the required scripts.
Here is the dockerfile: Dockerfile.Helm


