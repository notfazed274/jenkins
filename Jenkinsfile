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
                echo 'Executing .py files...'
                sh 'python3 main.py'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
    }
}