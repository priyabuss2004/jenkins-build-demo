pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }

        stage('Build'){
            agent {
                docker {
                    image 'node:latest'
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
    }
}