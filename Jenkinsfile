pipeline {
  agent any
  
  
  
  stages {
    stage('greeting') {
      steps {
        sh '''echo "hello world!"
'''
   
      }
    }
    stage('Build docker') {
      steps {
        sh 'docker build -t bray/popcorn:$BUILD_NUMBER .'
      }
    }
    }
      }
      stage('testing') {
        steps {
         sh '''docker run popcorn:$BUILD_NUMBER rails test
'''
    stage('docker push') {
      steps {
        sh '''docker login -u bray -p $DOCKER_PASSWORD
docker push bray/popcorn:$BUILD_NUMBER'''
      }
    }
  }
}