pipeline {
    agent any

    environment {
        DEPLOY_ENV = 'production'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building application...'
                echo "${env.BRANCH_NAME}"
            }
        }

        stage('Deploy to Production') {
            when {
                branch 'main'
            }
            steps {
                echo 'Deploying to production...'
                echo 'Branch: main - deployment allowed'
            }
        }

        stage('Run tests') {
            when {
                expression {
                    env.BUILD_NUMBER.toInteger() % 2 == 0
                }
            }
            steps {
                script {
                    echo "Running tests for build ${env.BUILD_NUMBER}"
                    echo "This is an even-numbered build"
                }
            }
        }

        stage('Skip tests') {
            when {
                expression {
                    env.BUILD_NUMBER.toInteger() % 2 != 0
                }
            }
            steps {
                echo "Skipping tests for build ${env.BUILD_NUMBER}"
                echo "This is an odd-numbered build"
            }
        }

        stage('Security scan') {
            when {
                allOf {
                    anyOf {
                        branch 'main'
                        branch 'release'
                    }
                    expression {
                        env.DEPLOY_ENV == 'staging' || env.DEPLOY_ENV == 'production'
                    }
                }
            }
            steps {
                script {
                    echo "Running security scan"
                    echo "Branch: ${env.BRANCH_NAME}, Environment: ${env.DEPLOY_ENV}"
                }
            }
        }

        stage('Summary') {
            steps {
                echo """
                === Pipeline Execution Summary ===
                Branch: ${env.BRANCH_NAME}
                Build Number: ${env.BUILD_NUMBER}
                Deploy environment: ${env.DEPLOY_ENV}
                All stages completed.
                """
            }
        }
    }
}
