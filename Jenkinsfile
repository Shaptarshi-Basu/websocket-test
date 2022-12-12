pipeline {
  environment {
    imagename = "chat-app"
    registryCredential = 'basu2110'
    dockerImage = ''
  }
  agent any
  stages {
    stage('Cloning Git') {
      steps {
        git([url: 'https://github.com/Shaptarshi-Basu/websocket-test.git', branch: 'main'])
 
      }
    }
    stage('Building image') {
      steps{
        script {
          dockerImage = docker.build imagename
        }
      }
    }
    stage('Push image') {
      steps{
        script {
          withDockerRegistry([ credentialsId: "docker_cred", url: "https://index.docker.io/v1/" ]) {
          dockerImage.push()
          }
        }
      }
    }
  }
}
