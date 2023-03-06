pipeline {
  agent any

  tools {
    maven 'MAVEN_HOME' 
  }
  stages {

    stage ('clone code') {
      steps {
        git 'https://github.com/sridharp24/spring-petclinic-microservices.git'
      }
    }

    stage ('build code') {
      steps {
        sh '/var/lib/jenkins/workspace/spring-petclinic-microservices/mvnw clean install -P buildDocker'
      }
    }

   stage ('start service') {
      steps {        
        sh 'docker-compose --file /var/lib/jenkins/workspace/spring-petclinic-microservices/docker-compose.yml up'        
        }
       }

      }
}
