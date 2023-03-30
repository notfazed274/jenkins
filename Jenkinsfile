pipeline {
    agent {
        docker {
            image 'docker.io/notfazed274/2-1-test-1:latest'
        }
    }
    stages {
        stage('Test') {
            steps {
                script {
                    def reportFile = "newman-report.html"
                    sh "newman run collection-2.json -r html --reporter-html-export ${reportFile}"
                    sh "cat ${reportFile} | mail -s 'Newman Test Report' -a ${reportFile} admiring.visvesvaraya@gmail.com"
                }
            }
        }
    }
}

