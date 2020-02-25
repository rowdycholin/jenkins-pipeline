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
	    script {
              node_ver = sh ( script: "npm -v", returnStdout: true).trim()
	    }
          }
        }
        stage('Test On node6.3') {
          agent { docker { image 'node:6.3'} }
          steps {
	    script {
              node6_ver = sh ( script: "npm -v", returnStdout: true).trim()
	    }
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
