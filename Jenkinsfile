pipeline {
    agent any

    stages {
        stage('Run Script') {
            steps {
                sh 'ls -l'
                sh 'chmod +x hello.sh'
                sh 'bash hello.sh'
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
