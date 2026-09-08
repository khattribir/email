pipeline {
    agent any

    stages {

        stage('Run Tests') {
            steps {
                echo 'Running Tests'
            }

            post {
                always {
                    emailext(
                        to: 'khattriveer2@gmail.com',
                        subject: "Test Stage - ${currentBuild.currentResult}",
                        body: """
Test stage completed.

Status: ${currentBuild.currentResult}
Build Number: ${env.BUILD_NUMBER}
""",
                        attachLog: true,
                        compressLog: true
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
                        body: """
Security Scan stage completed.

Status: ${currentBuild.currentResult}
Build Number: ${env.BUILD_NUMBER}
""",
                        attachLog: true,
                        compressLog: true
                    )
                }
            }
        }
    }
}
