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
                sh 'pip install --user -r requirements.txt'
            }
        }
         stage('API testing') {
            steps {
                sh 'npm install'
                sh 'npm install newman'
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