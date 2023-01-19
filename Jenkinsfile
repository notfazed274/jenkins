pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/notfazed274/jenkins.git', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'python main.py'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
    }
}