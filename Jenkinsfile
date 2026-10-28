
pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:24-alpine'
                    reuseNode true
                }
            }

            steps {
                sh '''
                    pwd
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    pwd
                '''
            }
        }
    }
}
