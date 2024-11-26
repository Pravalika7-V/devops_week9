
pipeline {
    agent any 

    stages {
        stage('Build') {
            steps {
                script {
                    bat 'docker build -t Pravalika7/my-app .'
                     bat 'docker tag Pravalika7/my-app:latest Pravalika7/my-app:latest'
                      bat 'docker push Pravalika7/my-app:latest'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Run tests here if you have any
                    echo 'Running tests...'
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                   //  Deploy your Docker image
                   bat 'minikube start'
                    bat 'kubectl apply -f my-kube1-deployment.yaml'
                   bat 'kubectl apply -f my-kube1-service.yaml'
                    bat 'minikube dashboard'
                    bat 'kubectl get services'
                    echo 'Deploying application...'
                }
            }
        }
    }
}
