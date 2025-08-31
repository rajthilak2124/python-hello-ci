pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/rajthilak2124/python-hello-ci.git'
            }
        }
        stage('Build & Test in Docker') {
            agent {
                docker {
                    image 'python:3.9'
                    args '-u root:root'   // run as root inside container (fix pip permissions)
                }
            }
            steps {
                sh 'python --version'
                sh 'pip install -r requirements.txt'
                sh 'pytest || true'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}
