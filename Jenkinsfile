pipeline {
    agent any

    stages {

        stage('Run Tests') {
            steps {
                echo 'Running tests'
            }
            post {
                always {
                    emailext(
                        to: 'khattriveer2@gmail.com',
                        subject: "Test Stage - ${currentBuild.currentResult}",
                        body: "Test Stage completed with status: ${currentBuild.currentResult}",
                        attachLog: true
                    )
                }
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Running Security Scan'
            }
            post {
                always {
                    emailext(
                        to: 'khattriveer2@gmail.com',
                        subject: "Security Scan - ${currentBuild.currentResult}",
                        body: "Security Scan completed with status: ${currentBuild.currentResult}",
                        attachLog: true
                    )
                }
            }
        }
    }
}
