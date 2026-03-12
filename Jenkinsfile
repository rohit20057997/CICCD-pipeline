pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t vite-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                bat 'docker rm -f vite-container || echo No existing container'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run -d -p 8081:80 --name vite-container vite-app'
            }
        }

    }
}