pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID     = credentials('aws-creds-access-key-id')
        AWS_SECRET_ACCESS_KEY = credentials('aws-creds-access-key')
    }
    stages {
        stage('Example stage 2') {
            steps {
                withAWS(credentials: 'aws-credentials', region: 'us-east-1') {
                   s3FindFiles bucket:'exploit-cloudformation'
                   sh 'echo files=${file}'
                   sh 'echo "hello KB">hello.txt'
                   sh 'printenv|sort'
                }
            }
        }
    }
}
