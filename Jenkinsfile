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
    }
}