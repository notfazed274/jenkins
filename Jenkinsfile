pipeline {
    agent {
        docker {
            image 'docker.io/notfazed274/image-os:latest'
	    args '-e SNAP_DATA=/home/snap'
        }
    }
    stages {
        stage('Run Flask app') {
            steps {
		sh 'snap install node --classic --channel=8'
		sh 'npm install newman'
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
