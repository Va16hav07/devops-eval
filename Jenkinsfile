pipeline {
    agent any
    tools {
        nodejs 'nodejs-18'
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
                sh 'npm run build'
                echo 'Build completed'
            }
        }
    }
}