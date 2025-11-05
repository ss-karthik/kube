pipeline {
    agent any

    environment {
        DOCKER_HOST = "unix:///home/karthik/.docker/desktop/docker.sock"
    }

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    // Build the image (name it however you like)
                    dockerImage = docker.build("my-kube1:latest")
                }
            }
        }

        stage('Push to Docker Hub') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', 'dockerhub-credentials') {
                        dockerImage.push('latest')
                    }
                }
            }
        }
    }
}