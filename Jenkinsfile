pipeline {
    agent any
    stages {
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
                sh 'newman run POC.postman_collection.json'
            }
        }
    }
}