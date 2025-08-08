pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git url: 'https://github.com/NagaprajwalB/task2.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the app...'
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'npm test'
            }
        }

        stage('Docker Build') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t nodejs-demo-app .'
            }
        }

        stage('Docker Run') {
            steps {
                echo 'Running Docker container...'
                sh 'docker run -d -p 3000:3000 --name nodejs-app nodejs-demo-app'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed.'
        }
    }
}
