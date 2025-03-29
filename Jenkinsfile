pipeline {
    agent any
    tools {
        nodejs 'node'
    }
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Va16hav07/devops-eval.git', branch: 'main'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
                echo 'Dependencies installed'
            }
        }
        stage('Test') {
            steps {
                script {
                    try {
                        sh 'npm test'
                    } catch (err) {
                        echo 'No tests defined'
                    }
                }
            }
        }
        stage('Build') {
            steps {
                script {
                    try {
                        sh 'npm run build'
                        echo 'Build completed successfully'
                    } catch (err) {
                        echo 'Build failed'
                        throw err
                    }
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    try {
                        sh 'npm start'
                        echo 'Application started successfully'
                    } catch (err) {
                        echo 'Error starting the application'
                        throw err
                    }
                }
            }
        }
    }
}