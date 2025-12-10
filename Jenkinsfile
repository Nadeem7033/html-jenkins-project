pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/Nadeem7033/html-jenkins-project.git'
            }
        }

        stage('Build') {
            steps {
                echo "No build step required for HTML project."
            }
        }

        stage('Test') {
            steps {
                echo "Testing HTML files..."
                bat """
                echo Checking files...
                dir
                """
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying website..."
                bat """
                if not exist C:\\deploy mkdir C:\\deploy
                xcopy /s /y * C:\\deploy\\
                """
            }
        }
    }

    post {
        success {
            echo "✔ Deployment Successful!"
        }
        failure {
            echo "❌ Deployment Failed!"
        }
    }
}
