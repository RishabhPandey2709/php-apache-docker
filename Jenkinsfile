pipeline {
  environment {
    registry = "imrishabh27/demo"
    registryCredential = 'docker-hub'
    dockerImage = 'demo'
  }
  agent any
  
  stages {
    stage('Cloning Git') {
      steps {
        git 'http://github.com/rishank69/php-apache-docker'
      }
    }
    
    stage('Building image') {
      steps{
        script {
          dockerImage = docker.build registry + ":$BUILD_NUMBER"
        }
      }
    }
    stage('Deploy Image') {
      steps{
         script {
            docker.withRegistry( 'https://registry.hub.docker.com/imrishabh27/demo', registryCredential ) {
            dockerImage.push()
          }
        }
      }
    }
    
  }
}
