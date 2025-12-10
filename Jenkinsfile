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
                sh 'ls -l'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying HTML website to /var/www/html-jenkins"
                sh '''
                    rm -rf /var/www/html-jenkins || true
                    mkdir -p /var/www/html-jenkins
                    cp -r * /var/www/html-jenkins
                '''
            }
        }
    }

    post {
        success {
            echo "🎉 Deployment Successful!"
        }
        failure {
            echo "❌ Deployment Failed!"
        }
    }
}
