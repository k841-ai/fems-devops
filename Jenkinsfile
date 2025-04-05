pipeline {
    agent any
    environment {
        PATH = "/usr/local/bin:/opt/homebrew/bin:/usr/bin:/bin:/usr/sbin:/sbin"
    }
    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning source code...'
            }
        }
        stage('Build') {
            steps {
                echo 'Building application...'
            }
        }
        stage('Docker Build') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t keisha841/fems-backend:latest .'
            }
        }
        stage('Docker Push') {
            steps {
                echo 'Pushing Docker image...'
                sh 'docker push keisha841/fems-backend:latest'
            }
        }
    }
    post {
        always {
            echo 'Pipeline completed.'
        }
    }
}
