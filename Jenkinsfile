pipeline {
    agent any

    stages {

        stage('List Basics') {
            steps {
                script {
                    def environments = ['dev', 'staging', 'production']

                    echo "${environments[0]}"
                    echo "${environments[-1]}"
                    echo "${environments.size()}"

                    environments.add('qa')
                    echo "${environments.size()}"
                }
            }
        }

        stage('Deploy to Servers') {
            steps {
                script {
                    def servers = [
                        'server1.example.com',
                        'server2.example.com',
                        'server3.example.com'
                    ]

                    for (server in servers) {
                        echo "Deploying to ${server}"
                        sleep(time: 1, unit: 'SECONDS')
                        echo "Deployment to ${server} completed."
                    }
                }
            }
        }

        stage('Config Map') {
            steps {
                script {
                    def config = [
                        'appName'    : 'MyWebApp',
                        'version'    : '2.0.0',
                        'port'       : 8080,
                        'environment': 'production'
                    ]

                    config.each { key, value ->
                        echo "${key}: ${value}"
                    }

                    config['region'] = 'us-east-1'

                    echo "${config.size()}"
                    echo "${config}"
                }
            }
        }

        stage('Multi-environment deploy') {
            steps {
                script {
                    def environments = [
                        'dev'    : ['dev1.example.com', 'dev2.example.com'],
                        'staging': ['stage1.example.com'],
                        'prod'   : ['prod1.example.com', 'prod2.example.com', 'prod3.example.com']
                    ]

                    environments.each { env, servers ->
                        for (server in servers) {
                            echo "Deploying to ${env}: ${server}"
                        }
                    }
                }
            }
        }

        stage('filter-environment') {
            steps {
                script {
                    echo "Filter stage placeholder"
                }
            }
        }
    }
}
