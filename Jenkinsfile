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
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                   sh '''
                    ls -la
                    node --version
                    npm --version
                    npm cache clean --force 
                    npm install
                    npm run build
                    ls -la
                   '''
            }
        }
    }
}