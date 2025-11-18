pipeline {
    agent none

    stages {
        stage('variables demo') {
            steps {
                script {
                    def appName = "MyApplication"
                    def port = 8080
                    def isProduction = false
                    echo "${appName}:${port}, status: ${isProduction}"
                }
            }
        }

        stage('String Operations') {
            steps {
                script {
                    def message = "Jenkins Pipeline Tutorial"
                    echo message.length().toString()
                    echo message.toUpperCase()
                    echo message.toLowerCase()
                    def newString = message.replace("Tutorial", "Course")
                    echo newString
                }
            }
        }

        stage ('Build Version') {
            steps {
                script {
                    def major = 1
                    def minor = 0
                    def patch = env.BUILD_NUMBER
                    env.APP_VERSION = "${major}.${minor}.${patch}"
                    echo "Application version: ${env.APP_VERSION}"
                }
            }
        }

        stage('Display Version') {
            steps {
                script {
                    echo "Using version: ${env.APP_VERSION}"
                    def imageName = "myapp:${env.APP_VERSION}"
                    echo "Docker Image would be: ${imageName}"
                }
            }
        }

        stage('Jenkins Info') {
            steps {
                script {
                    echo env.BUILD_NUMBER
                    echo env.BUILD_ID
                    echo env.JOB_NAME
                    echo env.WORKSPACE
                    echo env.BUILD_URL
                }
            }
        }
    }
}
