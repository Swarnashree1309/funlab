pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/Swarnashree1309/funlab.git'
            }
        }

    
    stages {

        stage('Build Docker Image') {
            steps {
                echo "Building Docker image..."
                sh 'docker build -t funlab-image .'
            }
        }

        stage('Run Container') {
            steps {
                echo "Running Docker container..."
                sh 'docker run -d -p 8080:80 funlab-image'
            }
        }
    }
    }
}
