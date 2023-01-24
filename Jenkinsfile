pipeline {
    agent any
    stages {
            stage('Setup') {
            steps {
                withEnv(["PATH+JENKINS=${env.PATH}:/var/lib/jenkins/.local/bin"]) {
            }
        }
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
                sh 'flask --app main.py run'
            }
        }
        stage('Test') {
            steps {
                sh 'python3 req.py'
            }
        }
    }
}