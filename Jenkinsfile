def node6_ver
def node_ver

pipeline {
  agent none
  stages {
    stage('Run Tests') {
      parallel {
        stage('Test On node latest') {
          agent { docker { image 'node:latest' } }
          steps {
            sh "node_ver=`npm -v`"
            sh "echo node version: ${node_ver}"
          }
        }
        stage('Test On node6.3') {
          agent { docker { image 'node:6.3'} }
          steps {
            sh "node6_ver=`npm -v`"
            sh "echo node6 version: ${node6_ver}"
          }
        }
      }
    }
  }
  post {
    always {
      sh "echo node version: ${node_ver}"
      sh "echo node6 version: ${node6_ver}"
    }
  }
}
