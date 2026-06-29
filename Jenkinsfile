pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                    echo "Build stage completed."
                }
            }
        stage('Test') {
            echo "Test stage"
            }    
            steps {
                sh '''
                    test /build/index.html
                '''
            }
        }
    }
}
