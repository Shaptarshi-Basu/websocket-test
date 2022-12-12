pipeline {
    agent any
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
          sh 'docker build -t chat-app .'  
        }
      }
   }
}
