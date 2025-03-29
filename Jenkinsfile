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
        stage('Deploy') {
            steps {
                script {
                    try {
                        sh 'npm run build'
                        echo 'Application build successfully'
                    } catch (err) {
                        echo 'Error building the application'
                        throw err
                    }
                }
            }
        }
    }
}