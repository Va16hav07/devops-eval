pipline{
    tools{
        nodejs 'nodejs-18'
    }
    stages{
        stage('commit'){
            git url: 'https://github.com/Va16hav07/devops-eval.git' , branch : 'main'
        }
        stage('clone'){
            sh 'git clone ${GIT_URL} ${WORKSPACE}'
            echo 'Repository cloned'
        }
        stage('intalling dependencies'){
            steps{
                sh 'npm install'
                echo 'Dependencies installed'
            }
        }
        stage('test'){
            steps{
                sh 'npm test' || echo 'No tests defined'
            }
        }
        stage('build'){
            steps{
                sh 'npm run build'
                echo 'Build completed'
            }
        }
    }
}