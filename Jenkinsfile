pipeline {
    agent {
        docker {
            image 'docker.io/notfazed274/jenkins-docker-newman-mail:latest'
        }
    }
    stages {
        stage('Test') {
            steps {
                script {
                    def reportFile = "newman-report.html"
                    sh "newman run collection-2.json -r html --reporter-html-export ${reportFile}"
                    def emailBody = new File(reportFile).text
                    mail to: "admiring.visvesvaraya@gmail.com",
                        subject: "Newman Test Report",
                          mimeType: 'text/html',
                          body: emailBody,
                          attachments: [new FileAttachment("${reportFile}")]
                }
            }
        }
    }
}





