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
