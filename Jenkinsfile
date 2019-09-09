node {
  stage 'Checkout'
  git 'http://github.com/rishank69/php-apache-docker' 
 
  stage 'Docker build'
  docker.build('demo')
 
  stage 'Docker push'
  docker.withRegistry('https://cloud.docker.com/u/imrishabh27/repository/docker/imrishabh27/demo', 'docker-hub') {
    docker.image('demo').push('latest')
  }
}
