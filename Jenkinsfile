
pipeline {
    agent any

    stages {
        stage('Check Docker') {
            steps {
                bat 'docker --version'
            }
        }

        stage('check node version'){
            steps{
                  bat '''
                        node --version
                        npm --version
                  '''
            }
        }

        stage('Build React') {
            steps {
                bat '''
                    docker run --rm ^
                    -v "%CD%:/app" ^
                    -w /app ^
                    node:24-alpine ^
                    sh -c "node --version && npm --version && npm ci && npm run build"
                '''
            }
        }
    }
}
