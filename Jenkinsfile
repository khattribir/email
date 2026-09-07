pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                sh 'npm install || true'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test || true'
            }
            post {
                always {
                    emailext(
                        to: 'khattriveer2@gmail.com',
                        subject: 'Test Stage Completed',
                        body: 'The Test stage has finished. Check attached log.',
                        attachLog: true
                    )
                }
            }
        }

        stage('Security Scan') {
            steps {
                sh 'npm audit || true'
            }
            post {
                always {
                    emailext(
                        to: 'khattriveer2@gmail.com',
                        subject: 'Security Scan Completed',
                        body: 'The Security Scan stage has finished. Check attached log.',
                        attachLog: true
                    )
                }
            }
        }
    }
}
