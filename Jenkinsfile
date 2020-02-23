pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID     = credentials('aws-creds-access-key-id')
        AWS_SECRET_ACCESS_KEY = credentials('aws-creds-access-key')
    }
    stages {
        stage('Example stage 2') {
            steps {
                sh 'printenv' 
            }
        }
    }
}
