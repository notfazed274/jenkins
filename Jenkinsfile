pipeline {
    agent {
        docker {
            image 'docker.io/notfazed274/2-1-test-1:latest'
        }
    }
    stages {
        stage('Test') {
            steps {
                sh 'newman run collection-2.json'
            }
        }
    }
}
