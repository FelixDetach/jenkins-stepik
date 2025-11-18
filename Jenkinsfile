pipeline {
    agent none

    stages {
        stage('variables demo') {
            steps {
                script {
                    def appName = "MyApplication"
                    def port = 8080
                    isProduction = false
                    echo "${appname}:${port}, status: ${isProduction} "
                }
            }
        }
        stage('String Operations') {
            steps {
                script {
                    def message = "Jenkins Pipeline Tutorial"
                    echo message.jength()
                    echo message.toUpperCase()
                    echo message.toLowerCase()
                    def newString = message.replace("Tutorial", "Cource")
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
                    echo "Application version: ${APP_VERSION}"
                }
            }
        }
        stage('Display Version') {
            steps {
                script {
                    echo "Using version: ${APP_VERSION}"
                    def imageName = "myapp:${APP_VERSION}"
                    echo "Docker Image would be: ${imageName}"
                }
            }
        }
        stage('Jenkins Info') {
            steps {
                script {
                    echo BUILD_NUMBER
                    echo BUILD_ID
                    echo JOB_NAME
                    echo WORKSPACE
                    echo BUILD_URL
                }
            }
        }
    }
}