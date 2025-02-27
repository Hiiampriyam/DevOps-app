pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Hiiampriyam/devops-app.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t priyamarora/devops-app .'
            }
        }
        stage('Push Image to Docker Hub') {
            steps {
                withDockerRegistry([credentialsId: 'docker-hub-credentials', url: '']) {
                    sh 'docker push your-dockerhub-username/devops-app'
                }
            }
        }
    }
}
