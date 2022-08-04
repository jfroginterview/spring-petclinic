pipeline {
    environment {
      registry = "jfroginterview/"
      registryCredential = 'jfroginterviewRepository'
      registryUri = 'https://jfroginterviewregistry.jfrog.io'
      registryBase = "jfroginterviewregistry.jfrog.io/"
      dockerImage = ''
    }
    agent any
    tools {
      maven 'maven-3.8.4'
    }
    stages {
      stage('Compile') {
        steps {
            sh 'mvn clean install'
        }
      }
      stage('Building Image') {
        steps{
          script {
            dockerImage = docker.build registryBase + registry + "petclinic:latest"
          }
        }
      }
      stage('Push Image') {
        steps{
           script {
              docker.withRegistry( registryUri, registryCredential ) {
              dockerImage.push()
            }
          }
        }
      }
    }
}
