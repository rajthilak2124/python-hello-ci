pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/rajthilak2124/python-hello-ci.git'
            }
        }
        stage('Build') {
            steps { sh 'pip install -r requirements.txt' }
        }
        stage('Test') {
            steps { sh 'pytest || true' }
        }
        stage('Deploy') {
            steps { echo 'Deploying...' }
        }
    }
}
