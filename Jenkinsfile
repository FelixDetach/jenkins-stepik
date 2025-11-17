pipeline {
    agent any

    stages {
        stage('Check agent') {
            steps {
                echo "running on agent..."
                sh 'hostname'
                sh 'echo "${WORKSPACE}"'
                sh 'echo "${NODE_NAME}"'
            }
        }
    }
}