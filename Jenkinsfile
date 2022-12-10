pipeline {
    agent none
    tools {
       go '1.19'
    }
    stages {
       stage('Build') {
        steps {
          // Output will be something like "go version go1.19 darwin/arm64"
          sh 'go version'
          sh 'go build main.go'
          sh 'ls'
        }
      }
      stage('Docker Build') {
    	agent any
      steps {
      	sh 'docker build -t shanem/spring-petclinic:latest .'
      }
    }  
   }
}
