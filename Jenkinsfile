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
        stage('Test On Centos') {
          agent { docker { image 'centos:latest' } }
          steps {
            sh "uname -r"
          }
        }
      }
    }
  }
}
