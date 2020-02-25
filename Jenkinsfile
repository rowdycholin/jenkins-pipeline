pipeline {
  agent none
  def node6_ver
  def node_ver
  stages {
    stage('Run Tests') {
      parallel {
        stage('Test On node latest') {
          agent { docker { image 'node:latest' } }
          steps {
            sh "node_ver=`npm -v`"
          }
        }
        stage('Test On node6.3') {
          agent { docker { image 'node:6.3'} }
          steps {
            sh "node6_ver=`npm -v`"
          }
        }
      }
    }
  }
  post {
    always {
      echo "node version: ${node_ver}"
      echo "node6 version: ${node6_ver}"
    }
  }
}
