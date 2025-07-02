pipeline {
    agent any
    tools {
        nodejs 'nodejs'  // Must match the name in Jenkins Tools
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Sruthy-Madhu/jenkins-demo.git'
            }
        }
        stage('Build') {
            steps {
                sh 'npm install'
                sh 'npm run build'
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
