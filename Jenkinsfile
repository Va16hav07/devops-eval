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
                sh 'npm test'
                echo 'Tests executed'
            }
        }
        stage('Build') {
            steps {
                echo 'Building the project'
                sh 'npm run build'
                echo 'Build completed'

            }
        }
    }
}