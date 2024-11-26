pipeline {
    agent any 

    stages {
        stage('Build') {
            steps {
                script {
                    bat 'docker build -t w9-csedd .'
                     bat 'docker tag w9-csedd:latest shiv4j/w9-dh-app-csedd:latest'
                      bat 'docker push shiv4j/w9-dh-app-csedd:latest'
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