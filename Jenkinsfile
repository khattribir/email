pipeline {
    agent any

    stages {

        stage('Run Tests') {
            steps {
                echo 'Running Tests'
            }
            post {
                always {
                    mail(
                        to: 'khattriveer2@gmail.com',
                        subject: "Test Stage - SUCCESS",
                        body: "The Test stage has completed successfully."
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
                    mail(
                        to: 'khattriveer2@gmail.com',
                        subject: "Security Scan - SUCCESS",
                        body: "The Security Scan stage has completed successfully."
                    )
                }
            }
        }
    }
}
