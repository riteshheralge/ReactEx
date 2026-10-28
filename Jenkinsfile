
pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node'
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
