# assignment02
Assignment 2

# Explanation

### Initialization
I have used a template "Hello World" Spring Boot Application as a project, since assignment is about deployment and automation.
I've initialized spring boot app at https://start.spring.io


### pom.xml & circleci/config.yml
I have configured ```pom.xml``` to add dependencies ```jib-maven-plugin```.

Then I've added ```circleci``` directory containing ```config.yml``` file thorugh CircleCi web-app, since I was having issues with adding it manually.

### Docker Access Variables & Docker Image
I have specified ```DOCKER_PASS``` & ```DOCKER_USER``` variables in CircleCi project settings to make it more dynamic as well as secure, and I pass them with maven command.
I have also specified Docker image directory with ```-Dimage```. 
All of it is done with Maven Google Jib plugin.


First couple of builds failed because I had to make a pull request and merge new `.circleci/config.yml` directory.


# End
