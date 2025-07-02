pipeline {
    agent any  // Runs on any available Jenkins agent

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Sruthy-Madhu/jenkins-demo.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Installing dependencies...'
                sh 'npm install'  // Example for Node.js (modify as needed)
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'npm test'  // Example test command
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Add deployment steps (e.g., `scp`, `rsync`, Docker push)
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
