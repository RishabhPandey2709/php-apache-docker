node {
  stage 'Checkout'
  git 'http://github.com/rishank69/php-apache-docker' 
 
  stage 'Docker build'
  docker.build('demo')
 
  stage 'Docker push'
  docker.withRegistry('https://cloud.docker.com/repository/registry-1.docker.io/imrishabh27/demo', 'docker-hub') {
    docker.image('demo').push('latest')
  }
}
