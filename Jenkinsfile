pipeline {
    agent any

    stages {
        stage('Build stage') {
            agent {
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    ls -la
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }
        stage('Test stage') {
            steps {
                sh '''
                    echo 'Test stage starged'
                    test -f build/index.html
                '''
            }
        }
    }
}
