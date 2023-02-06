pipeline {
    agent {
        docker {
            image 'docker.io/notfazed274/image-os:latest'
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
