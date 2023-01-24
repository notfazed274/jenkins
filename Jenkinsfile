pipeline {
    agent {
        docker {
            image 'Dockerfile'
        }
    }
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/notfazed274/jenkins.git', branch: 'main'
            }
        }
        stage('Test') {
            steps {
                sh 'python3 req.py'
            }
        }
    }
}