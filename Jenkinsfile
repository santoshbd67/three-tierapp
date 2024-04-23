pipeline {
    agent any

    
    stages {
stage('Checkout') {
            steps {
                git 'https://github.com/your/repository.git'
            }
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('santoshbd67/frontend', "-f /frontend/Dockerfile .")
                }
            }
        }

        stage('Push Docker Image') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', 'dockerhub') {
                        docker.image('santoshbd67/frontend').push('latest')
                    }
                }
            }
        }
    }
}
