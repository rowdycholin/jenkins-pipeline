def node16_ver
def node_ver

pipeline {
  agent any
  stages {
    stage('Run Tests') {
      parallel {
        stage('Test On node latest') {
          agent { docker { image 'node:latest' } }
          steps {
	    script {
              node_ver = sh ( script: "node --version", returnStdout: true).trim()
	    }
          }
        }
        stage('Test On node 16.13') {
          agent { docker { image 'node:16.13'} }
          steps {
	    script {
              node16_ver = sh ( script: "node --version", returnStdout: true).trim()
	    }
          }
        }
      }
    }
  }
  post {
    always {
      echo 'node version: ${node_ver}'
      echo "node6 version: ${node6_ver}"
    }
  }
}
