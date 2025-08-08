pipeline {
    agent {
        docker {
            image 'node:18'  // This image has node + npm
            args '-v /var/run/docker.sock:/var/run/docker.sock'  // Give access to Docker
        }
    }

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/NagaprajwalB/task2.git'
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
                sh 'docker run -d -p 3000:3000 nodejs-demo-app'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed.'
        }
    }
}
