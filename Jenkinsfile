pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/notfazed274/jenkins.git', branch: 'main'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }
        stage('Run Flask app') {
            steps {
                sh '/var/lib/jenkins/.local/bin/flask --app main.py run &'
            }
        }
        stage('Test') {
            steps {
                sh 'python3 req.py'
            }
        }
    }
}