pipeline {
    agent none

    stages {
        stage('Check agent') {
            agent any
            steps {
                echo "running on agent..."
                sh 'hostname'
                sh 'echo "${WORKSPACE}"'
                sh 'echo "${NODE_NAME}"'
            }
        }
        stage('Build info') {
            agent any
            steps {
                echo 'Build information...'
                echo "$BUILD_NUMBER"
                echo "$BUILD_ID"
                echo "$BUILD_URL"
            }
        }
    }
}