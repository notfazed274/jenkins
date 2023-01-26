pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps
                node('14.x') {
                git url: 'https://github.com/notfazed274/jenkins.git', branch: 'main'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'pip install --user -r requirements.txt'
            }
        }
        stage('Run Flask app') {
            steps {
                sh 'flask --app main.py run &'
            }
        }
        stage('Test') {
            steps {
                sh 'python3 req.py'
            }
        }
    }
}