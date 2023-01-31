pipeline {
    agent {
        docker {
            image 'docker.io/notfazed274/docker-poc:latest'
        }
    }
    stages {
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
