pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/akshayaaa-08/github-jenkin-deployment.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t devops-demo .'
            }
        }

        stage('Deploy') {
            steps {
                bat 'docker stop devops-demo || exit 0'
                bat 'docker rm devops-demo || exit 0'
                bat 'docker run -d --name devops-demo -p 8081:80 devops-demo'
            }
        }
    }
}
