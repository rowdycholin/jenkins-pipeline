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
        stage('Test On guyton/centos6') {
          agent { docker { image 'guyton/centos6'} }
          steps {
            sh "uname -r"
          }
        }
      }
    }
  }
}
