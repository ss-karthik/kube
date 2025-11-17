pipeline {
    agent any 

    stages {
        stage('Build') {
            steps {
                script {
                    sh 'docker login -u karthikss123 -p Km68vk@11'

                    sh 'docker build -t my-kube:latest .'
                    sh 'docker tag my-kube:latest karthikss123/my-kube:latest'
                    sh 'docker push karthikss123/my-kube:latest'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    echo 'Running tests...'
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    sh 'minikube start'
                    sh 'kubectl apply -f my-kube1-deployment.yaml'
                    sh 'kubectl apply -f my-kube1-service.yaml'
                    echo '✅ Deployedsuccessfully to Minikube!'
                } 
            }
        }
    }
}
