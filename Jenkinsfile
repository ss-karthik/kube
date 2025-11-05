pipeline {
    agent any 

    stages {
        stage('Build') {
            steps {
                script {
                    sh 'docker login -u karthikss -p karthikss123'

                    sh 'docker build -t w9-dd-app:latest .'
                    sh 'docker tag w9-dd-app:latest siddharthpg/w9-dh-app:latest'
                    sh 'docker push siddharthpg/w9-dh-app:latest'
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
                    sh 'kubectl apply -f my-kube1-deployment.yaml'
                    sh 'kubectl apply -f my-kube1-service.yaml'
                    echo '✅ Deployedsuccessfully to Minikube!'
                } 
            }
        }
    }
}