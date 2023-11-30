pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from Git
                script {
                    checkout scm
                }
            }
        }

        stage('Install Dependencies') {
            steps {
                // Install Node.js dependencies using npm
                script {
                    sh 'npm install'
                }
            }
        }

        stage('Build') {
            steps {
                // Build your Node.js application (replace 'build' with your build command)
                script {
                    sh 'npm run build'
                }
            }
        }

        stage('Test') {
            steps {
                // Run tests (replace 'test' with your test command)
                script {
                    sh 'npm test'
                }
            }
        }

        stage('Deploy') {
            steps {
                // Deploy your application (replace 'deploy' with your deployment command)
                script {
                    sh 'npm run deploy'
                }
            }
        }
    }
}
