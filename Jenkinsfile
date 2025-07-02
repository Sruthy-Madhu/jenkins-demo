pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/your-username/jenkins-demo.git'
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
                    docker.build("your-dockerhub-username/jenkins-demo:latest")
                }
            }
        }
        stage('Docker Push') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub-creds') {
                        docker.image("your-dockerhub-username/jenkins-demo:latest").push()
                    }
                }
            }
        }
    }
}
