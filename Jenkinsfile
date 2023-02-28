pipeline {
  agent any

  tools {
    maven 'MAVEN_HOME' 
  }
  stages {

    stage ('clone code') {
      steps {
        git 'https://github.com/sridharp24/spring-petclinic.git'
      }
    }

    stage ('build code') {
      steps {
        sh 'mvn clean package'
      }
    }

   stage ('deploy war') {
      steps {        
        deploy adapters: [tomcat8(credentialsId: 'TomcatCred', path: '', url: 'http://localhost:9090')], contextPath: '/petclinic', war: '**/*.jar'
        }
       }

      }
}
