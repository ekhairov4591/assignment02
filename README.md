# assignment02
Assignment 2

# Explanation

I have used a template "Hello World" Spring Boot Application as a project since assignment is about deployment and automation.
I've initialized spring boot app at https://start.spring.io

I have configured pom.xml to add dependencies as following `jib-maven-plugin'
Then I've added `.circleci/config.yml` file thorugh CircleCi web-app in since I was having issues with adding it manually.

      
I have specified DOCKER_PASS & DOCKER_USER variables in CircleCi project settings to make it more dynamic and I pass them with maven command.
I have also specified Docker image directory with -Dimage. 
All of it is done with Maven Google Jib plugin.
