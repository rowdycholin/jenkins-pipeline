pipeline {
  agent none
  stages {
    stage('Run Tests') {
      parallel {
        stage('Test On node lates') {
          agent { docker { image 'node:latest' } }
          steps {
            sh "npm -v"
          }
        }
        stage('Test On node6.3') {
          agent { docker { image 'node:6.3'} }
          steps {
            sh "npm -v"
          }
        }
      }
    }
  }
}
