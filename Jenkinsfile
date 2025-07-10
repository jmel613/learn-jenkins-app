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
                    npm run build
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
                    ls
                    test -f public/index.html
                    npm --version
                    npm test
                '''
            }
        }
    }
}