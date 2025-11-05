pipeline {
    agent any

    environment {
        IMAGE_NAME = "kube1:latest"
        DOCKER_HUB_REPO = "karthikss123/kube"
    }

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/ss-karthik/kube.git'
            }
        }

        stage('Build Docker Image') {
    steps {
        sh 'docker build -t karthikss123/kube:latest .'
    }
}


        stage('Push to Docker Hub') {
    steps {
        sh '''
            docker login -u karthikss123 -p Km68vk@11
            docker push karthikss123/kube:latest
        '''
    }
}

    }
}