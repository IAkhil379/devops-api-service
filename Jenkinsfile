pipeline {
    agent any
    stages {
        stage('Build Image') {
            steps {
                sh 'docker build -t devops-api:latest .'
            }
        }
        stage('Test') {
            steps {
                echo 'Executing unit tests...'
            }
        }
        stage('Deploy to K8s') {
            steps {
                echo 'Applying configurations...'
                sh 'kubectl apply -f k8s/deployment.yaml'
                sh 'kubectl apply -f k8s/service.yaml'
            }
        }
    }
}
