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
The Test stage has completed.

Status: ${currentBuild.currentResult}
Build Number: ${env.BUILD_NUMBER}

The Jenkins build log is attached to this email.
""",
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
                        body: """
The Security Scan stage has completed.

Status: ${currentBuild.currentResult}
Build Number: ${env.BUILD_NUMBER}

The Jenkins build log is attached to this email.
""",
                        attachLog: true
                    )
                }
            }
        }
    }
}
