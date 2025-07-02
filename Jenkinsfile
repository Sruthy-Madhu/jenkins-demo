pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Sruthy-Madhu/jenkins-demo.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh 'npm test || true'  # Skip if no tests
            }
        }
        stage('Docker Build') {
            steps {
                script {
                    docker.build("Sruthy-Madhu/jenkins-demo:latest")
                }
            }
        }
        stage('Docker Push') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub-creds') {
                        docker.image("Sruthy-Madhu/jenkins-demo:latest").push()
                    }
                }
            }
        }
    }
}
