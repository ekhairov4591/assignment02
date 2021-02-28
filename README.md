# assignment02
Assignment 2

#Explanation

I have used a template "Hello World" Spring Boot Application as a project since assignment is about deployment and automation.

I have configured pom.xml to add dependencies as following:
`
<plugin>
				<groupId>com.google.cloud.tools</groupId>
				<artifactId>jib-maven-plugin</artifactId>
				<version>2.7.1</version>
				<configuration>
					<from>
						<image>openjdk:11-jdk-slim</image>
					</from>
					
					<container>
						<ports>
							<port>8080</port>
						</ports>
					</container>
				</configuration>
			</plugin>
			`
      
      
Then I've added `.circleci/config.yml` file thorugh CircleCi web-app in since I was having issues with adding it manually.

`config.yml` is as following:
`
version: 2.1

jobs:
  build:
    docker:
      - image: circleci/openjdk:11.0.1-jdk

    steps:
      - checkout # git pull

      # package into a jar
      - run: mvn clean package

      # build and push docker image to docker hub
      - run: mvn clean compile jib:build -Djib.to.auth.username=$DOCKER_USER -Djib.to.auth.password=$DOCKER_PASS -Dimage=ekhairov4591/assignment02:$CIRCLE_BUILD_NUM
      `
      
      I have specified DOCKER_PASS & DOCKER_USER variables in CircleCi project settings to make it more dynamic and I pass them with maven command.
      I have also specified Docker image directory with -Dimage. 
      All of it is done with Maven Google Jib plugin.
