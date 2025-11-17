pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                echo 'Привет от Jenkins и Просто Девопс!'
                echo 'Сегодняшняя дата:'
                sh 'date'
            }
        }
        stage('System info') {
            steps {
                echo 'system info:'
                sh 'uname -a'
                echo 'directory:'
                sh 'pwd'
                echo 'files:'
                sh 'ls -la'
            }
        }
        stage('Environment') {
            steps {
                echo "Build Number: ${BUILD_NUMBER}"
                echo "Job Name: ${JOB_NAME}"
                echo "Workspace: ${WORKSPACE}"
            }
        }
    }
}