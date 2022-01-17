
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


So basically the next steps should be pull the image and deploy the image as docker container based on the environment we use (Docker Swarm, Kubernetes, Cloud Native). 


NOTE:
Github actions workflow required some secrets and intial tags on the repo to pass that why its failing right now. I just added the workflow skelton for understanding.

Issues Encountered:

Multiple .py scripts in multiple folders to need to add into docker image, so added them as a folder under /app
Few Dependencies are not upto date, so its having issues during the env setup ( this can be resolved by looking at the new packages or upgrades by going through each one of those in each build failure)
Next one is Codecov is not properly enabled for code coverage reports
