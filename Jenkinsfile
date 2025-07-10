pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                }
            }
            steps {
                sh '''
                    echo 'Building'
                    npm --version
                    npm ci
                    npm build all
                '''
            }
        }
                stage('Test') {
            agent {
                docker {
                    image 'node:18-alpine'
                }
            }
            steps {
                sh '''
                    echo 'Test stage'
                    test -f public/index.htmml
                    npm --version
                    npm ci
                    npm build all
                '''
            }
        }
    }
}