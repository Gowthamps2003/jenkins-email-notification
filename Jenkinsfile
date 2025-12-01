pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Gowthamps2003/jenkins-email-notification.git'
            }
        }

        stage('Run Script') {
            steps {
                sh 'chmod +x hello.sh'
                sh './hello.sh'
            }
        }
    }

    post {
        success {
            emailext (
                to: "gowthamps2003@gmail.com",
                subject: "Jenkins Build SUCCESS",
                body: "Build Successful!\n\nBuild URL: ${BUILD_URL}"
            )
        }

        failure {
            emailext (
                to: "gowthamps2003@gmail.com",
                subject: "Jenkins Build FAILED",
                body: "Build Failed!\n\nBuild URL: ${BUILD_URL}"
            )
        }
    }
}
