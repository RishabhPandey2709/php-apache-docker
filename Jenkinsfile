pipeline {
  environment {
    registry = "imrishabh27/ci_images"
    registryCredential = 'docker-hub-cred'
    dockerImage = 'ci_images'
  }
  agent any
  
  stages {
    stage('Cloning Git') {
      steps {
        git 'https://github.com/rishank69/php-apache-docker.git'
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
            docker.withRegistry( '', registryCredential ) {
            dockerImage.push()
          }
        }
      }
    }
    
  }
}
