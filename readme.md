# Readme.md

## Steps taken to complete the request

**Local server**
* Provisioned a Centos 7 VM on my local server
* Installed Java 11
* Installed Jenkins
* Installed Docker

**Gmail**
* Created email address (jfroginterview@gmail.com)

**Github**
* Created online account with Gmail account
* Forked petclinic project into https://github.com/jfroginterview/spring-petclinic
* Removed nohttp-checkstyle checks from pom.xml file (lines 146 through 162) to prevent the http vs https errors happening when looking for dependencies.
* Created Jenkinsfile
* Created Dockerfile

**JFrog**
* Created online cloud account (jfroginterviewregistry.jfrog.io)
* Created local repository for docker images (jfroginterview)
* Will send credentials for "docker login" through email

**Jenkins**
* Created pipeline
* Configured GitHub as repo
* Added global credentials for JFrog registry
* Set up tools: Maven 3.8.4

## How to run the project

With Docker installed on the machine, run the following steps:
* docker login -u _usernameSentByEmail_ -p _passwordSentByEmail_
* docker run -d -p 8080:8080 jfroginterviewregistry.jfrog.io/jfroginterview/petclinic:latest
* The website will be available at http://localhost:8080

