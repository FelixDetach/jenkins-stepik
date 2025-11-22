pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Building application..."
                sh 'mkdir -p ./build'
                sh 'echo "Application binary" > ./build/app.jar'
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                sleep 2
                echo "Test completed"
            }
            post {
                always {
                    echo "Pipeline finished"
                    echo "Build number: ${env.BUILD_NUMBER}"
                }
                failure {
                    echo "Pipeline failed"
                    echo "Build number: ${env.BUILD_NUMBER}"
                }
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying application..."
                sleep 3
                echo "Deployment completed"
            }
            post {
                always {
                    echo "Deployment stage finished"
                    sh 'ls -la build/'
                }
            }
        }
    }

    post {
        always {
            echo "===Post actions==="
            echo "Pipeline completed"
            sh 'date'

            echo "Archiving build artifacts..."
            sh 'tar -czf build_artifacts.tar.gz -C build .'
            sh 'ls -lh build_artifacts.tar.gz'
            echo "Archive artifacts completed"
        }
    }
}
