pipeline {
  agent none
  stages {
    stage('Run Tests') {
      parallel {
        stage('Test On Alpine') {
          agent { docker { image 'node:7-alpine' } }
          steps {
            sh "uname -r"
          }
        }
        stage('Test On ubuntu') {
          agent { docker { image 'ubuntu:latest' } }
          steps {
            sh "uname -r"
          }
        }
      }
    }
  }
}
