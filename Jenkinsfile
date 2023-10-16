pipeline{
    agent any
    stages {
        stage('Build and Test'){
            steps {
                script {
                    // checkout the code from the github repository
                    checkout scm

                    // Build the Docker image
                    sh 'docker build -t my-web-app .'
                }
            }
        }
        stage('Deploy to kubernetes'){
            steps {
                sh 'kubectl apply -f deployment.yaml'
            }
        }
    }
}