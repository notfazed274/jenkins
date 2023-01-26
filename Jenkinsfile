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
                sh 'curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -'
                sh 'sudo apt-get install -y nodejs'
                sh 'npm install -g newman'
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