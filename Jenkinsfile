pipeline {
	agent none
  stages {
  	stage('Maven Install') {
    	agent {
      	docker {
        	image 'go:1.19.4'
        }
      }
      steps {
      	sh 'go --version'
      }
    }
    stage('Docker Build') {
    	agent any
      steps {
      	sh 'docker build -t chat-app .'
      }
    }
  }
}
