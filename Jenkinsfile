          
pipeline {
    agent any

    stages {

        stage('Clone Repo') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Swarnashree1309/funlab.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t funlab-image .'
            }
        }

        stage('Run Container') {
            steps {
                echo 'Running container...'
                sh '''
                docker stop funlab || true
                docker rm funlab || true
                docker run -d --name funlab -p 8080:80 funlab-image
                '''
            }
        }
    }
}
