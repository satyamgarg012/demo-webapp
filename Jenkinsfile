pipeline {

    agent any

    environment {
        IMAGE_NAME = "demo-webapp"
    }

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                kubectl apply -f deployment.yaml
                kubectl apply -f service.yaml
                '''
            }
        }
    }
}
