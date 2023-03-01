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
        sh 'mvnw clean install -P buildDocker'
      }
    }

   stage ('start service') {
      steps {        
        sh 'scripts/run_all.sh'        
        }
       }

      }
}
